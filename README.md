# ADBLOCK-GIST
Adblock rules for Surge 4 and Quantumult X, compatible with Surge Module. Duplicated rules from *[domain rules](https://github.com/TPCTPCTPC/Adblock-gist/tree/master/DOMAINs)* are removed/merged to **[Keywords.list](https://github.com/TPCTPCTPC/Adblock-gist/blob/master/Keywords.list)** & **[Suffixes.list](https://github.com/TPCTPCTPC/Adblock-gist/blob/master/Suffixes.list)**.

💡 Check the content before use.

💡 Use AdGuard for a better effect on Safari.

## Profile Introduction

This Profiles is featured in modularised blocking rules. Except for basic rules, the others will be sorted by network services. eg: Youtube, Spotify, Alibaba. Both **HTTP** and **HTTPS** blocking rules are included and **HTTPS** requests shall be decrytped by MITM, use it at your own risk.

#### Extended blockers for common trackers and advertisements: 
1. **[Suffixes](https://github.com/TPCTPCTPC/Adblock-gist/blob/master/Suffixes.list)** 
2. **[Keywords](https://github.com/TPCTPCTPC/Adblock-gist/blob/master/Keywords.list)** 
3. **[Others](https://github.com/TPCTPCTPC/Adblock-gist/blob/master/Others.list)**

#### Modularised rule sets with [IP-based rules](https://manual.nssurge.com/rule/ip-based.html), [Domain-based rules](https://manual.nssurge.com/rule/domain-based.html) and [Logical rules](https://manual.nssurge.com/rule/logical-rule.html): 
1. **[Domain Rules](https://github.com/TPCTPCTPC/Adblock-gist/tree/master/DOMAINs)**
2. **[Supplement for anti-AD](https://github.com/TPCTPCTPC/Adblock-gist/tree/master/Supplement%20for%20anti-AD)**

#### Modularised rule sets with [HTTP(S) rules](https://manual.nssurge.com/rule/http.html): 
1. **[URL Regex](https://github.com/TPCTPCTPC/Adblock-gist/tree/master/URL-REGEX)**
2. **[Mock](https://github.com/TPCTPCTPC/Adblock-gist/tree/master/Mock)**
3. **[URL Rewrite](https://github.com/TPCTPCTPC/Adblock-gist/tree/master/URL-REWRITE)**


## Compatibility

|                                                                                            |`Surge`|`Quantumult X`|
|--------------------------------------------------------------------------------------------|:-----:|:------------:|
|*[Suffixes.list](https://github.com/TPCTPCTPC/Adblock-gist/blob/master/Suffixes.list)*                      |☑️|☑️|
|*[Keywords.list](https://github.com/TPCTPCTPC/Adblock-gist/blob/master/Keywords.list)*                      |☑️|☑️|
|*[Others.list](https://github.com/TPCTPCTPC/Adblock-gist/blob/master/Others.list)*                          |☑️|☑️|
|*[Domain Rules](https://github.com/TPCTPCTPC/Adblock-gist/tree/master/DOMAINs)*                             |☑️|☑️|
|*[URL Regex](https://github.com/TPCTPCTPC/Adblock-gist/tree/master/URL-REGEX)*                              |☑️|   |
|*[URL Rewrite](https://github.com/TPCTPCTPC/Adblock-gist/tree/master/URL-REWRITE)*                          |   |☑️|
|*[Mock](https://github.com/TPCTPCTPC/Adblock-gist/tree/master/Mock)*                                     |☑️|   |
|*[Supplement for anti-AD](https://github.com/TPCTPCTPC/Adblock-gist/tree/master/Supplement%20for%20anti-AD)*|☑️|☑️|

## Work with *[anti-AD](https://github.com/privacy-protection-tools/anti-AD)*:

After Version 4.2.2, Surge is able to load 1,000,000+ rules through ```DOMAIN-SET```. **anti-AD** is an abundant adblocking filter list based on *Easylist* and optimised for Chinese websites. If you like to use **anti-AD** rules through ```DOMAIN-SET```, please subscribe the supplement version (deduplicated already).

DOMAIN-SET example:
```
DOMAIN-SET,https://raw.githubusercontent.com/privacy-protection-tools/anti-AD/master/anti-ad-surge2.txt,REJECT

or

DOMAIN-SET,https://anti-ad.net/surge2.txt,REJECT
```

## Work with *Mock (Map Local)*

This feature allows Surge to return an empty json to the network request, which can significantly reduce RAM usage on device than JavaScript(*Yachen Liu, Surge Testflight 1723*). Mocking feature is now universial and available on *Surge Module* and base configuration. **The fuction of mocking in this gist is duplicate with ```URL-REGEX rules```, choose one you prefer.**

## Create your own *[Surge Module](https://manual.nssurge.com/others/module.html)*:
```
#!name=$yourname
#!desc=$yourdescription
// Optional: ignore if you need both
#!system=(ios/mac)

[Rule]
RULE-SET,https://raw.githubusercontent.com/TPCTPCTPC/Adblock-gist/master/DOMAINs/EXAMPLE.list,REJECT
RULE-SET,https://raw.githubusercontent.com/TPCTPCTPC/Adblock-gist/master/URL-REGEX/EXAMPLE.list,REJECT

[Map Local]
^https://an\.example\.com/ad data="empty.json" // You can generate an empty json on your own surge.

[MITM]
hostname = %APPEND% an.example.com
```

### Why create your own *Module*?

It is your responsibility to avoid risks from the Man-In-The-Middle attack. 
A remote *Module* can be easily incerted any new hostnames and Javascripts, which could significantly increase the risk of your networking safety, if the user did not notice the change when updating the *Module*.

## **Quantumult X** Users?
ADBLOCK-GIST now supports QX with *[domain rules](https://github.com/TPCTPCTPC/Adblock-gist/tree/master/DOMAINs)* compatibly and *[url rewrites rules](https://github.com/TPCTPCTPC/Adblock-gist/tree/master/URL-REWRITE)* exclusively.

## Credits:
- [anti-AD](https://github.com/privacy-protection-tools/anti-AD)
- [Choler](https://github.com/Choler/Surge)
- [ConnersHua](https://github.com/ConnersHua/Profiles/tree/master)
- [domain-list-community](https://github.com/v2ray/domain-list-community)
- [Lãng Khách](https://github.com/langkhach270389/Scripting/tree/master/Surge)
- [lhie1](https://github.com/lhie1/Rules)
- [onewayticket255](https://github.com/onewayticket255/Surge-Script)
- [primovist](https://github.com/primovist/ScriptsForSurge)
- [Yachen Liu](https://manual.nssurge.com/)
