---
## Front matter
title: "Отчёт по лабораторной работе 4"
subtitle: "Первоначальное конфигурирование сети"
author: "Суннатилло Махмудов"

## Generic otions
lang: ru-RU
toc-title: "Содержание"

## Bibliography
bibliography: bib/cite.bib
csl: pandoc/csl/gost-r-7-0-5-2008-numeric.csl

## Pdf output format
toc: true # Table of contents
toc-depth: 2
lof: true # List of figures
lot: true # List of tables
fontsize: 12pt
linestretch: 1.5
papersize: a
documentclass: scrreprt
## I18n polyglossia
polyglossia-lang:
  name: russian
  options:
	- spelling=modern
	- babelshorthands=true
polyglossia-otherlangs:
  name: english
## I18n babel
babel-lang: russian
babel-otherlangs: english
## Fonts
mainfont: IBM Plex Serif
romanfont: IBM Plex Serif
sansfont: IBM Plex Sans
monofont: IBM Plex Mono
mathfont: STIX Two Math
mainfontoptions: Ligatures=Common,Ligatures=TeX,Scale=0.94
romanfontoptions: Ligatures=Common,Ligatures=TeX,Scale=0.94
sansfontoptions: Ligatures=Common,Ligatures=TeX,Scale=MatchLowercase,Scale=0.94
monofontoptions: Scale=MatchLowercase,Scale=0.94,FakeStretch=0.9
mathfontoptions:
## Biblatex
biblatex: true
biblio-style: "gost-numeric"
biblatexoptions:
  - parentracker=true
  - backend=biber
  - hyperref=auto
  - language=auto
  - autolang=other*
  - citestyle=gost-numeric
## Pandoc-crossref LaTeX customization
figureTitle: "Рис."
tableTitle: "Таблица"
listingTitle: "Листинг"
lofTitle: "Список иллюстраций"
lotTitle: "Список таблиц"
lolTitle: "Листинги"
## Misc options
indent: true
header-includes:
  - \usepackage{indentfirst}
  - \usepackage{float} # keep figures where there are in the text
  - \floatplacement{figure}{H} # keep figures where there are in the text
---

# Цель работы

Провести подготовительную работу по первоначальной настройке коммутаторов сети.

# Теоретические сведения

Локальная вычислительная сеть (LAN) представляет собой совокупность взаимосвязанных устройств, обменивающихся данными по каналам связи. Передача информации в сети осуществляется в виде кадров и пакетов, проходящих через различные уровни модели OSI. В данной работе рассматривались принципы взаимодействия устройств на физическом, канальном и сетевом уровнях.

Концентратор (hub) работает на физическом уровне и передаёт входящий сигнал на все порты без анализа содержимого. Все устройства, подключённые к концентратору, используют общий канал передачи данных, поэтому в такой сети возможны коллизии — ситуации, когда несколько устройств одновременно начинают передачу.

Коммутатор (switch) функционирует на канальном уровне и передаёт кадры на основе MAC-адресов. Он запоминает соответствие MAC-адресов и портов в таблице коммутации и направляет данные только нужному получателю. Это уменьшает количество лишнего трафика и практически устраняет коллизии.

Маршрутизатор (router) работает на сетевом уровне и обеспечивает передачу пакетов между различными IP-сетями. Он анализирует IP-адреса источника и назначения и выбирает оптимальный путь доставки данных.

# Выполнение лабораторной работы

1. В логической рабочей области Packet Tracer размещены коммутаторы и оконечные устройства согласно схеме сети L1. Все устройства соединены через соответствующие интерфейсы в соответствии с топологией.

