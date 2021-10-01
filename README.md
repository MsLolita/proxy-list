<!-- MARKDOWN LINKS & IMAGES -->
<!-- https://www.markdownguide.org/basic-syntax/#reference-style-links -->
[contributors-shield]: https://img.shields.io/github/contributors/jetkai/proxy-list?style=for-the-badge
[contributors-url]: https://github.com/jetkai/proxy-list/graphs/contributors
[forks-shield]: https://img.shields.io/github/forks/jetkai/proxy-list?style=for-the-badge
[forks-url]: https://github.com/jetkai/proxy-list/network/members
[stars-shield]: https://img.shields.io/github/stars/jetkai/proxy-list?style=for-the-badge
[stars-url]: https://github.com/jetkai/proxy-list/stargazers
[issues-shield]: https://img.shields.io/github/issues/jetkai/proxy-list?style=for-the-badge
[issues-url]: https://github.com/jetkai/proxy-list/issues
[license-shield]: https://img.shields.io/github/license/jetkai/proxy-list?style=for-the-badge
[license-url]: https://github.com/jetkai/proxy-list/blob/main/LICENSE
[commit-shield]: https://img.shields.io/github/last-commit/jetkai/proxy-list?style=for-the-badge
[commit-url]: https://github.com/jetkai/proxy-list/commits/main

# 🎁 SOCKS4/5 & HTTP/S PROXIES // ONLINE & READY

[![Commits][commit-shield]][commit-url]
[![Contributors][contributors-shield]][contributors-url]
[![Stargazers][stars-shield]][stars-url]
[![Forks][forks-shield]][forks-url]
[![Issues][issues-shield]][issues-url]
[![MIT License][license-shield]][license-url]

## About This Project & The Proxies
This repository contains a free list of tested SOCKS4/5 & HTTP/S proxies in -> **JSON**, **TXT** & **CSV** format. 

### Testing:

These proxies are tested ~12x/day (every 2 hours) against OVH & other EU/US hosting providers, they have been verified to write & read data <**AT THE TIME OF TESTING**>. No authentication is required to connect to these proxies.

