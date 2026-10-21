# فهرست roadmaps/networking/roadmap.html (Index)

این فایل یک نمایهٔ فشرده از `roadmaps/networking/roadmap.html` (نقشه راه شبکه) است — فقط شناسه/عنوان/سطح/برچسب نردبان — تا بدون بارگذاری کل فایل بتوان ساختار آن را مرور کرد.

- ستون **سطح** = دشواری موضوع (Beginner/Intermediate/Advanced/Expert).
- ستون **L** = حداقل سطح نردبان مهندسی نرم‌افزار (۱ تا ۸) که باید این موضوع را بداند؛ سطوح بالاتر هم باید بدانند (تعریف کامل هر سطح در فاز p54 فایل `../backend/roadmap.html` و در `../bitpin-engineering-ladder.md`). مقدار **اختیاری** یعنی موضوع برای هیچ سطحی الزامی نیست.
- پیشرفت این نقشه راه جدا از نقشه راه اصلی ذخیره می‌شود (کلید localStorage: `network_roadmap_progress_v1`) و با دکمه‌های اکسپورت/ایمپورت به فایل `network-roadmap-progress-YYYY-MM-DD.json` منتقل می‌شود.

## p0 (فاز 0) 🧭 مبانی شبکه و مدل‌های لایه‌ای
زبان مشترک شبکه: لایه‌ها، Encapsulation، معیارهای کارایی و سفر یک درخواست از کلاینت تا سرور.

| id | عنوان | سطح | L |
|---|---|---|---|
| nf-osi-tcpip | مدل OSI و TCP/IP، Encapsulation و PDUها | Beginner | L1+ |
| nf-latency-bandwidth | Latency، Bandwidth، Throughput، Jitter و BDP | Beginner | L1+ |
| nf-request-journey | سفر یک درخواست: از curl تا سرور و برگشت (Packet Walk) | Beginner | L1+ |

## p1 (فاز 1) 🔌 لایهٔ پیوند و شبکهٔ محلی (LAN)
Ethernet، MAC، ARP، DHCP و VLAN — آنچه قبل از رسیدن بسته به روتر اتفاق می‌افتد.

| id | عنوان | سطح | L |
|---|---|---|---|
| l2-ethernet-mac | Ethernet، MAC Address، Frame و Switch | Beginner | L1+ |
| l2-arp | ARP، Neighbor Table و ARP Spoofing | Intermediate | L2+ |
| l2-dhcp | DHCP: فرآیند DORA، Lease و رزرو IP | Beginner | L1+ |
| l2-vlan-stp | VLAN، Trunk (802.1Q) و Spanning Tree | Intermediate | اختیاری |

## p2 (فاز 2) 🧮 IP، آدرس‌دهی و Subnetting
IPv4/IPv6، CIDR، NAT، ICMP و MTU — هویت و آدرس هر میزبان در شبکه.

| id | عنوان | سطح | L |
|---|---|---|---|
| ip-ipv4-cidr | IPv4، CIDR و Subnetting | Beginner | L1+ |
| ip-private-nat | آدرس‌های خصوصی، NAT، SNAT/DNAT و Port Forwarding | Intermediate | L2+ |
| ip-icmp-mtu | ICMP، TTL، MTU و Fragmentation | Intermediate | L2+ |
| ip-ipv6 | IPv6: آدرس‌دهی، SLAAC، NDP و Dual-Stack | Intermediate | L3+ |

## p3 (فاز 3) 🧭 مسیریابی (Routing)
جدول مسیریابی، Policy Routing در لینوکس، OSPF و BGP — بسته چطور راهش را پیدا می‌کند.

| id | عنوان | سطح | L |
|---|---|---|---|
| rt-routing-table | جدول مسیریابی، Default Gateway و Longest Prefix Match | Beginner | L1+ |
| rt-linux-routing | مسیریابی در لینوکس: ip route، ip rule، Policy Routing و IP Forwarding | Intermediate | L3+ |
| rt-dynamic-ospf | مسیریابی پویا: Distance Vector، Link State و OSPF | Advanced | اختیاری |
| rt-bgp-internet | BGP و ساختار اینترنت: AS، Peering، Anycast و BGP Hijack | Advanced | L5+ |

## p4 (فاز 4) 🚚 لایهٔ انتقال: TCP و UDP
Socket، هندشیک، حالت‌های TCP، کنترل ازدحام، UDP/QUIC و Timeoutها.

