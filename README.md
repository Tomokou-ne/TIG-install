# TIG-install

How to install InfluxDB v1.8.10 + Telegraf + Grafana manual for Windows 10

!! Make sure you created ports 8086, 8080 & 3000 in your system !! [Tutorial](https://www.databasemart.com/kb/open-port-in-windows-firewall)

---
# InfluxDB v1.8.10 using PowerShell

1. Install Chocolay 

``` Set-ExecutionPolicy Bypass -Scope Process -Force; iwr https://community.chocolatey.org/install.ps1 -UseBasicParsing | iex ```

2. Using link (https://community.chocolatey.org/packages/influxdb1) install InfluxDB

``` choco install influxdb1 ```

3. Move to your folder with InfluxDB (here's my example)

``` cd "C:\Program Files\InfluxData\" ``` 

4. Open first influxd.exe, then repeat step 3 another PowerShell window and open influx.exe

``` .\influxd.exe ```
``` .\influx.exe ```

You shold see, how program is working.

5. Create user for Telegraf in influx.exe PowerShell window, also create database for Telegraf metrics

``` CREATE USER telegraf WITH PASSWORD 'password' WITH ALL PRIVILEGES ```
``` CREATE DATABASE telegraf ```

---
# Telegraf 

1. Go to InfluxDB official cite and download the latest version in .zip

2. Extract zip file in C:\Program Files\Telegraf

3. Make telegraf.conf file to yur preferences, or just download mine :)
   In here you can build telegraf by yourself, just visit official web cite if you'd like to

   You can make sure if your conf file is working by writing in PowerShell
``` cd "C:\Program Files\Telegraf\" ```
``` .\telegraf.exe -config .\telegraf.conf -test ``` 

5. Run Telegraf in PowerShell
   
``` cd "C:\Program Files\Telegraf\" ``` 
``` .\telegraf.exe ``` 

---
# Grafana

1. Download instalation file from official cite

2. Extract zip file

3. Run Grafana simply clicking to grafana.exe

4. Open your browser and write

``` localhost:3000 ```

5. Authorise using 'admin' 'admin'

6. Start using your Grafana by creating new dashboard and adding all parameters from telegraf.cong file
  

8. 
