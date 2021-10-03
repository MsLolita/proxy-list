<!-- MARKDOWN LINKS & IMAGES -->
<!-- https://www.markdownguide.org/basic-syntax/#reference-style-links -->
[contributors-shield]: https://img.shields.io/github/contributors/jetkai/proxy-list?style=flat&logo=github
[contributors-url]: https://github.com/jetkai/proxy-list/graphs/contributors
[forks-shield]: https://img.shields.io/github/forks/jetkai/proxy-list?style=flat&logo=github
[forks-url]: https://github.com/jetkai/proxy-list/network/members
[stars-shield]: https://img.shields.io/github/stars/jetkai/proxy-list?style=flat&logo=github
[stars-url]: https://github.com/jetkai/proxy-list/stargazers
[issues-shield]: https://img.shields.io/github/issues/jetkai/proxy-list?style=flat&logo=github
[issues-url]: https://github.com/jetkai/proxy-list/issues
[license-shield]: https://img.shields.io/github/license/jetkai/proxy-list?style=flat&logo=github
[license-url]: https://github.com/jetkai/proxy-list/blob/main/LICENSE
[commit-shield]: https://img.shields.io/github/last-commit/jetkai/proxy-list?style=flat&logo=github
[commit-url]: https://github.com/jetkai/proxy-list/commits/main
[commit-activity]: https://img.shields.io/github/commit-activity/w/jetkai/proxy-list?style=flat&logo=github
[commit-activity-url]: https://github.com/jetkai/proxy-list/commits/main

# 🎁 SOCKS4/5 & HTTP/S PROXIES // ONLINE & READY

[![Commits][commit-shield]][commit-url]
[![Commits][commit-activity]][commit-activity-url]
[![Stargazers][stars-shield]][stars-url]
[![Forks][forks-shield]][forks-url]
[![Issues][issues-shield]][issues-url]

## 📰About This Project & The Proxies:
This repository contains a free list of tested SOCKS4/5 & HTTP/S proxies in -> **JSON**, **TXT** & **CSV** format. No authentication is required when connecting to these proxies.

## 👩‍💻Proxy Testing:

These proxies are tested ~12x/day (every 2 hours) against EU/US hosting providers - **see below**, they have been verified to write & read data <**AT THE TIME OF TESTING**>.

**Hosting Provider**|**Country**|**Continent**
:-----:|:-----:|:-----:
OVH|France|EU
Amazon Web Services|United States|NA
Oracle Cloud|United Kingdom|EU
Microsoft Azure|Hong Kong|AS

