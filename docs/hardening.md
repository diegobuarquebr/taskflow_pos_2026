
## Docker build e Trivy antes do hardening

Comandos rodados a partir da raiz do projeto
```
docker build -t taskflow:vuln -f codigo/app-exemplo/Dockerfile codigo/app-exemplo
trivy image --severity HIGH,CRITICAL taskflow:vuln > antes.txt
```
[Output to scan trivy](antes.txt) - arquivo com 1545 linhas

## Docker build e Trivy após hardening

Comandos rodados a partir da raiz do projeto
```
docker build -t taskflow:hardened -f Dockerfile codigo/app-exemplo
trivy image --severity HIGH,CRITICAL taskflow:hardened > depois.txt   
```
[Output to scan trivy](depois.txt) - arquivo com 230 linhas