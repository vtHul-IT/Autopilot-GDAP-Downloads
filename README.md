# CaptureTech Autopilot GDAP downloads

Deze repository bevat uitsluitend publieke, ondertekende releases van
**CaptureTech Autopilot GDAP** voor Windows x64. Broncode, PowerShell-engine en
operationele documentatie worden apart en privé beheerd.

## Downloaden

Download altijd de meest recente EXE en checksum vanaf
[Releases](https://github.com/vtHul-IT/Autopilot-GDAP-Downloads/releases).

Via PowerShell:

```powershell
$exe = Join-Path $env:TEMP 'capturetech-autopilot-gdap.exe'
Invoke-RestMethod 'https://github.com/vtHul-IT/Autopilot-GDAP-Downloads/releases/latest/download/capturetech-autopilot-gdap.exe' -OutFile $exe
Get-AuthenticodeSignature -LiteralPath $exe | Format-List Status,SignerCertificate,TimeStamperCertificate
Start-Process -FilePath $exe -Verb RunAs
```

Controleer vóór gebruik dat `Status` gelijk is aan `Valid` en dat de publisher
**CaptureTech IT-Services BV** is. Vergelijk voor bredere distributie ook de
meegeleverde `capturetech-autopilot-gdap.exe.sha256`.

## Meldingen en support

Gebruik voor functionele vragen en beveiligingsmeldingen de reguliere
CaptureTech IT-servicedesk. Plaats geen tokens, hardwarehashes of klantgegevens
in een GitHub-issue.
