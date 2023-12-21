# mk_23_kr
# Курсовые работы по дисциплине "Микроконтроллеры мехатронных устройств"
## Автор: Способова Ю.П.
### Используемое ПО
1. arm-none-eabi-g++ --- кросс-компилятор.
1. make --- система сборки проекта.
1. cmake --- система управления проектом.
1. git --- система контроля версий.

Настройка проекта:
     cmake -B build

Сборка проекта:
    cmake --build build

Прошивка МК:
    cmake --install build


 Переферия:
 1.Интерфейс связи с другими модулями робота - SPI  

     SCK (PB10) - тактирование (синхронизация)
     MOSI (PC3) - выход данных ведущего
     MISO (PC2) - вход данных ведущего 
     CS (PB9) - выбор ведомого

 2.Интерфейс связи с ПК - Ethernet подключается к МК через модуль (Lan8720)
 3.Программатор МК - JTAG(20 pin)
    
    TDI (PA15) — Test Data Input — сигнал данных на вход, данные задвигаются по переднему фронту TCK.
    TDO (PB3) — Test Data Output — выход последовательных данных JTAG, выдвигаются по заднему фронту TCK, должен находиться в третьем состоянии — Z — когда данные не передаются.
    TMS (PA13) — Test Mode Select — сигнал управления TAP — контроллером.
    TRST (PB14) — Test Reset — не всегда есть, так как ресета можно добиться удерживая некоторое время TMS = 1, активный уровень сигнала — 0.
    TCK (PA14) — Test Clock — тактовая частота.

 4.Индикация: 

    Звуковая индикация (OLED96) 
        SDA(PB7) - линия данных 
        SCL(PB6) - линия тактирования 
    ЖКИ символьный Winstar
        SDA(PA8) - линия данных
        SCL(PA9) - линия тактирования

 5.Датчик - Arduino Water Sensor подключается через неинвертирующий операционный усилитель (Lm358) потом к МК

 6.Питание 12 вольт которые преобразуются черес DC DC преобразователь(MP9943)   
    





