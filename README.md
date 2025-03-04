
# Privilege Escalation Cheatsheet (Vulnhub)

This cheasheet is aimed at the CTF Players and Beginners to help them understand the fundamentals of Privilege Escalation with examples. It is not a cheatsheet for Enumeration using Linux Commands. Privilege escalation is all about proper enumeration. There are multiple ways to perform the same tasks. We have performed and compiled this list on our experience. Please share this with your connections and direct queries and feedback to [Pavandeep Singh](https://www.linkedin.com/in/pavan2318).

<a href="https://ibb.co/YBB2JqR"><img src="https://i.ibb.co/F446cjx/cheatsheet.jpg" alt="cheatsheet" border="0"></a>


Table of Contents
=================

* [Abusing Sudo Rights](#sudo)
* [SUID Bit](#suid)
* [Kernel Exploit](#kernel)
* [Path Variable](#path)
* [Enumeration](#enum)
* [MySQL](#mysql)
* [Crontab](#crontab)
* [Wildcard Injection](#wild)
* [Capabilities](#capabilities)
* [Writable etc/passwd file](#etc)
* [Writable files or script as root](#root)
* [Buffer Overflow](#buffer)
* [Docker](#docker)

<a name="sudo"></a>
## Abusing Sudo Rights


1.	[Holynix: v1](https://www.hackingarticles.in/hack-the-holynix-v1-boot-2-root-challenge/)
2.	[DE-ICE:S1.120](https://www.hackingarticles.in/hack-the-de-ice-s1-120-vm-boot-to-root/)
3.	[21 LTR: Scene1](https://www.hackingarticles.in/hack-the-21ltr-scene-1-vm-boot-to-root/)
4.	[Kioptrix : Level 1.2](https://www.hackingarticles.in/hack-the-kioptrix-level-1-2-boot2root-challenge/)
5.	[Skytower](https://www.hackingarticles.in/hack-the-skytower-ctf-challenge/)
6.	[Fristileaks](https://www.hackingarticles.in/hack-fristileaks-vm-ctf-challenge/)
7.	[Breach 2.1](https://www.hackingarticles.in/hack-breach-2-1-vm-ctf-challenge/)
8.	[Zico 2](https://www.hackingarticles.in/hack-zico2-vm-ctf-challenge/)
9.	[RickdiculouslyEasy](https://www.hackingarticles.in/hack-rickdiculouslyeasy-vm-ctf-challenge/)
10.	[Dina](https://www.hackingarticles.in/hack-dina-vm-ctf-challenge/)
11.	[Depth](https://www.hackingarticles.in/hack-depth-vm-ctf-challenge/)
12.	[The Ether: Evil Science](https://www.hackingarticles.in/hack-ether-evilscience-vm-ctf-challenge/)
13.	[Basic penetration](https://www.hackingarticles.in/hack-the-basic-penetration-vm-boot2root-challenge/)
14.	[DerpNStink](https://www.hackingarticles.in/hack-the-derpnstink-vm-ctf-challenge/)
15.	[W1R3S.inc](https://www.hackingarticles.in/hack-the-w1r3s-inc-vm-ctf-challenge/)
16.	[Bob:1.0.1](https://www.hackingarticles.in/hack-the-bob-1-0-1-vm-ctf-challenge/)
17.	[The blackmarket](https://www.hackingarticles.in/hack-the-blackmarket-vm-ctf-challenge/)
18.	[Violator](https://www.hackingarticles.in/hack-the-violator-ctf-challenge/)
19.	[Basic Pentesting : 2](https://www.hackingarticles.in/hack-the-basic-pentesting2-vm-ctf-challenge/)
20.	[Temple of Doom](https://www.hackingarticles.in/hack-the-temple-of-doom-ctf-challenge/)
21.	[Wakanda : 1](https://www.hackingarticles.in/hack-the-wakanda-1-ctf-challenge/)
22.	[Matrix : 1](https://www.hackingarticles.in/matrix-1-vulnhub-walkthrough/)
23.	[KFIOFan : 1](https://www.hackingarticles.in/kfiofan1-vulnhub-walkthrough/)
24.	[W34n3ss 1](https://www.hackingarticles.in/w34kn3ss-1-vulnhub-lab-walkthrough/)
25.	[Replay : 1](https://www.hackingarticles.in/replay-1-vulnhub-lab-walkthrough/)
26.	[Unknowndevice64 : 1](https://www.hackingarticles.in/unknowndevice64-v2-0-vulnhub-walkthrough/)
27.	[Web Developer : 1](https://www.hackingarticles.in/web-developer-1-vulnhub-lab-walkthrough/)
28.	[SP ike](https://www.hackingarticles.in/sp-ike-vulnhub-lab-walkthrough/)
29.	[DC-2](https://www.hackingarticles.in/dc-2-walkthrough/)
30.	[DC6](https://www.hackingarticles.in/dc6-lab-walkthrough/)
31.	[Born2Root2](https://www.hackingarticles.in/born2root-2-vulnhub-walkthrough/)
32.	[DC-4](https://www.hackingarticles.in/dc-4-vulnhub-walkthrough/)
33.	[Development](https://www.hackingarticles.in/development-vulnhub-walkthrough/)
34.	[Sputnik 1](https://www.hackingarticles.in/sputnik-1-vulnhub-walkthrough/)
35.	[PumpkinRaising](https://www.hackingarticles.in/pumpkinraising-vulnhub-walkthrough/)
36.	[Matrix-3](https://www.hackingarticles.in/matrix-3-vulnhub-walkthrough/)
37.	[symfonos : 2](https://www.hackingarticles.in/symfonos2-vulnhub-walkthrough/)
38.	[Digitalworld.local : JOY](https://www.hackingarticles.in/digitalworld-local-joy-vulnhub-walkthrough/)
39.	[PumpkinFestival](https://www.hackingarticles.in/mission-pumpkin-v1-0-pumpkinfestival-vulnhub-walkthrough/)
40.	[Sunset](https://www.hackingarticles.in/sunset-vulnhub-walkthrough/)
41.	[Ted:1](https://www.hackingarticles.in/ted1-vulnhub-walkthrough/)
42.	[CLAMP 1.0.1](https://www.hackingarticles.in/clamp-1-0-1-vulnhub-walkthrough/)
43.	[Torment](https://www.hackingarticles.in/digitalworld-localtorment-vulnhub-walkthrough/)
44.	[WestWild: 1.1](https://www.hackingarticles.in/westwild-1-1-vulnhub-walkthorugh/)
45.	[Broken: Gallery](https://www.hackingarticles.in/broken-gallery-vulnhub-walkthrough/)
<a name="suid"></a>
## SUID Bit

1.	[Tr0ll 1](https://www.hackingarticles.in/hack-the-troll-1-vm-boot-to-root/)
2.	[Mr. Robot](https://www.hackingarticles.in/hack-mr-robot-vm-ctf-challenge/)
3.	[Covfefe](https://www.hackingarticles.in/hack-covfefe-vm-ctf-challenge/)
4.	[Toppo:1](https://www.hackingarticles.in/hack-the-toppo1-vm-ctf-challenges/)
5.	[/dev/random : K2](https://www.hackingarticles.in/hack-the-dev-random-k2-vm-boot2root-challenge/)
6.	[FourAndSix : 2](https://www.hackingarticles.in/fourandsix-2-vulnhub-walkthrough/)
7.	[DC-1](https://www.hackingarticles.in/dc-1-vulnhub-walkthrough/)
8.	[digitalworld.local - BRAVERY](https://www.hackingarticles.in/digitalworld-local-bravery-vulnhub-walkthrough/)
9.	[Happycorp : 1](https://www.hackingarticles.in/happycorp1-vulnhub-walkthrough/)
10.	[MinU: v2](https://www.hackingarticles.in/minu-v2-vulnhub-walkthrough/)
11.	[hackme1](https://www.hackingarticles.in/hackme-1-vulnhub-walkthrough/)
12.	[dpwwn:2](https://www.hackingarticles.in/dpwwn2-vulnhub-walkthrough/)
13.	[Kevgir](https://www.hackingarticles.in/hack-kevgir-vm-ctf-challenge/)
<a name="kernel"></a>
## Kernel Exploit

1.	[LAMPSecurity: CTF 5](https://www.hackingarticles.in/hack-the-lampsecurity-ctf-5-ctf-challenge/)
2.	[pWnOS -1.0](https://www.hackingarticles.in/hack-the-pwnos-1-0-boot-to-root/)
3.	[Hackademic-RTB1](https://www.hackingarticles.in/hack-the-hackademic-rtb1-vm-boot-to-root/)
4.	[Kioptrix : Level 1.1](https://www.hackingarticles.in/hack-the-kioptrix-level-2-boot2root-challenge/)
5.	[Kioprtix: 5](https://www.hackingarticles.in/hack-the-kioptrix-5-ctf-challenge/)
6.	[SecOS: 1](https://www.hackingarticles.in/hack-the-secos1-ctf-challenge/)
7.	[Droopy](https://www.hackingarticles.in/hack-droopy-vm-ctf-challenge/)
8.	[Stapler](https://www.hackingarticles.in/hack-stapler-vm-ctf-challenge/)
9.	[Sidney](https://www.hackingarticles.in/hack-sydney-vm-ctf-challenge/)
10.	[Simple](https://www.hackingarticles.in/hack-simple-vm-ctf-challenge/)
11.	[VulnOS: 2.0](https://www.hackingarticles.in/hack-the-vulnos-2-0-vm-ctf-challenge/)
12.	[Lord of the Root](https://www.hackingarticles.in/hack-lord-root-vm-ctf-challenge/)
13.	[Acid Reloaded](https://www.hackingarticles.in/hack-acid-reloaded-vm-ctf-challenge/)
14.	[Pluck](https://www.hackingarticles.in/hack-pluck-vm-ctf-challenge/)
15.	[Fartknocker](https://www.hackingarticles.in/hack-fartknocker-vm-ctf-challenge/)
16.	[Nightmare](https://www.hackingarticles.in/hack-the-box-nightmare-walkthrough/)
17.	[Super Mario](https://www.hackingarticles.in/hack-super-mario-ctf-challenge/)
18.	[BTRSys:dv 2.1](https://www.hackingarticles.in/hack-btrsys-v2-1-vm-boot2root-challenge/)
19.	[Trollcave](https://www.hackingarticles.in/hack-the-trollcave-vm-boot-to-root/)
20.	[Golden Eye:1](https://www.hackingarticles.in/hack-the-golden-eye1-ctf-challenge/)
21.	[Lampiao : 1](https://www.hackingarticles.in/hack-the-lampiao-1-ctf-challenge/)
22.	[WinterMute : 1](https://www.hackingarticles.in/hack-the-wintermute-1-ctf-challenge/)
23.	[ch4inrulz : 1.0.1](https://www.hackingarticles.in/hack-the-ch4inrulz-1-0-1-ctf-challenge/)
24.	[Typhoon : 1.02](https://www.hackingarticles.in/typhoon-1-02-vulnhub-walkthrough/)
25.	[DC-3](https://www.hackingarticles.in/dc-3-walkthrough/)
26.	[DC-5](https://www.hackingarticles.in/dc-5-vulnhub-walkthrough/)
27. [GrimTheRipper:1](https://www.hackingarticles.in/grimtheripper-1-vulnhub-walkthrough/)
<a name="path"></a>
## Path Variable

1.	[PwnLab](https://www.hackingarticles.in/penetration-testing-pwnlab-ctf-challenge/)
2.	[Nullbyte](https://www.hackingarticles.in/hack-nullbyte-vm-ctf-challenge/)
3.	[USV](https://www.hackingarticles.in/hack-usv-2017-ctf-challenge/)
4.	[The Gemini inc](https://www.hackingarticles.in/hack-the-gemini-inc-ctf-challenge/)
5.	[Silky-CTF: 0x01](https://www.hackingarticles.in/silky-ctf-0x01-vulnhub-walkthrough/)
6.	[symfonos : 1](https://www.hackingarticles.in/symfonos1-vulnhub-walkthrough/)
7.	[Beast 2](https://www.hackingarticles.in/beast-2-vulnhub-walkthrough/)
8.	[Zeus:1](https://www.hackingarticles.in/zeus1-vulnhub-walkthrough/)
<a name="enum"></a>
## Enumeration

1.	[The Library:1](https://hackingarticles.in/the-library1-vulnhub-walkthrough/)
2.	[The Library:2](https://www.hackingarticles.in/the-library2-vulnhub-walkthrough/)
3.	[LAMPSecurity: CTF 4](https://www.hackingarticles.in/hack-the-lampsecurity-ctf4-ctf-challenge/)
4.	[LAMPSecurity: CTF 7](https://www.hackingarticles.in/hack-the-lampsecurity-ctf-7-ctf-challenge/)
5.	[LAMPSecurity: CTF 8](https://www.hackingarticles.in/hack-the-lampsecurity-ctf8-ctf-challenge-2/)
6.	[Xerxes: 1](https://www.hackingarticles.in/xerxes-1-vulnhub-walkthrough/)
7.	[pWnOS -2.0](https://www.hackingarticles.in/hack-the-pwnos-2-0-boot-2-root-challenge/)
8.	[DE-ICE:S1.130](https://www.hackingarticles.in/hack-the-de-ice-s1-130-boot2root-challenge/)
9.	[DE-ICE:S1.140](https://www.hackingarticles.in/hack-the-de-ice-s1-140-boot-to-root/)
10.	[Hackademic-RTB2](https://www.hackingarticles.in/hack-the-hackademic-rtb2-boot2root/)
11.	[SickOS 1.1](https://www.hackingarticles.in/hack-sickos-1-1-vm-ctf-challenge/)
12.	[Tommyboy](https://www.hackingarticles.in/hack-tommyboy-vm-ctf-challenge/)
13.	[Minotaur](https://www.hackingarticles.in/hack-minotaur-vm-ctf-challenge/)
14.	[VulnOS: 1](https://www.hackingarticles.in/hack-the-vulnos-1-ctf-challenge/)
15.	[Spyder Sec](https://www.hackingarticles.in/hack-spydersec-vm-ctf-challenge/)
16.	[Acid](https://www.hackingarticles.in/hack-acid-vm-ctf-challenge/)
17.	[Necromancer](https://www.hackingarticles.in/hack-necromancer-vm-ctf-challenge/)
18.	[Freshly](https://www.hackingarticles.in/hack-freshly-vm-ctf-challenge/)
19.	[Fortress](https://www.hackingarticles.in/hack-fortress-vm-ctf-challenge/)
20.	[Billu : B0x](https://www.hackingarticles.in/hack-billu-b0x-vm-boot2root-challenge/)
21.	[Defence Space](https://www.hackingarticles.in/hack-the-defense-space-vm-ctf-challengehack-defense-vm-ctf-challenge/)
22.	[Moria 1.1](https://www.hackingarticles.in/hack-moria-1-1-ctf-challenge/)
23.	[Analougepond](https://www.hackingarticles.in/hack-analougepond-vm-ctf-challenge/)
24.	[Lazysysadmin](https://www.hackingarticles.in/hack-lazysysadmin-vm-ctf-challenge/)
25.	[Bulldog](https://www.hackingarticles.in/hack-bulldog-vm-boot2root-challenge/)
26.	[BTRSys 1](https://www.hackingarticles.in/hack-btrsys1-vm-boot2root-challenge/)
27.	[G0rmint](https://www.hackingarticles.in/hack-g0rmint-vm-ctf-challenge/)
28.	[Blacklight : 1](https://www.hackingarticles.in/hack-the-blacklight-1-ctf-challenge/)
29.	[RootThis : 1](https://www.hackingarticles.in/hack-the-blacklight-1-ctf-challenge/)
30.	[Cyberry:1](https://hackingarticles.in/hack-vm-cyberry-1boot2root-challenge/)
<a name="mysql"></a>
## MySQL

1.	[Kioptrix : Level 1.3](https://www.hackingarticles.in/hack-the-kioptrix-level-1-3-boot2root-challenge/)
2.	[Raven](https://www.hackingarticles.in/hack-the-raven-walkthrough-ctf-challenge/)
3.	[Raven : 2](https://www.hackingarticles.in/raven-2-vulnhub-walkthrough/)
<a name="crontab"></a>
## Crontab

1.	[Billy Madison](https://www.hackingarticles.in/hack-billy-madison-vm-ctf-challenge/)
2.	[Born2root](https://www.hackingarticles.in/hack-born2root-vm-ctf-challenge/)
3.	[BSides Vancuver: 2018](https://www.hackingarticles.in/hack-the-bsides-vancouver2018-vm-boot2root-challenge/)
4.	[Jarbas : 1](https://www.hackingarticles.in/hack-the-jarbas-1-ctf-challenge/)
5.	[SP:Jerome](https://www.hackingarticles.in/spjerome-vulnhub-walkthrough/)
6.  [dpwwn: 1](https://www.hackingarticles.in/dpwwn-1-vulnhub-walkthrough/)
<a name="wild"></a>
## Wildcard Injection

1.	[Milnet](https://www.hackingarticles.in/hack-milnet-vm-ctf-challenge/)
2.	[Pipe](https://www.hackingarticles.in/hack-pipe-vm-ctf-challenge/)
<a name="capabilities"></a>
## Capabilities

1.	[Kuya : 1](https://www.hackingarticles.in/vulnhub-kuya-1-walkthrough/)
2.	[DomDom: 1](https://www.hackingarticles.in/domdom-1-vulnhub-walkthrough/)
<a name="etc"></a>

## Writable etc/passwd file

1.	[Hackday Albania](https://www.hackingarticles.in/hack-hackday-albania-vm-ctf-challenge/)
2.	[Billu Box 2](https://www.hackingarticles.in/hack-billu-b0x-vm-boot2root-challenge/)
3.	[Bulldog 2](https://www.hackingarticles.in/hack-the-bulldog2-ctf-challenge/)

<a name="root"></a>
## Writable files or script as root

1.	[Skydog](https://www.hackingarticles.in/hack-skydog-vm-ctf-challenge/)
2.	[Breach 1.0](https://www.hackingarticles.in/hack-breach-1-0-vm-ctf-challenges/)
3.	[Bot Challenge: Dexter](https://www.hackingarticles.in/hack-bot-challenge-dexter-boot2root-challenge/)
4.	[Fowsniff : 1](https://www.hackingarticles.in/fowsniff-1-vulnhub-walkthrough/)
5.	[Mercy](https://www.hackingarticles.in/mercy-vulnhub-walkthrough/)
6.	[Casino Royale](https://www.hackingarticles.in/casino-royale-1-vulnhub-walkthrough/)
7.	[SP eric](https://www.hackingarticles.in/sp-eric-vulnhub-lab-walkthrough/)
8.	[PumpkinGarden](https://www.hackingarticles.in/pumpkingarden-vulnhub-walkthrough/)
9.	[Tr0ll: 3](https://www.hackingarticles.in/tr0ll-3-vulnhub-walkthrough/)
10. [Nezuko:1](https://www.hackingarticles.in/nezuko-1-vulnhub-walkthrough/)
11. [Symfonos:3](https://www.hackingarticles.in/symfonos3-vulnhub-walkthrough/)
12. [AI: Web: 1](https://www.hackingarticles.in/ai-web-1-vulnhub-walkthrough/)
<a name="buffer"></a>
## Buffer Overflow

1.	[Tr0ll 2](https://www.hackingarticles.in/hack-the-tr0ll-2-boot2root-challenge/)
2.	[IMF](https://www.hackingarticles.in/hack-imf-vm-ctf-challenge/)
3.	[BSides London 2017](https://www.hackingarticles.in/hack-the-bsides-london-vm-2017boot2root/)
4.	[PinkyPalace](https://www.hackingarticles.in/hack-the-pinkypalace-vm-ctf-challenge/)
5.	[ROP Primer](https://www.hackingarticles.in/hack-the-rop-primer-1-0-1-ctf-challenge/)
6.  [CTF KFIOFAN:2](https://www.hackingarticles.in/ctf-kfiofan-2-vulnhub-walkthorugh/)
<a name="docker"></a>
## Docker

1.	[Donkey Docker](https://www.hackingarticles.in/hack-donkeydocker-ctf-challenge/)
2.	[Game of Thrones](https://www.hackingarticles.in/hack-game-thrones-vm-ctf-challenge/)
3.	[HackinOS : 1](https://www.hackingarticles.in/hackinos1-vulnhub-lab-walkthrough/)
