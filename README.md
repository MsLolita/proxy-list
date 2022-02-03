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

# [SAMPLE PROXIES] - [February 03 2022 | 05:29:04]

### Proxy Statistics:
- _Online Proxies (By Protocol):_
   - **SOCKS4** -> 3427
   - **SOCKS5** -> 984
   - **HTTP** -> 1988
   - **HTTPS** -> 1700

- _Proxies (Total):_
   - **Online Proxies (SOCKS4/5 + HTTP/S)** -> 8099
   - **Unique Online Proxies** -> 7053
   - **Unique Online/Offline Proxies (Archive)** -> 49445

## [SOCKS4 (3427/7053)](https://raw.githubusercontent.com/jetkai/proxy-list/main/online-proxies/txt/proxies-socks4.txt)
```yaml
1.0.133.100:51327
1.1.163.30:4145
1.4.214.148:5678
1.9.27.217:4153
1.9.164.242:35471
1.14.104.55:49915
1.20.96.30:4153
1.20.96.164:4153
1.20.137.82:32241
1.20.198.9:4153
1.20.220.79:4145
1.20.235.153:5678
1.32.57.85:5678
1.32.59.217:31981
1.53.137.164:4145
1.55.241.4:4145
1.83.154.35:4145
1.179.130.201:4153
1.179.148.9:36476
1.179.186.68:1080
1.179.202.33:5678
1.186.40.2:39651
1.212.157.115:4145
2.135.223.134:5678
2.136.195.109:5678
2.179.167.29:9969
2.183.8.145:4153
3.141.13.98:5678
3.144.165.41:5555
4.14.120.234:39593
```

## [SOCKS5 (984/7053)](https://raw.githubusercontent.com/jetkai/proxy-list/main/online-proxies/txt/proxies-socks5.txt)
```yaml
1.14.104.55:49915
1.71.170.146:7302
1.180.0.162:7302
1.196.217.57:7302
3.8.234.250:14542
3.113.19.41:48540
3.144.99.13:38800
5.11.17.230:1080
5.58.178.99:7777
5.128.61.28:1080
5.183.101.101:14999
5.183.101.106:14999
5.183.103.132:14999
5.253.235.194:14999
8.129.8.2:9999
8.210.48.101:18118
13.231.137.2:48540
14.136.204.35:1088
14.231.171.214:5009
20.94.179.174:1080
23.94.73.246:1080
23.94.149.131:53335
23.224.46.169:51615
23.234.213.157:6666
24.103.162.189:31337
24.249.199.4:4145
27.116.51.85:6667
27.116.51.186:6667
27.156.80.73:16790
31.22.7.188:50260
```

## [HTTP (1988/7053)](https://raw.githubusercontent.com/jetkai/proxy-list/main/online-proxies/txt/proxies-http.txt)
```yaml
1.0.205.87:8080
1.1.189.58:8080
1.4.198.67:8081
1.13.165.87:8080
1.15.182.239:7890
1.32.59.217:47045
1.117.231.98:8080
1.179.136.98:8080
1.180.156.226:65001
1.186.40.35:1111
2.136.185.208:4128
2.179.193.146:80
3.20.236.208:49205
3.110.81.200:8888
3.215.177.148:49205
3.250.42.250:3128
5.9.103.181:8088
5.16.0.77:1256
5.16.7.213:1256
5.20.91.12:60792
5.34.153.142:8080
5.131.243.252:8080
5.133.24.132:8080
5.134.221.222:8080
5.153.234.91:3128
5.160.91.130:3128
5.160.101.165:3128
5.183.101.106:14999
5.183.103.132:14999
5.188.136.52:8080
```

## [HTTPS (1700/7053)](https://raw.githubusercontent.com/jetkai/proxy-list/main/online-proxies/txt/proxies-https.txt)
```yaml
1.0.170.50:80
1.2.252.65:8080
1.4.198.67:8081
1.10.141.220:54620
1.13.165.87:8080
1.20.217.221:8080
1.32.59.217:47045
1.179.136.98:8080
1.179.148.9:55636
1.180.156.226:65001
1.186.40.35:1111
1.186.245.226:80
2.137.212.62:8080
2.179.193.146:80
2.184.4.68:6565
2.188.166.25:3128
3.20.236.208:49205
3.215.177.148:49205
5.9.112.247:3128
5.16.0.49:8080
5.16.0.174:8080
5.20.91.12:60792
5.34.153.142:8080
5.58.178.99:41890
5.59.136.230:8080
5.131.243.11:8080
5.131.243.252:8080
5.141.244.97:61288
5.153.234.91:3128
5.160.101.170:3128
```

## [ARCHIVE (7053/49445)](https://raw.githubusercontent.com/jetkai/proxy-list/main/archive/txt/working-proxies-history.txt)
```yaml
1.0.132.249:4153
1.0.133.89:4153
1.0.133.100:51327
1.0.136.42:4145
1.0.136.161:4145
1.0.136.168:4145
1.0.136.201:4145
1.0.136.222:4145
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
1.0.191.138:4153
1.0.205.87:8080
1.0.209.187:8080
1.0.213.133:8080
1.0.220.169:4153
1.0.226.138:4145
```



Thx Co Pure Gs - Sort Meister! 💟