[Source Code](https://github.com/jetkai/ProxyBuilder/blob/main/src/main/kotlin/spb/net/proxy/ProxyTester.kt)
```kotlin
    private fun useSocksProxy(serverAddress: String?, serverPort: Int): ClientSocket? {
        val proxy = Proxy(Proxy.Type.SOCKS, InetSocketAddress(proxyAddress, proxyPort))
        val socket = Socket(proxy)
        if(socks4)
            forceSocks4(socket)
        try {
            socket.soTimeout = 3000
            socket.tcpNoDelay = true
            socket.connect(InetSocketAddress(serverAddress, serverPort))
        } catch (e : IOException) {
            socket.close()
        }
        if(socket.isClosed)
            return null
        return ClientSocket().init(socket)
    }
```

### Proxy Formatting:

These proxies are scraped from various sources & I compile this data using my [ProxyBuilder](https://github.com/jetkai/ProxyBuilder) application. Proxies are sorted from lowest to highest 0-255 & duplicated proxies are removed — the only exception is if an IP has a different port open, which is also a working proxy tunnel <**Less than 1% of the total proxies at the time of testing**>.

```IP:Port -> 1.0.132.249:4153```

### Compatability:

Proxies work for any application that can establish a socket connection, such as... An application that has proxy support (FireFox, Chrome), or as an example, these Java Apps -> [JaySyiPker](https://github.com/JayArrowz/JaySyiPker), [Bruteforce-RSPS](https://github.com/jetkai/Bruteforce-RSPS) & [718 Cheat Client (Final)](https://github.com/jetkai/718-Cheat-Client-Final).

### ProxyList Links (Direct URL):

- _Online Proxies:_
    - **JSON** -> [proxies.json](https://raw.githubusercontent.com/jetkai/proxy-list/main/proxies.json)
    - **TXT** -> [proxies.txt](https://raw.githubusercontent.com/jetkai/proxy-list/main/proxies.txt)
    - **CSV** -> [proxies.csv](https://raw.githubusercontent.com/jetkai/proxy-list/main/proxies.csv)
- _Online/Offline Proxies (Archive):_
  - **JSON** -> [working-proxies-history.json](https://raw.githubusercontent.com/jetkai/proxy-list/main/archive/working-proxies-history.json)
  - **TXT** -> [working-proxies-history.txt](https://raw.githubusercontent.com/jetkai/proxy-list/main/archive/working-proxies-history.txt)
  - **CSV** -> [working-proxies-history.csv](https://raw.githubusercontent.com/jetkai/proxy-list/main/archive/working-proxies-history.csv)

### Next Updates:

Further updates will be made to this project throughout the year, the next update I am working on will keep a record of proxy up-time, location, isp & speed.

---

# [SAMPLE PROXIES] - [October 01 2021 | 03:29:02]

### Proxy Statistics:
- _Online Proxies (By Protocol):_
   - **SOCKS4** -> 3717
   - **SOCKS5** -> 168
   - **HTTP** -> 911
   - **HTTPS** -> 894

- _Proxies (Total):_
   - **Online Proxies (SOCKS4/5 + HTTP/S)** -> 5690
   - **Unique Online Proxies** -> 5332
   - **Unique Online/Offline Proxies (Archive)** -> 55308

## [SOCKS4 (3717/5332)](https://raw.githubusercontent.com/jetkai/proxy-list/main/online-proxies/txt/proxies-socks4.txt)
```yaml
1.4.214.148:5678
1.9.165.67:4153
1.9.167.35:60489
1.10.140.43:4145
1.20.95.95:5678
1.20.96.164:4153
1.20.137.82:32241
1.20.168.157:4145
1.20.184.75:4153
1.53.137.84:4145
1.55.241.4:4145
1.179.130.201:4153
1.179.145.101:33109
1.179.148.9:36476
1.179.172.45:31225
1.179.181.213:30500
1.179.186.70:1080
1.179.201.189:5678
1.186.40.157:39651
1.186.82.4:5678
1.212.157.115:4145
1.212.181.131:4145
1.220.145.45:4145
1.221.173.148:4145
1.234.35.141:1080
2.38.199.61:1080
2.135.223.134:5678
2.139.162.80:4145
2.183.9.228:5678
3.141.13.98:5678
```

## [SOCKS5 (168/5332)](https://raw.githubusercontent.com/jetkai/proxy-list/main/online-proxies/txt/proxies-socks5.txt)
```yaml
1.116.4.222:7890
8.129.25.203:9999
8.131.254.15:9999
8.214.2.182:7890
24.249.199.12:4145
24.249.199.14:57335
27.116.51.178:6667
27.116.51.181:6667
27.116.51.186:6667
31.7.232.178:1080
31.128.248.1:1080
36.89.86.49:56845
36.94.126.50:1080
37.156.104.178:3327
43.128.13.103:28010
43.224.8.12:6667
43.224.10.11:6667
43.224.10.19:6667
43.224.10.27:6667
43.224.10.35:6667
43.224.10.37:6667
43.224.10.42:6667
46.0.234.11:5678
47.75.113.110:10017
47.240.226.173:7891
47.242.5.82:5678
52.175.21.231:1080
64.126.160.161:31337
66.42.224.229:41679
66.135.227.178:4145
```

## [HTTP (911/5332)](https://raw.githubusercontent.com/jetkai/proxy-list/main/online-proxies/txt/proxies-http.txt)
```yaml
1.20.207.200:8080
1.116.4.222:7890
5.16.0.49:8080
5.16.0.77:1256
5.34.153.142:8080
5.44.54.16:8080
5.44.54.106:8080
5.183.71.145:39305
5.190.29.161:8080
8.129.10.162:3228
8.129.179.234:3228
8.208.91.118:8000
8.214.2.182:7890
12.139.210.121:8080
13.229.47.250:8118
14.102.13.161:8080
14.160.26.153:8080
14.161.252.185:55443
14.177.236.212:55443
14.192.148.170:3128
14.192.150.210:3128
14.241.225.167:80
18.220.20.81:8080
24.172.34.114:49920
27.72.244.228:8080
27.111.45.18:55443
27.116.51.119:8080
27.121.85.74:8080
27.191.60.5:3256
27.191.60.91:3256
```

## [HTTPS (894/5332)](https://raw.githubusercontent.com/jetkai/proxy-list/main/online-proxies/txt/proxies-https.txt)
```yaml
1.0.205.87:8080
1.1.220.100:8080
1.10.187.237:8080
1.20.166.142:8080
1.20.207.200:8080
1.116.4.222:7890
1.179.148.9:55636
3.8.23.128:34798
5.16.0.49:8080
5.16.0.180:8080
5.20.91.12:60792
5.44.54.106:8080
5.59.136.230:8080
5.149.219.201:8080
5.183.234.1:8080
8.129.10.162:3228
8.129.179.234:3228
8.208.91.118:80
8.242.215.250:999
14.102.152.158:8080
14.160.26.153:8080
14.161.10.191:8080
14.161.252.185:55443
14.170.154.10:8080
18.159.210.15:9300
18.220.20.81:8080
24.106.221.230:53281
27.72.244.228:8080
27.109.116.28:55443
27.109.116.119:23500
```

## [ARCHIVE (5332/55308)](https://raw.githubusercontent.com/jetkai/proxy-list/main/archive/txt/working-proxies-history.txt)
```yaml
1.0.132.249:4153
1.0.133.89:4153
1.0.133.100:51327
1.0.136.51:4145
1.0.136.115:4145
1.0.137.117:5678
1.0.144.14:5678
1.0.202.54:5678
1.0.205.87:8080
1.0.209.45:4145
1.0.212.209:4145
1.0.213.150:5678
1.0.215.76:5678
1.0.215.239:5678
1.0.225.117:5678
1.0.251.164:4145
1.1.160.205:4145
1.1.185.208:4145
1.1.189.58:8080
1.1.220.100:8080
1.1.224.68:5678
1.1.225.97:5678
1.1.226.87:5678
1.1.226.224:5678
1.1.227.33:5678
1.1.227.203:4145
1.1.229.183:5678
1.1.230.183:5678
1.1.231.200:4145
1.1.245.173:5678
```



Thx Co Pure Gs - Sort Meister! 💟