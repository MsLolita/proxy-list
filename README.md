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

# [SAMPLE PROXIES] - [March 15 2022 | 11:29:03]

### Proxy Statistics:
- _Online Proxies (By Protocol):_
   - **SOCKS4** -> 581
   - **SOCKS5** -> 168
   - **HTTP** -> 741
   - **HTTPS** -> 696

- _Proxies (Total):_
   - **Online Proxies (SOCKS4/5 + HTTP/S)** -> 2186
   - **Unique Online Proxies** -> 1985
   - **Unique Online/Offline Proxies (Archive)** -> 57616

## [SOCKS4 (581/1985)](https://raw.githubusercontent.com/jetkai/proxy-list/main/online-proxies/txt/proxies-socks4.txt)
```yaml
1.4.214.148:5678
1.9.167.35:60489
3.141.13.98:5678
4.28.96.166:39593
5.133.24.167:5678
8.42.70.4:39593
13.58.88.184:5678
13.58.223.158:5678
14.102.78.67:4145
14.215.212.37:4153
14.232.160.252:10801
18.216.32.60:5678
18.216.72.10:5678
24.214.238.54:10661
24.234.142.123:31008
24.249.199.4:4145
24.249.199.12:4145
27.123.1.34:4153
27.123.222.34:5678
27.123.222.35:5678
27.123.222.36:5678
27.123.222.37:5678
27.123.222.38:5678
31.28.241.117:4145
31.173.251.198:40547
36.37.86.60:50031
36.37.244.41:5678
36.67.14.5:5678
36.67.14.151:5678
36.67.142.11:5678
```

## [SOCKS5 (168/1985)](https://raw.githubusercontent.com/jetkai/proxy-list/main/online-proxies/txt/proxies-socks5.txt)
```yaml
5.11.17.230:1080
5.144.135.117:1080
8.210.48.101:17896
14.23.50.42:7302
23.234.213.157:6666
24.249.199.4:4145
36.32.191.51:7302
37.131.202.95:33427
37.139.243.32:1080
39.184.147.250:7302
43.129.243.128:3001
43.224.10.32:6667
43.224.10.33:6667
45.67.229.104:30001
45.67.229.104:30002
50.62.35.16:59816
50.62.63.126:10230
50.62.63.126:64405
51.79.52.80:3080
51.83.21.224:16379
51.155.3.184:33427
54.37.90.13:33410
58.20.184.7:7302
58.21.199.78:7302
58.220.191.18:7300
58.253.216.242:7302
59.59.6.86:7300
59.61.227.37:7302
60.12.72.206:7300
60.190.52.6:7302
```

## [HTTP (741/1985)](https://raw.githubusercontent.com/jetkai/proxy-list/main/online-proxies/txt/proxies-http.txt)
```yaml
1.0.170.50:8080
1.0.170.50:80
1.2.252.65:8080
1.20.217.52:8080
1.179.148.9:55636
1.179.232.220:8080
1.186.40.35:1111
1.186.85.38:1111
2.179.193.146:80
3.20.236.208:49205
5.16.7.213:1256
5.133.30.150:8080
5.160.91.130:3128
5.180.130.90:80
5.180.130.90:443
5.189.186.24:5566
8.214.41.50:80
8.242.207.202:8080
12.88.29.66:9080
14.139.184.130:3128
18.216.72.10:49205
27.105.130.93:8080
27.109.116.28:55443
27.147.209.215:8080
31.3.169.45:8080
31.128.71.241:8081
31.163.192.161:3129
34.229.130.62:49205
36.66.103.211:3128
36.66.124.193:3128
```

## [HTTPS (696/1985)](https://raw.githubusercontent.com/jetkai/proxy-list/main/online-proxies/txt/proxies-https.txt)
```yaml
1.2.252.65:8080
1.186.85.38:1111
1.186.245.226:80
2.179.193.146:80
2.184.4.70:6565
3.20.236.208:49205
5.131.243.11:8080
5.139.161.156:55443
5.180.130.90:8080
8.214.41.50:80
8.242.207.202:8080
12.88.29.66:9080
14.139.184.130:3128
14.143.172.238:8080
14.177.236.212:55443
14.192.3.161:82
18.191.253.100:49205
18.216.72.10:49205
18.216.136.190:9090
18.222.17.49:49205
27.255.3.134:3128
31.128.71.241:8081
31.173.94.93:43539
31.202.170.187:8080
34.229.130.62:49205
34.230.89.25:49205
36.37.180.59:65205
36.66.172.121:39810
36.67.27.153:8080
36.67.52.35:8080
```

## [ARCHIVE (1985/57616)](https://raw.githubusercontent.com/jetkai/proxy-list/main/archive/txt/working-proxies-history.txt)
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
1.0.157.49:4145
1.0.160.106:4153
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
1.0.190.19:4145
1.0.191.138:4153
1.0.205.87:8080
1.0.209.116:4145
```



Thx Co Pure Gs - Sort Meister! 💟