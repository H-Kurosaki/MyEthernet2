このライブラリはWiz550ioの機能を有効に活用するためにEthernet2ライブラリVer1.0.3から改変し分岐させたものです。
Wiz550ioのROMに書き込まれた内蔵MACアドレス設定機能を有効化しています。
MACアドレスをソースコード上にハードコーディングしなくても自動的に正しいMACアドレスが割り当てられます。

元々のEthernet2ライブラリはArduinoにおいてW5500を搭載したイーサネット通信機能を動作させるためのものです。
Ver1.0.3とVer1.0.4以降ではROMにMACアドレスが書き込まれたW5500に対する動作に違いがあります。
Ver1.0.3では内蔵MACアドレスを利用できます。これはVer1.0.3の隠し機能として実装されていました。
しかし、Ver1.0.4以降では内蔵MACアドレスが無視されます。
この問題はROMにMACアドレスが書き込まれたWiz550ioを利用するときに発生します。
(Ethernet Shield2ではROMにMACアドレスが書かれていません。ステッカーに記載されているだけです)

Ethernet2ライブラリを最新版にアップデートすると内蔵MACアドレスを利用できなくなります。
この問題を解決するためVer1.0.3から分岐したのがこのMyEthernet2ライブラリです。
Ethernet2ライブラリと共存するために全てのファイル名を書き換えてあります。

既知の問題

このライブラリを用いる場合、ソフトウェア上でEthernetの初期化は1回しかできません。
Ethernetの初期化を複数回行うと異常な動作をします。
Ethernetを再初期化する場合はW5500にハードウェアリセットをかけてください。
なお、この問題はEthernet2ライブラリVer1.0.4では発生しません。

This library is a modified and branched version of Ethernet2 library Ver1.0.3 in order to make effective use of Wiz550io's functions.
It enables the built-in MAC address setting function written in the ROM of Wiz550io.
It automatically assigns the correct MAC address without hardcoding the MAC address in the source code.

The original Ethernet2 library is for running the Ethernet communication function with W5500 on Arduino.
There is a difference between Ver1.0.3 and Ver1.0.4 or later in the behavior of the W5500 with the MAC address written in ROM.
In Ver1.0.3, the built-in MAC address can be used. This was implemented as a hidden function in Ver1.0.3.
However, in Ver 1.0.4 and later, the built-in MAC address is ignored.
This problem occurs when you use Wiz550io with MAC address written in ROM.
(Ethernet Shield2 does not have the MAC address written in ROM. It is just written on a sticker.)

If you update the Ethernet2 library to the latest version, you will not be able to use the built-in MAC address.
To solve this problem, this MyEthernet2 library was branched from Ver1.0.3.
All file names have been rewritten to coexist with the Ethernet2 library.

Known problems
If you use this library, you can initialize Ethernet only once in the software.
If you initialize Ethernet multiple times, it will behave abnormally.
To reinitialize Ethernet, please perform a hardware reset on the W5500.
Please note that this problem does not occur in Ethernet2 library Ver1.0.4.


以下に古いREADME.mdの記述を残しておきます。
The old description of README.md is left as follows.

-----------------------------------------------------------------------------------------------------


Ethernet "2" Library for WIZNET 5500 ONLY!
========

doesn't work with other chipsets :)

Arduino
========

* Arduino is an open-source tool used for building electronics projects. Arduino consists of a physical programmable circuit board (often referred to as a micro-controller) and a development environment, or IDE (Integrated Development Environment) that runs on your computer, used to write and upload computer code to the board

* For more information, please consult the website at: http://www.arduino.org/

* To report a *bug* in the software or to request *a simple enhancement*, please go to:
http://github.com/arduino-org/Arduino/issues

If you're interested in modifying or extending the [Arduino.org](http://arduino.org) software, we would be very happy if you did it! If you want to integrate your work into the official release please create a pull request at : https://github.com/arduino-org/Arduino/compare/

If you're interested in collaborating please contact us!

Installation
------------
Ready-to-run software and instructions are available on : http://www.arduino.org/downloads

[Arduino.org](http://arduino.org) IDE is at this time developed, maintained and supported by the Arduino.org team: [support@arduino.org](mailto:support@arduino.org)

Credits
--------
[Arduino.org](http://arduino.org) is an open source project, developed by many and based on:

* The Arduino.cc IDE: http://www.arduino.cc/ 
* The Wiring project: http://www.wiring.org.co/
* The Processing project: http://processing.org

A special thanks to  Daniela Antonietti, Hernando Barragán, David Cuartielles, Ben Fry, Tom Igoe, Gianluca Martino, David A. Mellis, Massimo Banzi and Casey Reas for their works and inspirations.

Arduino uses the [GNU avr-gcc toolchain](http://gcc.gnu.org/wiki/avr-gcc), [avrdude](http://www.nongnu.org/avrdude/), [avr-libc](http://www.nongnu.org/avr-libc/), and code from
[Processing](http://www.processing.org) and [Wiring](http://wiring.org.co).

Icon and about image designed by [ToDo](http://www.todo.to.it/)
