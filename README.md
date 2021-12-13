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
This repository contains a free list of tested SOCKS4/5 & HTTP/S proxies in -> **JSON**, **TXT**, **CSV**, **XML** & **YAML** format. No authentication is required when connecting to these proxies.

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
    - **XML** -> [proxies.xml](https://raw.githubusercontent.com/jetkai/proxy-list/main/online-proxies/xml/proxies.xml)
    - **YAML** -> [proxies.yaml](https://raw.githubusercontent.com/jetkai/proxy-list/main/online-proxies/yaml/proxies.yaml)
- _Online/Offline Proxies (Archive):_
  - **JSON** -> [working-proxies-history.json](https://raw.githubusercontent.com/jetkai/proxy-list/main/archive/json/working-proxies-history.json)
  - **TXT** -> [working-proxies-history.txt](https://raw.githubusercontent.com/jetkai/proxy-list/main/archive/txt/working-proxies-history.txt)
  - **CSV** -> [working-proxies-history.csv](https://raw.githubusercontent.com/jetkai/proxy-list/main/archive/csv/working-proxies-history.csv)
  - **XML** -> [working-proxies-history.xml](https://raw.githubusercontent.com/jetkai/proxy-list/main/archive/xml/working-proxies-history.xml)
  - **YAML** -> [working-proxies-history.yaml](https://raw.githubusercontent.com/jetkai/proxy-list/main/archive/yaml/working-proxies-history.yaml)

## 🌍Geolocation & Graphs (Weekly):
Analytics are updated on a weekly basis and contains raw data, tables & graphs. 

You can view/download this data below.

**Query**|**Result**
:-----:|:-----:
Most Proxies By Country|Brazil (6749)
Most Detected Proxies By Country|Brazil (4680)
Most Proxies By Provider|Bharat Sanchar Nigam Ltd (2455)
Most Proxies By Port|5678 (33668)
Most Proxies By Protocol|SOCKS4 (44037)
Most Proxies By Continent|Asia (27864)

**Data Type**|**Link**
:-----:|:-----:
Graphs, Tables & Data (Excel) | [(analysis.xlsx)](https://raw.githubusercontent.com/jetkai/proxy-list/main/archive/xlsx/analysis.xlsx)
Raw Data (JSON) | [(archive-geo.json)](https://raw.githubusercontent.com/jetkai/proxy-list/main/archive/json/working-proxies-history-geo-beautify.json)
Raw Data (CSV) | [(archive-geo.csv)](https://raw.githubusercontent.com/jetkai/proxy-list/main/archive/csv/working-proxies-history-geo.csv)
Raw Data (XML) | [(archive-geo.xml)](https://raw.githubusercontent.com/jetkai/proxy-list/main/archive/xml/working-proxies-history-geo.xml)
Raw Data (YAML) | [(archive-geo.yaml)](https://raw.githubusercontent.com/jetkai/proxy-list/main/archive/yaml/working-proxies-history-geo.yaml)

![image](https://user-images.githubusercontent.com/26250917/135766207-17d4c531-2738-4209-808e-82c04b871331.png)


## Next Updates:

Further updates will be made to this project throughout the year, the next update I am working on will keep a record of proxy up-time, location, isp & speed.

---

# [SAMPLE PROXIES] - [December 13 2021 | 07:29:04]

### Proxy Statistics:
- _Online Proxies (By Protocol):_
   - **SOCKS4** -> 4595
   - **SOCKS5** -> 326
   - **HTTP** -> 1688
   - **HTTPS** -> 1418

- _Proxies (Total):_
   - **Online Proxies (SOCKS4/5 + HTTP/S)** -> 8027
   - **Unique Online Proxies** -> 7226
   - **Unique Online/Offline Proxies (Archive)** -> 37251

## [SOCKS4 (4595/7226)](https://raw.githubusercontent.com/jetkai/proxy-list/main/online-proxies/txt/proxies-socks4.txt)
```yaml
1.0.132.249:4153
1.0.162.181:4145
1.2.187.111:4145
1.2.208.183:4145
1.4.214.148:5678
1.9.27.217:4153
1.9.71.4:4153
1.9.167.35:60489
1.9.167.36:60489
1.9.213.114:4153
1.10.141.220:37718
1.10.189.133:50855
1.20.95.95:5678
1.20.96.30:4153
1.20.184.75:4153
1.20.198.8:4153
1.20.198.9:4153
1.20.198.10:4153
1.20.220.79:4145
1.20.227.66:4145
1.20.235.153:5678
1.32.57.85:5678
1.32.59.217:31981
1.53.137.84:4145
1.53.137.164:4145
1.179.145.101:33109
1.179.147.5:52210
1.179.148.9:36476
1.179.172.45:31225
1.179.173.114:4153
```

## [SOCKS5 (326/7226)](https://raw.githubusercontent.com/jetkai/proxy-list/main/online-proxies/txt/proxies-socks5.txt)
```yaml
3.80.95.152:3129
3.88.156.18:3129
3.234.216.105:1080
5.42.158.11:1080
5.42.158.106:1080
5.42.158.107:1080
5.42.158.108:1080
5.42.158.111:10800
5.42.158.111:1080
5.42.158.114:10800
5.42.158.114:1080
5.42.158.115:1080
5.42.158.115:10800
5.42.158.116:10800
5.42.158.116:1080
5.42.158.119:1080
5.42.158.121:10800
5.42.158.123:10800
5.42.158.124:10800
5.42.158.125:1080
5.42.158.125:10800
5.42.158.126:10800
5.56.134.237:45698
5.164.23.101:1080
14.23.124.132:1080
18.215.156.218:3129
20.203.224.112:1080
20.205.204.111:6666
23.94.149.131:53335
24.249.199.4:4145
```

## [HTTP (1688/7226)](https://raw.githubusercontent.com/jetkai/proxy-list/main/online-proxies/txt/proxies-http.txt)
```yaml
1.0.170.50:8080
1.15.182.239:7890
1.179.136.98:8080
1.179.148.9:55636
2.188.166.22:3128
3.94.93.17:49205
5.16.0.174:8080
5.16.0.180:8080
5.16.0.186:8080
5.20.91.12:60792
5.23.103.44:8080
5.23.103.45:8080
5.23.103.46:8080
5.34.153.142:8080
5.44.54.106:8080
5.56.134.237:55963
5.149.219.201:8080
5.160.85.155:3128
5.160.101.165:3128
5.183.234.1:8080
8.208.91.118:80
8.208.91.118:8000
8.208.91.118:3128
8.208.91.118:8800
8.242.144.67:999
12.90.37.182:8181
14.102.13.193:8080
14.102.44.25:44047
14.160.32.23:8080
14.161.252.185:55443
```

## [HTTPS (1418/7226)](https://raw.githubusercontent.com/jetkai/proxy-list/main/online-proxies/txt/proxies-https.txt)
```yaml
1.0.205.87:8080
1.2.252.65:8080
1.10.141.220:54620
1.20.166.142:8080
1.20.217.221:8080
1.179.136.98:8080
2.184.4.68:6565
2.188.166.22:3128
3.94.93.17:49205
5.16.0.174:8080
5.16.0.180:8080
5.16.0.186:8080
5.23.103.46:8080
5.45.106.24:8118
5.58.33.187:55507
5.141.82.95:81
5.149.219.201:8080
5.160.85.155:3128
5.164.214.23:8080
5.183.234.1:8080
8.208.91.118:8008
12.218.209.130:53281
14.102.13.193:8080
14.161.252.185:55443
14.177.235.17:8080
14.177.236.212:55443
14.192.2.161:83
14.192.3.161:83
14.241.39.191:8080
18.191.253.100:49205
```

## [ARCHIVE (7226/37251)](https://raw.githubusercontent.com/jetkai/proxy-list/main/archive/txt/working-proxies-history.txt)
```yaml
1.0.132.249:4153
1.0.133.89:4153
1.0.133.100:51327
1.0.136.168:4145
1.0.136.201:4145
1.0.141.90:4145
1.0.145.246:4145
1.0.147.198:4145
1.0.148.132:4145
1.0.152.157:4145
1.0.154.141:4145
1.0.161.151:4153
1.0.162.24:4145
1.0.162.181:4145
1.0.163.17:4145
1.0.163.85:4145
1.0.163.172:8081
1.0.170.50:8080
1.0.170.50:80
1.0.173.104:4145
1.0.174.87:4145
1.0.205.87:8080
1.0.213.133:8080
1.0.220.169:4153
1.0.226.138:4145
1.0.228.243:5678
1.0.229.154:5678
1.0.239.61:5678
1.0.239.174:4145
1.0.243.247:4145
```



Thx Co Pure Gs - Sort Meister! 💟