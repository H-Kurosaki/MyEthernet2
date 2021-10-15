このライブラリはWiz550ioの機能を有効に活用するためにEthernet2ライブラリ(https://github.com/adafruit/Ethernet2 )を改変したものです。
Wiz550ioのROMに書き込まれた内蔵MACアドレス設定機能を有効化しています。
MACアドレスをソースコード上にハードコーディングしなくても自動的に正しいMACアドレスが割り当てられます。

元々のEthernet2ライブラリはArduinoにおいてW5500を搭載したイーサネット通信機能を動作させるためのものです。
Ver1.0.3とVer1.0.4以降ではROMにMACアドレスが書き込まれたW5500に対する動作に違いがあります。
Ver1.0.3では内蔵MACアドレスを利用できます。これはVer1.0.3の隠し機能として実装されていました。
しかし、Ver1.0.4以降では内蔵MACアドレスが無視されます。
この問題はROMにMACアドレスが書き込まれたWiz550ioを利用するときに発生します。
(Ethernet Shield2ではROMにMACアドレスが書かれていません。ステッカーに記載されているだけです)

Ethernet2ライブラリを最新版にアップデートすると内蔵MACアドレスを利用できなくなります。
この問題を解決するため分岐したのがこのMyEthernet2ライブラリです。
Ethernet2ライブラリと共存するために全てのファイル名を書き換えてあります。

既知の問題

コンパイルのときに警告が出ますが実害は無いようです。

このライブラリを用いる場合、ソフトウェア上でEthernetの初期化は1回しかできません。
Ethernetの初期化を複数回行うと異常な動作をします。
Ethernetを再初期化する場合はW5500にハードウェアリセットをかけてください。
なお、この問題はEthernet2ライブラリVer1.0.4では発生しません。

This library is a modified and branched version of Ethernet2 library(https://github.com/adafruit/Ethernet2 ) in order to make effective use of Wiz550io's functions.
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

When you compile it, you will get a warning, but there seems to be no real harm.

If you use this library, you can initialize Ethernet only once in the software.
If you initialize Ethernet multiple times, it will behave abnormally.
To reinitialize Ethernet, please perform a hardware reset on the W5500.
Please note that this problem does not occur in Ethernet2 library Ver1.0.4.

-----------------------------------------------------------------------------------------------------
License
Copyright (c) 2009-2016 Arduino LLC. All right reserved.

This library is free software; you can redistribute it and/or modify it under the terms of the GNU Lesser General Public License as published by the Free Software Foundation; either version 2.1 of the License, or (at your option) any later version.

This library is distributed in the hope that it will be useful, but WITHOUT ANY WARRANTY; without even the implied warranty of MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE. See the GNU Lesser General Public License for more details.

You should have received a copy of the GNU Lesser General Public License along with this library; if not, write to the Free Software Foundation, Inc., 51 Franklin St, Fifth Floor, Boston, MA 02110-1301 USA