| id | عنوان | سطح | L |
|---|---|---|---|
| tp-ports-sockets | Port، Socket و چرخهٔ عمر اتصال از دید سیستم‌عامل (bind/listen/accept) | Beginner | L1+ |
| tp-tcp-handshake-states | TCP: هندشیک سه‌مرحله‌ای، حالت‌ها، FIN/RST و TIME_WAIT | Intermediate | L2+ |
| tp-tcp-flow-congestion | TCP: Flow Control، Congestion Control (CUBIC/BBR)، Retransmission و Nagle | Advanced | L4+ |
| tp-udp-quic | UDP و QUIC: چه زمانی TCP کافی نیست | Intermediate | L3+ |
| tp-keepalive-timeouts | Keepalive، Timeoutها و Connection Pooling | Intermediate | L3+ |

## p5 (فاز 5) 📖 DNS
از Resolve یک نام تا DNSSEC، Resolver لینوکس، مهاجرت DNS و Load Balancing مبتنی بر DNS.

| id | عنوان | سطح | L |
|---|---|---|---|
| dns-resolution | DNS: سلسله‌مراتب، Recursive/Authoritative و مسیر Resolve | Beginner | L1+ |
| dns-records | رکوردهای DNS: A/AAAA، CNAME، MX، TXT، NS، SOA، SRV، CAA و PTR | Beginner | L2+ |
| dns-ttl-caching | TTL، لایه‌های کش و مهاجرت DNS بدون Downtime | Intermediate | L2+ |
| dns-linux-resolver | DNS در لینوکس: /etc/hosts، resolv.conf، nsswitch، systemd-resolved و ndots | Intermediate | L3+ |
| dns-security-modern | امنیت DNS: Spoofing/Cache Poisoning، DNSSEC، DoH/DoT و DNS Tunneling | Advanced | L4+ |
| dns-split-geo | Split-Horizon DNS، GeoDNS و Load Balancing مبتنی بر DNS | Advanced | L5+ |

## p6 (فاز 6) 🔑 رمزنگاری و PKI (پایهٔ SSL/TLS)
Hash، رمز متقارن/نامتقارن، Diffie-Hellman، گواهی X.509 و تاریخچهٔ SSL تا TLS 1.3.

| id | عنوان | سطح | L |
|---|---|---|---|
| tls-crypto-basics | مبانی رمزنگاری: Hash، متقارن، نامتقارن، Diffie-Hellman و Forward Secrecy | Intermediate | L2+ |
| tls-x509-pki | گواهی X.509، زنجیرهٔ اعتماد، CA و Root Store | Intermediate | L2+ |
| tls-ssl-history | از SSL تا TLS 1.3: نسخه‌ها، حملات تاریخی (POODLE، BEAST، Heartbleed) و منسوخ‌شدن | Intermediate | L3+ |

## p7 (فاز 7) 🔒 TLS در عمل
هندشیک TLS 1.2/1.3، دیباگ با openssl، چرخهٔ عمر گواهی با ACME، mTLS و سخت‌سازی پیکربندی.

| id | عنوان | سطح | L |
|---|---|---|---|
| tls-handshake | هندشیک TLS 1.2 و 1.3، SNI، ALPN و Session Resumption | Advanced | L3+ |
| tls-openssl-debug | عیب‌یابی TLS با openssl s_client، curl -v و بررسی زنجیرهٔ گواهی | Intermediate | L2+ |
| tls-acme-lifecycle | صدور و چرخهٔ عمر گواهی: Let's Encrypt، ACME، cert-manager و Rotation | Intermediate | L3+ |
| tls-mtls | mTLS و احراز هویت سرویس‌به‌سرویس | Advanced | L4+ |
| tls-hardening | پیکربندی امن TLS: Cipher Suite، HSTS، OCSP Stapling، Certificate Transparency و Pinning | Advanced | L4+ |

## p8 (فاز 8) 🌐 HTTP از دید شبکه
HTTP/1.1، HTTP/2، HTTP/3، کش و CDN، WebSocket و gRPC — با تمرکز بر رفتار روی سیم و پراکسی.

| id | عنوان | سطح | L |
|---|---|---|---|
| http-11 | HTTP/1.1: پیام، هدرها، Keep-Alive و Chunked Encoding | Beginner | L1+ |
| http-caching-cdn | کش HTTP و CDN: Cache-Control، ETag، Vary و Edge | Intermediate | L2+ |
| http-2-3 | HTTP/2 و HTTP/3: Multiplexing، HPACK/QPACK و Head-of-Line Blocking | Advanced | L3+ |
| http-websocket-grpc | WebSocket، SSE و gRPC از دید شبکه و پراکسی | Intermediate | L3+ |

