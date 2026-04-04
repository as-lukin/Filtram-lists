# 🛡️ Filtram — DNS Blocklists

Auto-updated DNS blocklists for **Pi-hole**, **AdGuard Home**, **Unbound** and other DNS filters.

> 🕒 Updated daily at 03:00 UTC automatically

---

## 📋 Categories

| File | Description | AdGuard format |
|------|-------------|----------------|
| `social.txt` | Social networks (Facebook, TikTok, VK, Twitter...) | `social.adguard.txt` |
| `messengers.txt` | Messengers (WhatsApp, Telegram, Signal...) | `messengers.adguard.txt` |
| `adult.txt` | Adult content | `adult.adguard.txt` |
| `gambling.txt` | Gambling & betting | `gambling.adguard.txt` |
| `ads.txt` | Ad networks (DoubleClick, Criteo, Taboola...) | `ads.adguard.txt` |
| `tracking.txt` | Trackers & analytics (GA4, Hotjar, Yandex Metrica...) | `tracking.adguard.txt` |
| `crypto.txt` | Crypto exchanges & wallets | `crypto.adguard.txt` |
| `phishing.txt` | Phishing & malware | `phishing.adguard.txt` |
| `blocklist_ALL.txt` | ⭐ Everything combined | `blocklist_ALL.adguard.txt` |

---

## 🚀 Quick setup

### AdGuard Home
**Filters → DNS Blocklists → Add blocklist**

```
https://raw.githubusercontent.com/as-lukin/Filtram-lists/main/blocklist_ALL.adguard.txt
```

Or by category:
```
https://raw.githubusercontent.com/as-lukin/Filtram-lists/main/social.adguard.txt
https://raw.githubusercontent.com/as-lukin/Filtram-lists/main/tracking.adguard.txt
https://raw.githubusercontent.com/as-lukin/Filtram-lists/main/ads.adguard.txt
https://raw.githubusercontent.com/as-lukin/Filtram-lists/main/gambling.adguard.txt
https://raw.githubusercontent.com/as-lukin/Filtram-lists/main/adult.adguard.txt
https://raw.githubusercontent.com/as-lukin/Filtram-lists/main/crypto.adguard.txt
https://raw.githubusercontent.com/as-lukin/Filtram-lists/main/phishing.adguard.txt
```

### Pi-hole
**Settings → Blocklists → Add**
```
https://raw.githubusercontent.com/as-lukin/Filtram-lists/main/blocklist_ALL.txt
```

---

## 📡 Sources

Lists are compiled from 25+ open sources including:
- [Hagezi DNS Blocklists](https://github.com/hagezi/dns-blocklists) — 300k+ domains, daily updates
- [OISD](https://oisd.nl/) — one of the best balanced lists
- [StevenBlack/hosts](https://github.com/StevenBlack/hosts)
- [EasyList / EasyPrivacy](https://easylist.to/)
- [AdGuard DNS Filter](https://adguardteam.github.io/AdGuardSDNSFilter)
- [Disconnect.me](https://disconnect.me/)
- [UT1 Blacklists](https://github.com/olbat/ut1-blacklists) (adult, gambling, social)
- [BlocklistProject](https://blocklistproject.github.io/Lists/)
- [PhishingArmy](https://phishing.army/)
- And more...

Combined with hand-curated entries for 350+ services across all categories.

---

## 📄 License
MIT
