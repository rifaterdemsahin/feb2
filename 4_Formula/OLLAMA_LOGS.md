# Ollama Logs - How to View and Debug

## Log Locations by OS

### Windows
Ollama logs are stored in your user profile directory:
```
%LOCALAPPDATA%\Ollama\server.log
```
Typical full path: `C:\Users\<username>\AppData\Local\Ollama\server.log`

**View logs in PowerShell:**
```powershell
Get-Content "$env:LOCALAPPDATA\Ollama\server.log" -Tail 50
```

**Follow logs in real-time:**
```powershell
Get-Content "$env:LOCALAPPDATA\Ollama\server.log" -Wait -Tail 20
```

### macOS
```bash
cat ~/.ollama/logs/server.log
```

### Linux (systemd)
```bash
journalctl -u ollama -f
```

If running manually, logs go to stdout/stderr in the terminal.

---

## Useful Log Commands

### Show last 100 lines
```powershell
Get-Content "$env:LOCALAPPDATA\Ollama\server.log" -Tail 100
```

### Search logs for errors
```powershell
Select-String -Path "$env:LOCALAPPDATA\Ollama\server.log" -Pattern "error|ERROR|fail"
```

### Search logs for a specific model
```powershell
Select-String -Path "$env:LOCALAPPDATA\Ollama\server.log" -Pattern "llama2"
```

### Clear the log file
```powershell
Clear-Content "$env:LOCALAPPDATA\Ollama\server.log"
```

---

## Enable Debug Logging

Set the environment variable before starting Ollama:

### Windows (PowerShell)
```powershell
$env:OLLAMA_DEBUG = "1"
ollama serve
```

### Windows (System Environment Variable - persistent)
```powershell
[System.Environment]::SetEnvironmentVariable("OLLAMA_DEBUG", "1", "User")
```
Then restart the Ollama service.

### Linux / macOS
```bash
OLLAMA_DEBUG=1 ollama serve
```

---

## Common Log Patterns to Look For

| Pattern | Meaning |
|---------|---------|
| `loading model` | Model is being loaded into memory |
| `model loaded` | Model ready to serve requests |
| `out of memory` | GPU/RAM insufficient for model |
| `connection refused` | Ollama server not running |
| `404` | Requested model not found |
| `compute capability` | GPU compatibility info |

---

## API Endpoint for Runtime Status

Check if Ollama is running and healthy:
```bash
curl http://localhost:11434/
```

List loaded models:
```bash
curl http://localhost:11434/api/tags
```

Check running models:
```bash
curl http://localhost:11434/api/ps
```

---

## Environment Variables Reference

| Variable | Purpose | Default |
|----------|---------|---------|
| `OLLAMA_DEBUG` | Enable verbose logging | `0` |
| `OLLAMA_HOST` | Bind address | `127.0.0.1:11434` |
| `OLLAMA_MODELS` | Custom model storage path | OS default |
| `OLLAMA_NUM_PARALLEL` | Max parallel requests | `1` |
| `OLLAMA_MAX_LOADED_MODELS` | Max models in memory | `1` |