## p9 (فاز 9) 🔀 پراکسی و Load Balancing
Forward/Reverse/Transparent Proxy، SOCKS، Nginx/HAProxy، LB لایه ۴ و ۷، IP کلاینت و TLS Termination.

| id | عنوان | سطح | L |
|---|---|---|---|
| px-forward-reverse | Forward Proxy، Reverse Proxy، Transparent Proxy و SOCKS | Beginner | L2+ |
| px-nginx-haproxy | Nginx و HAProxy در عمل: upstream، timeout، buffering و reload | Intermediate | L2+ |
| px-l4-l7-lb | Load Balancing لایه ۴ و ۷: الگوریتم‌ها، Health Check و Sticky Session | Intermediate | L3+ |
| px-client-ip | حفظ IP کلاینت: X-Forwarded-For، Forwarded، PROXY Protocol و Trusted Proxies | Intermediate | L3+ |
| px-tls-termination | TLS Termination، Passthrough و Re-encryption در پراکسی | Advanced | L3+ |
| px-envoy-gateway | Envoy، API Gateway و Service Mesh (Data Plane) | Advanced | L5+ |

## p10 (فاز 10) 🛡️ تونل و VPN
Encapsulation و MTU در تونل، SSH Tunneling، WireGuard، IPsec/OpenVPN، Split Tunneling، Zero Trust و Overlay.

| id | عنوان | سطح | L |
|---|---|---|---|
| vpn-tunneling-basics | مفهوم تونل: Encapsulation، Overhead و MTU در تونل | Intermediate | L2+ |
| vpn-ssh-tunnels | تونل SSH: Local/Remote/Dynamic Forwarding و Jump Host | Intermediate | L2+ |
| vpn-wireguard | WireGuard: کلیدها، AllowedIPs، Routing و راه‌اندازی Site-to-Site | Intermediate | L3+ |
| vpn-ipsec-openvpn | IPsec و OpenVPN: IKE، Tunnel/Transport Mode و مقایسه | Advanced | اختیاری |
| vpn-split-zerotrust | Split Tunneling، DNS Leak، Bastion و Zero Trust Network Access | Advanced | L4+ |
| vpn-overlay-vxlan | GRE، VXLAN و شبکه‌های Overlay | Expert | اختیاری |

## p11 (فاز 11) 🧱 فایروال و امنیت شبکه
Netfilter، iptables/nftables، Conntrack، UFW و Security Group، و حملات رایج شبکه و دفاع در برابرشان.

| id | عنوان | سطح | L |
|---|---|---|---|
| fw-ufw-cloud-sg | UFW، firewalld و Security Groupهای کلاود | Beginner | L2+ |
| fw-netfilter-iptables | Netfilter، iptables و nftables: Table، Chain، Rule و NAT | Intermediate | L3+ |
| fw-conntrack-stateful | Conntrack و فایروال Stateful (و پر شدن جدول conntrack) | Advanced | L4+ |
| fw-attacks-ddos | حملات شبکه: Port Scan، SYN Flood، DDoS، MITM و دفاع | Advanced | L4+ |

## p12 (فاز 12) 🛠️ جعبه‌ابزار شبکه در لینوکس
ip، ping/mtr، dig، curl، ss، tcpdump/Wireshark، nc/socat/nmap و iperf3 — ابزارهای روزمرهٔ عیب‌یابی.

| id | عنوان | سطح | L |
|---|---|---|---|
| tool-iproute2 | iproute2: ip addr، ip link، ip route و ip neigh (جایگزین ifconfig/route/arp) | Beginner | L1+ |
| tool-ping-trace-mtr | ping، traceroute و mtr: Reachability، مسیر و Packet Loss | Beginner | L1+ |
| tool-dig | dig، host و nslookup: دیباگ حرفه‌ای DNS | Beginner | L1+ |
| tool-curl-wget | curl حرفه‌ای: -v، --resolve، --connect-to، زمان‌بندی (-w) و httpie | Beginner | L1+ |
| tool-ss-netstat-lsof | ss، netstat و lsof: سوکت‌ها، پورت‌ها و پروسهٔ صاحب آن‌ها | Beginner | L2+ |
| tool-nc-socat-nmap | nc، socat و nmap: ساخت اتصال دستی و اسکن پورت | Intermediate | L2+ |
| tool-tcpdump-wireshark | tcpdump، tshark و Wireshark: کپچر و تحلیل بسته | Intermediate | L3+ |
| tool-iperf-perf | iperf3، ethtool، iftop/nethogs و اندازه‌گیری کارایی شبکه | Intermediate | L3+ |

