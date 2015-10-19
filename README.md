﻿Контроллер температуры на ATMega328p/Arduino
============================================

Состоит из двух блоков:
1) На основе обычного термометра. Нет блока питания. Добавлены
   пьезопищалка и шина RJ-11 для связи со вторым блоком и получения
   от него питания;
2) Блок с:
   - преобразователем питания (переменные 220В в постоянные 5В)
     и соответствующей вилкой для подключения к сети 220В;
   - реле для управления нагревателем и соответствующей розеткой
     для подключения нагревателя;
   - двумя термодатчиками: внешним (для контроля температуры
     во внешней среде) и внутренним (внутри первого блока для
     измерения комнатной температуры);
   - двумя светодиодами для визуального контроля работы блока
     (зелёный - включен в сеть, питание 5В поставляется; красный -
     нагреватель включен);
   - каналом связи RJ-11 для связи с первым блоком и передачи
     питания ему.

Описание портов:
B0-B7 - аноды индикатора в последовательности B-G-C-Dp-D-E-A-F
        (для PORTB: F-A-E-D-Dp-C-G-B)
C2-C5 - катоды индикаторы в последовательности D4-D3-D2-D1
        (для PORTC: x-x-D1-D2-D3-D4-x-x)
D0-D3 - кнопки в последовательности [1]-[2]-[3]-[4]
        (для PORTD: x-x-x-x-[4]-[3]-[2]-[1])
D4    - канал управления реле 220В
D6    - пьезоизлучатель звука BUZZER
        (для PORTD: x-BUZ-x-x-x-x-x-x)
D7    - температурные датчики DS18B20
        (для PORTD: DS-x-x-x-x-x-x-x)