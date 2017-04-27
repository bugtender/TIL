## About Ping, time, ttl

I bought [Nier:Automata](https://www.niergame.com/) on PS4 last day. But the download speed of PSN made me sad. So I google how to boost download speed and find the answer - "Set the DNS".

There's lots of DNS provider in Taiwan. How can you figure out which one is the best for you ?

Just open your terminal and the log will tell you.

#### 8.8.8.8 Google DNS 

```shell
$ ping 8.8.8.8
PING 8.8.8.8 (8.8.8.8): 56 data bytes
64 bytes from 8.8.8.8: icmp_seq=0 ttl=45 time=31.276 ms
64 bytes from 8.8.8.8: icmp_seq=1 ttl=45 time=28.298 ms
64 bytes from 8.8.8.8: icmp_seq=2 ttl=45 time=27.739 ms
64 bytes from 8.8.8.8: icmp_seq=3 ttl=45 time=28.100 ms
```

Nice Google !

#### 139.175.1.1 SEEDNET DNS

```shell
$ ping 139.175.1.1
PING 139.175.1.1 (139.175.1.1): 56 data bytes
64 bytes from 139.175.1.1: icmp_seq=0 ttl=54 time=52.358 ms
64 bytes from 139.175.1.1: icmp_seq=1 ttl=54 time=53.641 ms
64 bytes from 139.175.1.1: icmp_seq=2 ttl=54 time=53.155 ms
64 bytes from 139.175.1.1: icmp_seq=3 ttl=54 time=52.176 ms
```

SEEDNET is little bit slower.

#### 168.95.1.1 Hinet DNS

```
$ ping 168.95.1.1
PING 168.95.1.1 (168.95.1.1): 56 data bytes
64 bytes from 168.95.1.1: icmp_seq=0 ttl=248 time=21.658 ms
64 bytes from 168.95.1.1: icmp_seq=1 ttl=248 time=21.227 ms
64 bytes from 168.95.1.1: icmp_seq=2 ttl=248 time=20.596 ms
64 bytes from 168.95.1.1: icmp_seq=3 ttl=248 time=22.049 ms
```

God job, Hinet!

First, time value is smaller the better. And the second is ttl (Time-to-live).

TTL is set by the system sending the packet. Each router that receives the packet subtracts 1 from the count; if the count remains greater than 0, the router forwards the packet, otherwise it discards. 

Different operating systems set different ttl defaults. Linux is 64, Unix is 255, Windows is 128 usually.

So if Google and Hinet both are 20ms. Then we compare the ttl.

Google is `64 - 45 = 9`, but the Hinet is `256 - 248 = 8`. So Hinet DNS will better than Google DNS theoretically.



- - -

## 關於 Ping, time, ttl

因為最近想要玩 PS4 上面的 [Nier:Automata](https://www.niergame.com/) ，結果數位版下載的速度讓我讓我等到往生，查了一下才發現可以使用修改 DNS 加速，沒辦法誰叫台灣沒有獨立節點呢。

不過網路上一堆人提供 DNS ，同樣在台灣還是會因為你的所在地區跟 ISP 影響到結果，到底哪一個是最適合你的呢？

打開終端機，用 ping 指令來看數據吧。

#### 8.8.8.8 Google DNS 

```shell
$ ping 8.8.8.8
PING 8.8.8.8 (8.8.8.8): 56 data bytes
64 bytes from 8.8.8.8: icmp_seq=0 ttl=45 time=31.276 ms
64 bytes from 8.8.8.8: icmp_seq=1 ttl=45 time=28.298 ms
64 bytes from 8.8.8.8: icmp_seq=2 ttl=45 time=27.739 ms
64 bytes from 8.8.8.8: icmp_seq=3 ttl=45 time=28.100 ms
```

嗯...不愧是 Google 速度不錯。

#### 139.175.1.1 SEEDNET DNS

```shell
$ ping 139.175.1.1
PING 139.175.1.1 (139.175.1.1): 56 data bytes
64 bytes from 139.175.1.1: icmp_seq=0 ttl=54 time=52.358 ms
64 bytes from 139.175.1.1: icmp_seq=1 ttl=54 time=53.641 ms
64 bytes from 139.175.1.1: icmp_seq=2 ttl=54 time=53.155 ms
64 bytes from 139.175.1.1: icmp_seq=3 ttl=54 time=52.176 ms
```

SEEDNET 速度就慢了點。

#### 168.95.1.1 Hinet DNS

```
$ ping 168.95.1.1
PING 168.95.1.1 (168.95.1.1): 56 data bytes
64 bytes from 168.95.1.1: icmp_seq=0 ttl=248 time=21.658 ms
64 bytes from 168.95.1.1: icmp_seq=1 ttl=248 time=21.227 ms
64 bytes from 168.95.1.1: icmp_seq=2 ttl=248 time=20.596 ms
64 bytes from 168.95.1.1: icmp_seq=3 ttl=248 time=22.049 ms
```

不愧是中華電信自肥。


上面這些數據來說，第一個要看的是 time 值（越小越好），第二個是要看 ttl。

ttl 的值比較難以直接用數字大小判斷，稍微解釋一下， ttl 全名叫做 Time-to-live 封包存活時間，一個封包從 A 點傳到 B 點會經過許多路由器，我們為了讓封包不要一直活在網路上浪費生命，所以我們讓封包經過一個路由器 ttl 就會自動減一，歸零的話就駕鶴歸西。

不過不同的系統有不同的 ttl 起始值， Linux 通常是 64 ， Unix 通常是 255 ， Windows 通常是 128 。

由此我們先假設 Google 跟中華電信的 time 都是 20 ms 好了，開始比較 ttl 的話， Google 要到我家就經過了 `64 - 45 = 9` 個，中華電信就是 `256 - 248 = 8` 個，那此時選擇中華電信理論上會快一點點。

但上面的實測數據用 time 就可以知道是中華電信大獲全勝了，調整好之後下載時間少了一半呢！
