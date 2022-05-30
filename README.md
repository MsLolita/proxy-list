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

# [SAMPLE PROXIES] - [May 30 2022 | 10:30:47]

### Proxy Statistics:
- _Online Proxies (By Protocol):_
   - **SOCKS4** -> 3498
   - **SOCKS5** -> 583
   - **HTTP** -> 2182
   - **HTTPS** -> 2002

- _Proxies (Total):_
   - **Online Proxies (SOCKS4/5 + HTTP/S)** -> 5564
   - **Unique Online Proxies** -> 5564
   - **Unique Online/Offline Proxies (Archive)** -> 11512

## [SOCKS4 (3498/5564)](https://raw.githubusercontent.com/jetkai/proxy-list/main/online-proxies/txt/proxies-socks4.txt)
```yaml
1.0.133.89:4153
1.0.133.100:51327
1.9.167.35:60489
1.9.213.114:4153
1.10.140.43:4145
1.10.141.220:54620
1.20.96.30:4153
1.20.96.164:4153
1.20.184.75:4153
1.20.227.66:4145
1.32.57.85:5678
1.32.59.217:47045
1.34.179.119:5678
1.53.137.84:4145
1.55.241.4:4145
1.179.147.5:52210
1.179.148.9:36476
1.186.85.74:5678
1.186.139.9:39651
1.212.157.115:4145
1.220.145.45:4145
1.221.173.148:4145
1.255.226.232:26680
2.139.162.80:4145
2.197.124.172:4153
3.120.173.144:8080
3.131.207.170:13343
3.141.13.98:5678
3.211.17.212:80
4.14.120.234:39593
```

## [SOCKS5 (583/5564)](https://raw.githubusercontent.com/jetkai/proxy-list/main/online-proxies/txt/proxies-socks5.txt)
```yaml
1.180.0.162:7302
1.255.226.232:26680
3.19.179.179:8000
3.120.173.144:8080
3.131.207.170:13343
3.211.17.212:80
5.161.86.206:1080
5.161.93.53:1080
5.161.100.145:1080
5.188.108.243:31535
5.189.170.180:5566
5.189.186.24:5566
5.189.229.42:1080
5.253.145.247:1080
8.136.192.43:80
8.209.220.34:80
8.218.69.97:8000
12.151.56.30:80
13.59.58.111:1080
13.233.84.6:39998
14.23.62.59:7300
14.149.69.217:7300
18.136.106.96:8081
18.162.51.223:8090
18.189.228.38:8000
18.206.33.119:8888
20.222.136.61:8000
20.230.193.232:80
20.239.2.157:80
23.94.30.107:1088
```

## [HTTP (2182/5564)](https://raw.githubusercontent.com/jetkai/proxy-list/main/online-proxies/txt/proxies-http.txt)
```yaml
1.0.170.50:80
1.1.220.100:8080
1.2.252.65:8080
1.10.141.220:54620
1.32.59.217:47045
1.179.136.98:8080
1.179.148.9:36476
1.186.85.38:1111
2.184.4.66:6565
2.188.164.194:8080
3.19.179.179:8000
3.20.236.208:49205
3.128.120.252:80
3.215.177.148:49205
5.16.1.17:8080
5.35.82.110:32132
5.44.62.166:8080
5.59.136.230:8080
5.104.174.199:23500
5.131.243.252:8080
5.135.176.161:10000
5.160.91.130:3128
5.167.141.239:3128
5.189.170.180:5566
5.189.186.24:5566
5.189.229.42:1080
5.202.191.226:80
8.208.91.118:8888
8.218.213.95:10809
8.242.212.170:999
```

## [HTTPS (2002/5564)](https://raw.githubusercontent.com/jetkai/proxy-list/main/online-proxies/txt/proxies-https.txt)
```yaml
1.0.170.50:80
1.1.220.100:8080
1.2.252.65:8080
1.10.141.220:54620
1.32.59.217:47045
1.179.136.98:8080
1.179.148.9:36476
1.186.85.38:1111
2.184.4.66:6565
2.188.164.194:8080
3.19.179.179:8000
3.20.236.208:49205
3.128.120.252:80
3.215.177.148:49205
5.16.1.17:8080
5.35.82.110:32132
5.44.62.166:8080
5.59.136.230:8080
5.104.174.199:23500
5.131.243.252:8080
5.135.176.161:10000
5.160.91.130:3128
5.167.141.239:3128
5.189.170.180:5566
5.189.186.24:5566
5.189.229.42:1080
5.202.191.226:80
8.208.91.118:8888
8.218.213.95:10809
12.31.246.5:8080
```

## [ARCHIVE (5564/11512)](https://raw.githubusercontent.com/jetkai/proxy-list/main/archive/txt/working-proxies-history.txt)
```yaml
1.0.132.249:4153
1.0.133.89:4153
1.0.133.100:51327
1.0.137.61:4153
1.0.170.50:80
1.0.205.87:8080
1.1.189.58:8080
1.1.220.100:8080
1.2.252.65:8080
1.4.214.148:5678
1.9.167.35:60489
1.9.167.36:60489
1.9.213.114:4153
1.10.133.211:4145
1.10.140.43:4145
1.10.141.220:54620
1.20.95.95:5678
1.20.96.30:4153
1.20.96.164:4153
1.20.137.82:32241
1.20.166.142:8080
1.20.184.75:4153
1.20.209.28:8080
1.20.217.52:8080
1.20.220.79:4145
1.20.227.66:4145
1.32.57.85:5678
1.32.59.217:47045
1.34.179.119:5678
1.53.137.84:4145
```



Thx Co Pure Gs - Sort Meister! 💟