![Топология сети L1](01.png){ #fig:001 width=80% }

2. Выполнена базовая настройка коммутатора **msk-donskaya-smahmudov-sw-1**.  
Настроен интерфейс управления **VLAN 2** с IP-адресом 10.128.1.2/24, задан шлюз по умолчанию 10.128.1.1.  
Настроены линии console и vty, включено шифрование паролей, создан пользователь admin, настроен доступ по SSH.

![Настройка msk-donskaya-smahmudov-sw-1](02.png){ #fig:002 width=80% }

3. Выполнена настройка коммутатора **msk-donskaya-smahmudov-sw-2**.  
Интерфейс VLAN 2 — 10.128.1.3/24, шлюз 10.128.1.1.  
Настроены параметры удалённого доступа и сохранена конфигурация.

![Настройка msk-donskaya-smahmudov-sw-2](03.png){ #fig:003 width=80% }

4. Выполнена настройка коммутатора **msk-donskaya-smahmudov-sw-3**.  
Интерфейс VLAN 2 — 10.128.1.4/24, шлюз 10.128.1.1.  
Настроены линии доступа и включён SSH.

![Настройка msk-donskaya-smahmudov-sw-3](04.png){ #fig:004 width=80% }

5. Выполнена настройка коммутатора **msk-donskaya-smahmudov-sw-4**.  
Интерфейс VLAN 2 — 10.128.1.5/24, шлюз 10.128.1.1.  
Настроены параметры управления и выполнено сохранение конфигурации.

![Настройка msk-donskaya-smahmudov-sw-4](05.png){ #fig:005 width=80% }

6. Выполнена настройка коммутатора **msk-pavlovskaya-smahmudov-sw-1**.  
Интерфейс VLAN 2 — 10.128.1.6/24, шлюз 10.128.1.1.  
Настроены линии доступа, включено шифрование паролей и SSH.

![Настройка msk-pavlovskaya-smahmudov-sw-1](06.png){ #fig:006 width=80% }

# Вывод

В ходе лабораторной работы была выполнена сборка топологии сети L1 в среде Cisco Packet Tracer и произведена базовая настройка коммутаторов. Для всех устройств настроены интерфейсы управления VLAN 2, назначены IP-адреса согласно плану адресации и задан шлюз по умолчанию.
На коммутаторах настроены параметры локального и удалённого доступа: пароли для console и vty, enable secret, включено шифрование паролей, создан пользователь admin и настроен доступ по протоколу SSH с генерацией RSA-ключей.
В результате работы обеспечено централизованное управление коммутаторами по защищённому протоколу SSH и подготовлена рабочая инфраструктура для дальнейшей настройки и тестирования сети.

# Контрольные вопросы

1. **При помощи каких команд можно посмотреть конфигурацию сетевого оборудования?**  

   Для просмотра текущей конфигурации используется команда:  
   – `show running-config` — отображает активную (текущую) конфигурацию, загруженную в оперативную память.  

   Также применяются вспомогательные команды:  
   – `show ip interface brief` — краткая информация об интерфейсах;  
   – `show vlan` — просмотр VLAN;  
   – `show mac address-table` — таблица MAC-адресов (для коммутаторов).

2. **При помощи каких команд можно посмотреть стартовый конфигурационный файл оборудования?**  

   Для просмотра сохранённой конфигурации, находящейся в энергонезависимой памяти (NVRAM), используется команда:  
   – `show startup-config`.

3. **При помощи каких команд можно экспортировать конфигурационный файл оборудования?**  

   Экспорт конфигурации (копирование во внешнее хранилище или на сервер) выполняется командой:  
   – `copy running-config tftp`  
   – `copy startup-config tftp`  

   Также возможны варианты:  
   – `copy running-config ftp`  
   – `copy running-config usbflash0:`  

4. **При помощи каких команд можно импортировать конфигурационный файл оборудования?**  

   Импорт конфигурации выполняется копированием файла с внешнего носителя или сервера:  
   – `copy tftp running-config`  
   – `copy tftp startup-config`  
   – `copy usbflash0:filename startup-config`  

   После загрузки конфигурации в running-config при необходимости её сохраняют командой:  
   – `write memory` или `copy running-config startup-config`.
	
# Список литературы

1. 802.1D-2004 - IEEE Standard for Local and Metropolitan Area Networks. Media Access Control (MAC) Bridges : тех. отч. / IEEE. — 2004. — С. 1— 277. — DOI: 10.1109/IEEESTD.2004.94569. — URL: http://ieeexplore.ieee.org/servlet/opac?punumber=9155.

2. 802.1Q - Virtual LANs. — URL: http://www.ieee802.org/1/pages/802.1Q.html.

3. A J. Packet Tracer Network Simulator. — Packt Publishing, 2014. — ISBN 9781782170426. — URL: https://books.google.com/books?id=eVOcAgAAQBAJ&dq=cisco+packet+tracer&hl=es&source=gbs_navlinks_s