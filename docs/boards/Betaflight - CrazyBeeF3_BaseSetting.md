# 基本設定


![Betaflight 02](images/BF02m.png)


### ミキサー
プロペラの回転方向を示します。  
この設定を行うことで回転方向を変更するものではなく、あくまでもFC基板がその指定した回転数で処理を行うというパラメータとなります。実際の回転方向は、CrazyBeeF3のようなブラシレスモーターを利用する場合は、CW/CCW配線を入れ替えるか、ESC設定にて回転方向をノーマル/リバース設定に変更します。  
また回転方向を変更する場合は、プロペラ形状(向き)もご注意ください。


### ESC / モーター機能
* デジタル処理となるDSHOTプロトコルが選択できます。RPMフィルターを用いる場合はDSHOTを選択してください。Betaflight 4.0.6を使用する場合は【DSHOT300】、Betaflight 4.1.1 PEを使用する場合は【DSHOT150】を選択するとバランスが良いとされています。機体やモーター構成との兼ね合いで前後調整ください。
* 【MOTOR_STOP】はアーム時にプロペラを回すか回さないかを選択します。好みでお選びください。
* 【双方向DSHOT】はBetaflight 4.1.1 PEを利用する際は、是非お奨めの設定となります。BLHeli_M(JazzMarverick)、もしくはJESC ESCファームウェアを別途インストールしてください。
* 【モーター極数】はブラシレスモーター内のモーターベルに付随する磁石の数です。Happymodel 0603、0802モーターは【12】となります。
* 【モーターアイドルスロットル値】はスロットル最低値におけるプロペラのアイドリング強度となります。Betaflightのバージョン、プロトコル、双方向DSHOT等の設定により前後しますが、上記の設定とする場合には0603モーターの場合は6.4～6.6程度で調整してみてください。


### FCボード & センサーアライメント
* 【第1】ジャイロ/加速度
* 【CW 90°】第1ジャイロ


### アーミング
* 【180】アーム最大値
Flip over after crash(タートル)モードを利用する場合は、こちらを【180】と設定してください。


### システム設定
* 【2kHz】ジャイロ演算周波数
* 【2kHz】PIDループ演算周波数
Betaflight 4.0.6の場合は4k/4k





### メニュー
Betaflight (詳細設定) の項目は以下の通りです。必要なページをお選びください：  

* [セットアップ](Betaflight%20-%20CrazyBeeF3FR.md)
* [ポート](Betaflight%20-%20CrazyBeeF3_Port.md)
* [基本設定](Betaflight%20-%20CrazyBeeF3_BaseSetting.md)
* [電源・バッテリー](Betaflight%20-%20CrazyBeeF3_Battery.md)
* [フェイルセーフ](Betaflight%20-%20CrazyBeeF3_failsafe.md)
* [PIDチューニング](Betaflight%20-%20CrazyBeeF3_PID.md)
* [受信機](Betaflight%20-%20CrazyBeeF3_Reciever.md)
* [モード](Betaflight%20-%20CrazyBeeF3_Mode.md)
* [調整](Betaflight%20-%20CrazyBeeF3_Addjust.md)
* [サーボ](Betaflight%20-%20CrazyBeeF3_Servo.md)
* [モーター](Betaflight%20-%20CrazyBeeF3_Motor.md)
* [OSD](Betaflight%20-%20CrazyBeeF3_OSD.md)
* [映像伝送用送信機](Betaflight%20-%20CrazyBeeF3_VTX.md)
* [センサー](Betaflight%20-%20CrazyBeeF3_Sensor.md)
* [テザーロギング](Betaflight%20-%20CrazyBeeF3_logging.md)
* [ブラックボックス](Betaflight%20-%20CrazyBeeF3_Blackbox.md)
* [CLI コマンドライン](Betaflight%20-%20CrazyBeeF3_CLI.md)




