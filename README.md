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

# [SAMPLE PROXIES] - [May 20 2022 | 09:29:03]

### Proxy Statistics:
- _Online Proxies (By Protocol):_
   - **SOCKS4** -> 1708
   - **SOCKS5** -> 172
   - **HTTP** -> 825
   - **HTTPS** -> 739

- _Proxies (Total):_
   - **Online Proxies (SOCKS4/5 + HTTP/S)** -> 3444
   - **Unique Online Proxies** -> 3149
   - **Unique Online/Offline Proxies (Archive)** -> 21809

## [SOCKS4 (1708/3149)](https://raw.githubusercontent.com/jetkai/proxy-list/main/online-proxies/txt/proxies-socks4.txt)
```yaml
1.0.136.172:4145
1.4.214.148:5678
1.9.213.114:4153
1.20.220.79:4145
1.32.57.85:5678
1.32.59.217:31981
1.179.147.5:52210
1.179.148.9:36476
1.179.186.71:1080
1.186.40.157:39651
1.186.40.177:39651
2.57.8.76:4153
2.139.162.80:4145
3.141.13.98:5678
4.14.120.234:39593
5.1.104.66:33041
5.8.240.94:4153
5.17.90.170:5678
5.22.154.50:32127
5.58.53.216:1085
5.58.66.55:14888
5.135.83.96:1000
5.160.81.157:4145
5.178.217.227:31019
5.180.100.24:5678
5.181.248.202:5678
5.189.229.42:1080
5.201.178.102:5678
5.226.125.10:10801
8.17.28.139:39593
```

## [SOCKS5 (172/3149)](https://raw.githubusercontent.com/jetkai/proxy-list/main/online-proxies/txt/proxies-socks5.txt)
```yaml
1.13.165.87:1080
1.71.170.146:7302
5.161.100.145:1080
5.189.229.42:1080
13.233.84.6:9999
18.136.106.96:8081
24.249.199.4:4145
24.249.199.12:4145
31.128.248.1:1080
31.184.220.67:1080
36.89.86.49:56845
43.135.74.226:38081
43.224.10.8:6667
43.224.10.26:6667
43.224.10.31:6667
43.224.10.37:6667
43.224.10.46:6667
43.251.116.59:8888
45.10.69.98:8888
46.101.5.73:45775
46.101.5.73:46999
46.101.5.73:47521
46.101.5.73:48334
46.101.5.73:48528
46.147.194.197:1080
50.63.165.21:23859
51.75.195.157:37606
51.155.3.184:33427
58.22.60.174:1080
59.98.82.114:1080
```

## [HTTP (825/3149)](https://raw.githubusercontent.com/jetkai/proxy-list/main/online-proxies/txt/proxies-http.txt)
```yaml
1.20.166.142:8080
1.179.144.41:8080
1.186.40.35:1111
1.186.85.114:1111
2.188.164.194:8080
3.20.236.208:49205
3.215.177.148:49205
5.16.1.17:8080
5.53.16.185:18080
5.61.38.247:3128
5.139.188.112:55443
5.167.141.239:3128
12.218.209.130:53281
14.157.114.20:7890
14.170.154.193:19132
14.192.2.161:84
14.207.145.80:9080
18.216.72.10:49205
18.222.17.49:49205
24.72.171.214:8080
27.72.149.205:8080
27.116.51.119:6666
27.123.4.106:8181
27.131.179.206:10443
27.255.58.74:8080
31.129.166.5:8080
31.131.67.14:8080
31.161.38.233:8090
31.171.154.199:8118
31.220.183.217:53281
```

## [HTTPS (739/3149)](https://raw.githubusercontent.com/jetkai/proxy-list/main/online-proxies/txt/proxies-https.txt)
```yaml
1.1.189.58:8080
1.179.148.9:55636
1.186.85.2:1111
3.19.179.179:8000
3.20.236.208:49205
3.215.177.148:49205
5.16.0.77:1256
5.16.1.17:8080
5.53.16.185:18080
5.104.174.199:23500
5.131.243.252:8080
5.167.141.239:3128
5.189.229.42:1081
5.202.191.226:80
5.202.191.226:8080
8.218.213.95:10809
14.20.235.19:45770
14.170.154.10:8080
14.170.154.193:19132
14.241.39.165:19132
18.216.72.10:49205
18.222.17.49:49205
31.14.124.3:8080
31.161.38.233:8090
31.171.154.199:8118
34.101.127.131:8080
34.229.130.62:49205
34.230.89.25:49205
36.37.86.27:9812
36.37.91.98:9812
```

## [ARCHIVE (3149/21809)](https://raw.githubusercontent.com/jetkai/proxy-list/main/archive/txt/working-proxies-history.txt)
```yaml
1.0.132.249:4153
1.0.133.89:4153
1.0.133.100:51327
1.0.136.168:4145
1.0.136.172:4145
1.0.136.197:4145
1.0.136.217:4145
1.0.137.61:4153
1.0.148.135:4145
1.0.149.73:4145
1.0.151.157:4145
1.0.152.183:4145
1.0.154.38:4145
1.0.154.166:4145
1.0.159.150:4145
1.0.160.238:4145
1.0.161.25:4145
1.0.161.232:4145
1.0.170.50:8080
1.0.170.50:80
1.0.205.87:8080
1.0.208.93:4145
1.0.213.104:4145
1.0.224.88:4145
1.0.232.127:4145
1.1.161.243:4145
1.1.169.159:4145
1.1.189.58:8080
1.1.220.100:8080
1.1.228.123:4145
```



Thx Co Pure Gs - Sort Meister! 💟