[Source Code](https://github.com/jetkai/ProxyBuilder/blob/main/src/main/kotlin/spb/net/proxy/ProxyTester.kt)
```kotlin
    //SOCKS example (HTTP/S) is also supported
    private fun useSocksProxy(serverAddress: String?, serverPort: Int): ClientSocket? {
        val proxy = Proxy(Proxy.Type.SOCKS, InetSocketAddress(proxyAddress, proxyPort))
        val socket = Socket(proxy)
        if(socks4)
            forceSocks4(socket)
        try {
            socket.soTimeout = Constants.CONNECTION_TIMEOUT //3000ms
            socket.tcpNoDelay = true
            socket.connect(InetSocketAddress(serverAddress, serverPort), Constants.CONNECTION_TIMEOUT)
        } catch (e : IOException) {
            socket.close()
        }
        if(socket.isClosed)
            return null
        return ClientSocket().init(socket) //Read/Write Data Function
    }
```

## 📝Proxy Formatting:

These proxies are scraped from various sources & I compile this data using my [ProxyBuilder](https://github.com/jetkai/ProxyBuilder) application. Proxies are sorted from lowest to highest 0-255 & duplicated proxies are removed — the only exception is if an IP has a different port open, which is also a working proxy tunnel <**Less than 1% of the total proxies at the time of testing**>.

```IP:Port -> 1.0.132.249:4153```

## ✔Compatability:

Proxies work for any application that can establish a socket connection, such as... An application that has proxy support (FireFox, Chrome), or as an example, these Java Apps -> [JaySyiPker](https://github.com/JayArrowz/JaySyiPker), [Bruteforce-RSPS](https://github.com/jetkai/Bruteforce-RSPS) & [718 Cheat Client (Final)](https://github.com/jetkai/718-Cheat-Client-Final).

## 🔗ProxyList Links (Direct URL):

- _Online Proxies:_
    - **JSON** -> [proxies.json](https://raw.githubusercontent.com/jetkai/proxy-list/main/online-proxies/json/proxies.json)
    - **TXT** -> [proxies.txt](https://raw.githubusercontent.com/jetkai/proxy-list/main/online-proxies/txt/proxies.txt)
    - **CSV** -> [proxies.csv](https://raw.githubusercontent.com/jetkai/proxy-list/main/online-proxies/csv/proxies.csv)
- _Online/Offline Proxies (Archive):_
  - **JSON** -> [working-proxies-history.json](https://raw.githubusercontent.com/jetkai/proxy-list/main/archive/json/working-proxies-history.json)
  - **TXT** -> [working-proxies-history.txt](https://raw.githubusercontent.com/jetkai/proxy-list/main/archive/txt/working-proxies-history.txt)
  - **CSV** -> [working-proxies-history.csv](https://raw.githubusercontent.com/jetkai/proxy-list/main/archive/csv/working-proxies-history.csv)

## 🌍Geolocation & Graphs (Weekly):
Analytics are updated on a weekly basis and contains raw data, tables & graphs. 

You can view/download this data below.

**Query**|**Result**
:-----:|:-----:
Most Proxies By Country|Brazil (6719)
Most Detected Proxies By Country|Brazil (4652)
Most Proxies By Provider|Bharat Sanchar Nigam Ltd (2449)
Most Proxies By Port|5678 (33610)
Most Proxies By Protocol|SOCKS4 (43928)
Most Proxies By Continent|Asia (27600)

**Name**|**Link**
:-----:|:-----:
Graphs, Tables & Data (Excel) | [(analysis.xlsx)](https://raw.githubusercontent.com/jetkai/proxy-list/main/archive/csv/working-proxies-history.csv)
Raw Data (JSON) | [(archive-geo.json)](https://raw.githubusercontent.com/jetkai/proxy-list/main/archive/json/working-proxies-history-geo-beautify.json)
Raw Data (CSV) | [(archive-geo.csv)](https://raw.githubusercontent.com/jetkai/proxy-list/main/archive/csv/working-proxies-history-geo.csv)

![image](https://user-images.githubusercontent.com/26250917/135737945-c275ad3d-e086-4d3c-b593-a9096362e673.png)


## Next Updates:

Further updates will be made to this project throughout the year, the next update I am working on will keep a record of proxy up-time, location, isp & speed.

---

# [SAMPLE PROXIES] - [October 03 2021 | 05:29:03]

### Proxy Statistics:
- _Online Proxies (By Protocol):_
   - **SOCKS4** -> 4459
   - **SOCKS5** -> 286
   - **HTTP** -> 1956
   - **HTTPS** -> 2681

- _Proxies (Total):_
   - **Online Proxies (SOCKS4/5 + HTTP/S)** -> 9382
   - **Unique Online Proxies** -> 8135
   - **Unique Online/Offline Proxies (Archive)** -> 57382

## [SOCKS4 (4459/8135)](https://raw.githubusercontent.com/jetkai/proxy-list/main/online-proxies/txt/proxies-socks4.txt)
```yaml
1.0.132.249:4153
1.0.133.100:51327
1.0.136.183:4145
1.0.152.157:4145
1.1.154.73:4145
1.1.161.198:4145
1.4.157.35:36202
1.4.214.148:5678
1.9.71.4:4153
1.9.167.36:60489
1.9.213.114:4153
1.10.141.220:37718
1.20.99.41:5678
1.20.168.157:4145
1.20.184.75:4153
1.20.203.220:4145
1.20.207.200:4145
1.20.220.79:4145
1.32.59.217:31981
1.179.147.5:52210
1.179.148.9:36476
1.179.172.45:31225
1.179.181.213:30500
1.179.183.73:61468
1.186.46.36:5678
1.186.82.4:5678
1.212.181.131:4145
1.221.173.148:4145
2.62.150.112:1080
3.141.13.98:5678
```

## [SOCKS5 (286/8135)](https://raw.githubusercontent.com/jetkai/proxy-list/main/online-proxies/txt/proxies-socks5.txt)
```yaml
1.116.4.222:7890
5.61.53.57:9502
5.61.53.57:9053
5.105.0.135:16379
5.105.1.86:16379
5.164.23.101:1080
8.210.163.246:50028
8.210.251.244:24691
8.214.2.182:7890
13.250.172.147:48540
24.249.199.4:4145
24.249.199.12:4145
27.22.85.58:8100
27.116.51.85:6667
27.116.51.181:6667
31.7.232.178:1080
36.27.223.70:64312
36.89.86.49:56845
36.94.126.50:1080
37.156.104.178:3327
37.187.72.30:57257
39.105.134.60:10705
43.132.157.62:2120
43.224.10.8:6667
43.224.10.11:6667
43.224.10.26:6667
43.224.10.27:6667
43.224.10.30:6667
43.224.10.31:6667
43.224.10.37:6667
```

## [HTTP (1956/8135)](https://raw.githubusercontent.com/jetkai/proxy-list/main/online-proxies/txt/proxies-http.txt)
```yaml
1.1.189.58:8080
1.10.188.78:45208
1.15.182.239:7890
1.116.4.222:7890
1.179.144.41:8080
2.188.166.25:3128
2.188.166.26:3128
3.82.92.51:49205
3.83.243.92:49205
5.11.17.105:8090
5.16.0.97:1256
5.16.0.174:8080
5.16.0.180:8080
5.16.0.186:8080
5.20.91.12:60792
5.26.96.212:8080
5.34.153.142:8080
5.59.136.230:8080
5.141.244.28:8080
5.149.219.201:8080
8.129.10.162:3228
8.208.91.118:8888
8.208.91.118:8000
8.208.91.118:3128
8.208.91.118:81
8.214.2.182:7890
14.160.26.153:8080
14.161.10.191:8080
18.220.20.81:8080
24.113.42.177:48678
```

## [HTTPS (2681/8135)](https://raw.githubusercontent.com/jetkai/proxy-list/main/online-proxies/txt/proxies-https.txt)
```yaml
1.0.205.87:8080
1.1.189.58:8080
1.4.157.35:46944
1.15.182.239:7890
1.20.166.142:8080
1.20.207.200:8080
1.20.217.52:8080
1.32.44.17:8080
1.71.132.216:6969
1.71.133.202:6969
1.71.143.122:6969
1.116.4.222:7890
1.116.12.21:3228
1.116.155.200:7788
1.179.144.41:8080
1.179.183.73:50178
2.59.76.233:53281
2.179.193.146:80
2.188.166.22:3128
2.188.166.26:3128
3.17.148.147:49205
3.20.236.208:49205
3.82.92.51:49205
3.82.128.23:49205
3.82.186.15:49205
3.84.17.68:49205
3.86.23.10:49205
3.86.147.133:49205
3.92.48.99:49205
3.95.161.236:49205
```

## [ARCHIVE (8135/57382)](https://raw.githubusercontent.com/jetkai/proxy-list/main/archive/txt/working-proxies-history.txt)
```yaml
1.0.132.249:4153
1.0.133.89:4153
1.0.133.100:51327
1.0.136.51:4145
1.0.136.115:4145
1.0.136.183:4145
1.0.137.117:5678
1.0.144.14:5678
1.0.152.157:4145
1.0.160.160:4145
1.0.202.54:5678
1.0.205.87:8080
1.0.209.45:4145
1.0.212.209:4145
1.0.213.150:5678
1.0.215.76:5678
1.0.215.239:5678
1.0.225.117:5678
1.0.251.164:4145
1.1.154.73:4145
1.1.160.205:4145
1.1.161.198:4145
1.1.185.208:4145
1.1.189.58:8080
1.1.220.100:8080
1.1.224.68:5678
1.1.225.97:5678
1.1.226.87:5678
1.1.226.224:5678
1.1.227.33:5678
```



Thx Co Pure Gs - Sort Meister! 💟
