

To build donutCS on kali you'll first need to install the dotnet sdk.  
  
### First, add the microsoft keys

``` 
wget -qO- https://packages.microsoft.com/keys/microsoft.asc | gpg --dearmor > microsoft.asc.gpg  
mv microsoft.asc.gpg /etc/apt/trusted.gpg.d/  
wget -q https://packages.microsoft.com/config/debian/9/prod.list  
mv prod.list /etc/apt/sources.list.d/microsoft-prod.list   
``` 
### Second, install dotnet 2.1  
```
apt-get update 
apt-get install apt-transport-https  
apt-get update  
apt-get install dotnet-sdk-2.1  
```
### Third, clone this repo  
```
git clone https://github.com/n1xbyte/donutCS  
```

### Finally, move into the repo root and build
```
cd donutCS/
dotnet build
dotnet run
```
  
`dotnet run` will output the help menu  
  
```
DEBUG] Starting Donut
[DEBUG] Parsing Arguements:
Donut 1.0.0
Copyright (C) 2019 Donut

ERROR(S):
  Required option 'f, InputFile' is missing.

  -f, --InputFile         Required. .NET assembly, EXE, DLL, VBS, JS or XSL file to execute in-memory.

  -u, --URL               HTTP server that will host the donut module.

  -a, --Arch              (Default: 3) Target architecture : 1=x86, 2=amd64, 3=amd64+x86.

  -b, --Level             (Default: 3) Bypass AMSI/WLDP : 1=skip, 2=abort on fail, 3=continue on fail.

  -o, --Payload           (Default: payload.bin) Output file.

  -c, --NamespaceClass    Optional class name.  (required for .NET DLL)

  -m, --Method            Optional method or API name for DLL. (required for .NET DLL)

  -p, --Args              Optional parameters or command line, separated by comma or semi-colon.

  -r, --Version           CLR runtime version. MetaHeader used by default or v4.0.30319 if none available.

  -d, --Name              AppDomain name to create for .NET. Randomly generated by default.

  --help                  Display this help screen.

  --version               Display version information.

[DEBUG] Entering Donut_Create()
[DEBUG] Entering ParseConfig()
[DEBUG] Donut_Create() finished with: [-] Invalid parameter
```