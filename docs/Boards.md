# フライトコントローラのハードウェアについて

現在のターゲットは、STM32F303 および STM32F4 シリーズプロセッサを使用するフライトコントローラハードウェアを対象としています。コアロジックはハードウェアドライバから分離されており、他のプロセッサへの移植が可能です。

Betaflight の現行バージョンの利用をご希望の場合は、256KB のフラッシュメモリを搭載した STM32 F4 および STM32 F7 ベースのFCボードをお勧めします。F4、F7プロセッサは、より高速でUSBサポートを内蔵しており、追加のデバイスを必要とせずに、より多くのハードウェアをサポートします。

推奨されるボードのコアセットは以下の通りです：

* [CrazyBee F4 FR Pro](boards/Board%20-%20CrazyBeeF4FRPro.md) ※未編集
* [CrazyBee F4 FS Pro](boards/Board%20-%20CrazyBeeF4FSPro.md) ※未編集
* [CrazyBee F4 DX Pro](boards/Board%20-%20CrazyBeeF4DXPro.md) ※未編集


レガシーボードのコアセットは以下の通りです：

* [CrazyBee F3 FR](boards/Board%20-%20CrazyBeeF3FR.md) ※2020/11/29 絶賛作成中！
* [CrazyBee F3 FS](boards/Board%20-%20CrazyBeeF3FS.md) ※未編集
* [Seriously Pro SPRacingF3](boards/Board%20-%20SPRacingF3.md) ※未編集
* [Seriously Pro SPRacingF3Mini](boards/Board%20-%20SPRacingF3MINI.md) ※未編集
* [Seriously Pro SPRacingF3EVO](boards/Board%20-%20SPRacingF3EVO.md) ※未編集
* [Seriously Pro SPRacingF3NEO](boards/Board%20-%20SPRacingF3NEO.md) ※未編集


備考: CPU の EEPROM 容量が 256KB 未満のボードを使用している場合、使用可能な機能が制限される可能性があります。
備考：ハードウェア開発者は、256KB未満のEEPROMスペースを持つCPUを持つ新しいボードを設計すべきではありません。

各FCボードには長所・短所がそれぞれあり、ハードウェアを購入する前にチェックすべき主な事の一つとして、FCボード上で同時に使用する十分なシリアルポート数と入出力ピンが提供されているかを確認してください。FCボードの特性により、いくつかの機能は排他的な場合があります。

配線の詳細については、FCボード固有のマニュアルを参照してください。
必要に応じて、受信機やブザーなど、Betaflight で動作することが知られている他のハードウェアへのリンクも提供しています。

