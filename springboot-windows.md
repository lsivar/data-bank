# 1. springboot 启动脚本, 带 CMD窗口
```cmd
chcp 65001 
java --server.port=8080 -Dfile.encoding=UTF-8 -Dloader.path=lib -jar C:\AVENSEN\apps\server\PX211-Server-1.0.73.jar
```

# 2. springboot 启动脚本, 不带CMD
```cmd
@echo off
start javaw -Dloader.path=lib -jar C:\AVENSEN\apps\server\PX211-Server-1.0.73.jar
exit
```

# 3.springboot停止脚本
```cmd
@echo off
setlocal enabledelayedexpansion
for /f "eol=* tokens=*" %%i in ('netstat -an -o ^| findstr "9001"') do (
set a=%%i
set a=!a:~69,10!
echo !a!
taskkill /F /PID !a!
)
```