## p13 (فاز 13) 🐧 شبکه در کرنل لینوکس
Namespace، veth و Bridge، تیونینگ sysctl، مسیر بسته در کرنل و eBPF/XDP.

| id | عنوان | سطح | L |
|---|---|---|---|
| lk-namespaces-veth | Network Namespace، veth و Bridge: ساخت شبکهٔ کانتینر از صفر | Advanced | L4+ |
| lk-sysctl-tuning | تیونینگ sysctl: somaxconn، backlog، ephemeral ports، tcp_tw_reuse و بافرها | Advanced | L4+ |
| lk-packet-path | مسیر بسته در کرنل: NIC، Ring Buffer، NAPI/softirq، Netfilter Hooks و Socket | Expert | اختیاری |
| lk-ebpf-xdp | eBPF و XDP برای Observability و فیلتر سریع شبکه | Expert | اختیاری |

## p14 (فاز 14) ☸️ شبکهٔ کانتینر و کلاود
شبکهٔ Docker، مدل شبکهٔ Kubernetes و CNI، Service/Ingress، NetworkPolicy و VPC کلاود.

| id | عنوان | سطح | L |
|---|---|---|---|
| cn-docker-net | شبکهٔ Docker: bridge، host، none، Port Publishing و DNS داخلی | Intermediate | L2+ |
| cn-cloud-vpc | VPC کلاود: Subnet عمومی/خصوصی، Route Table، NAT Gateway، Peering و PrivateLink | Intermediate | L3+ |
| cn-k8s-net-model | مدل شبکهٔ Kubernetes: Pod IP و CNI (Calico، Cilium، Flannel) | Advanced | L3+ |
| cn-k8s-services-ingress | Service، kube-proxy (iptables/IPVS)، Ingress، Gateway API و CoreDNS | Advanced | L3+ |
| cn-k8s-netpol | NetworkPolicy و ایزوله‌سازی ترافیک در Kubernetes | Advanced | L4+ |

## p15 (فاز 15) 🔍 عیب‌یابی، عملکرد و طراحی شبکه
روش لایه‌به‌لایه، MTU Black Hole، تحلیل تأخیر، مانیتورینگ شبکه و بازبینی معماری شبکهٔ سیستم.

| id | عنوان | سطح | L |
|---|---|---|---|
| ts-methodology | روش لایه‌به‌لایهٔ عیب‌یابی شبکه (Bottom-up، Top-down، Divide & Conquer) | Intermediate | L2+ |
| ts-latency-analysis | تحلیل تأخیر: DNS/Connect/TLS/TTFB، Tail Latency و Packet Loss | Advanced | L3+ |
| ts-mtu-blackhole | MTU Black Hole، PMTUD و MSS Clamping | Advanced | L4+ |
| ts-observability | مانیتورینگ شبکه: متریک‌های retransmit/drop، Blackbox Exporter و Synthetic Check | Advanced | L4+ |
| ts-design-review | طراحی و بازبینی معماری شبکه: Segmentation، HA، DR و هزینهٔ ترافیک | Expert | L6+ |

## p16 (فاز 16) 🏗️ پروژه‌های عملی شبکه (هم‌راستا با نردبان)
یک زیرساخت واحد که در ۶ گام هم‌زمان با سطوح نردبان رشد می‌کند: هر سطح یک پروژه با صورت‌مسئلهٔ ثابت و معیار پذیرش عددی.

| id | عنوان | سطح | L |
|---|---|---|---|
| nproj-l1 | پروژه سطح یک: اسکریپت «چک‌آپ اتصال» برای عیب‌یابی DNS/TCP/TLS/HTTP یک سرویس | Beginner | L1+ |
| nproj-l2 | پروژه سطح دو: استقرار سرویس پشت Nginx با HTTPS (Let's Encrypt)، Redirect و IP درست کلاینت | Beginner | L2+ |
| nproj-l3 | پروژه سطح سه: شبکهٔ خصوصی سه‌سروری با WireGuard، فایروال nftables و DNS داخلی | Intermediate | L3+ |
| nproj-l4 | پروژه سطح چهار: Load Balancer دسترس‌پذیر (keepalived/VRRP + HAProxy) و mTLS بین سرویس‌ها | Advanced | L4+ |
| nproj-l5 | پروژه سطح پنج: شبکهٔ کانتینر از صفر (namespace/veth/bridge/NAT) و مقایسه با CNI واقعی + NetworkPolicy | Advanced | L5+ |
| nproj-l6 | پروژه سطح شش: طراحی شبکهٔ چندمنطقه‌ای با GeoDNS/Anycast، DR و سند طراحی + PoC | Expert | L6+ |
