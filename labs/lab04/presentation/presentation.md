---
lang: ru-RU
title: Администрирование локальных сетей
subtitle: Первоначальная настройка коммутаторов (Лабораторная работа №4)
author:
  - Суннатилло Махмудов
date: 28 февраля 2026
toc: false
slide_level: 2
aspectratio: 169
section-titles: true
theme: metropolis
header-includes:
 - \metroset{progressbar=frametitle,sectionpage=progressbar,numbering=fraction}
---

# Цель работы

## Цель лабораторной работы
* Провести первоначальную настройку коммутаторов сети
* Настроить интерфейсы управления VLAN 2
* Обеспечить удалённый доступ по протоколу SSH

# Теоретическая часть

## Назначение коммутатора в сети
* Работает на канальном уровне (L2)
* Передаёт кадры на основе MAC-адресов
* Формирует таблицу коммутации
* Обеспечивает сегментацию доменов коллизий

## Управление коммутатором
* Настройка SVI (VLAN Interface)
* Назначение IP-адреса управления
* Настройка console и vty
* Включение SSH (RSA-ключи)

# Выполнение лабораторной работы

## Топология сети L1

![Топология сети L1](01.png){ width=80% }

## msk-donskaya-smahmudov-sw-1

* VLAN 2 — 10.128.1.2/24  
* Шлюз — 10.128.1.1  

![Настройка msk-donskaya-smahmudov-sw-1](02.png){ width=80% }

## msk-donskaya-smahmudov-sw-2

* VLAN 2 — 10.128.1.3/24  
* Шлюз — 10.128.1.1  

![Настройка msk-donskaya-smahmudov-sw-2](03.png){ width=80% }

## msk-donskaya-smahmudov-sw-3

* VLAN 2 — 10.128.1.4/24  
* Шлюз — 10.128.1.1  

![Настройка msk-donskaya-smahmudov-sw-3](04.png){ width=80% }

## msk-donskaya-smahmudov-sw-4

* VLAN 2 — 10.128.1.5/24  
* Шлюз — 10.128.1.1  

![Настройка msk-donskaya-smahmudov-sw-4](05.png){ width=80% }

## msk-pavlovskaya-smahmudov-sw-1

* VLAN 2 — 10.128.1.6/24  
* Шлюз — 10.128.1.1  

![Настройка msk-pavlovskaya-smahmudov-sw-1](06.png){ width=80% }

# Вывод

## Вывод

* Собрана топология сети L1
* Выполнена базовая настройка всех коммутаторов
* Настроены SVI VLAN 2 и IP-адреса управления
* Настроен защищённый удалённый доступ по SSH
* Конфигурации сохранены в энергонезависимой памяти