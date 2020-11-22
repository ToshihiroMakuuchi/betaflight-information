# CrazyBee F3 FR
![CrazyBee F3 FR front](images/CrazyBeeF3FRtop.jpg)
![CrazyBee F3 FR back](images/CrazyBeeF3FRbottom.jpg)

## FCボードの説明
CrazyBee F3 フライトコントローラーは、1S専用TinyWhoop向けブラシレスレーシングドローン用の高集積FCボードです。
世界で初めて、4in1タイプ受信機とESC/OSD/電流計を内蔵した小型ブラシレスフライトコントローラーと言われています。
URUAV UR65(FrSky)に搭載されたが最初となり、リプレースパーツとしてHappymodelが基板単体で発売しました。

## MCU・センサー類と機能について

### ハードウェアと機能

  - MCU: STM32F303CCT6
  - IMU: MPU6000 (SPI) 
  - IMU割込: 有効
  - 仮想COMポート(VCP): 有り
  - OSD: Betaflight標準OSD対応
  - バッテリー電圧センサー: 有り
  - オンボード電圧レギュレーター: 有効, booster, 5V/800mA
  - オンボード現行センサー：最大 14A (抵抗変更改造により28Aまでアップ可能)
  - オンボード受信機: Frsky/S-FHSS互換受信機 (CC2500チップ) ※Frsky_D(D8) Frsky_X(D16) S-FHSS(BF4.0.X以降で対応)
  - Buttons: 1 (受信機 Bindボタン) ※Bootボタンはありません
  - オンボードESC: 4x Blheli_s Max 5A per ESC
  - ESCコネクタ: 3-pin, PicoBlade 1.25mm pitch
  - ブザー出力: 2-pin, soldering pad
  - オンボードLED: 4LED (受信機用 赤x2 白x2)

## リソースマッピング

| Label                      | Pin | Timer  | DMA | Default     | Note                             |
|----------------------------|------|-------|-----|-------------|----------------------------------|
| MPU6000_INT_EXTI           | PC13 |       |     |             |                                  |
| MPU6000_CS_PIN             | PA4  |       |     |             |    SPI1                          |
| MPU6000_SCK_PIN            | PA5  |       |     |             |    SPI1                          |
| MPU6000_MISO_PIN           | PA6  |       |     |             |    SPI1                          |
| MPU6000_MOSI_PIN           | PA7  |       |     |             |    SPI1                          |
| OSD_CS_PIN                 | PB1  |       |     |             |    SPI1                          |
| OSD_SCK_PIN                | PA5  |       |     |             |    SPI1                          |
| OSD_MISO_PIN               | PA6  |       |     |             |    SPI1                          |
| OSD_MOSI_PIN               | PA7  |       |     |             |    SPI1                          |
| RX_CS_PIN                  | PB12 |       |     |             |    SPI2                          |
| RX_SCK_PIN                 | PB13 |       |     |             |    SPI2                          |
| RX_MISO_PIN                | PB14 |       |     |             |    SPI2                          |
| RX_MOSI_PIN                | PB15 |       |     |             |    SPI2                          |
| RX_GDO0_PIN                | PA8  |       |     |             |                                  |
| RX_BIND_PIN                | PA9  |       |     |             |                                  |
| RX_LED_PIN                 | PA10 |       |     |             |                                  |
| PWM1                       | PB8  | TIM8, CH2 | |             |                                  |
| PWM2                       | PB9  | TIM8, CH3 | |             |                                  |
| PWM3                       | PA3  | TIM2, CH4 | |             |                                  |
| PWM4                       | PA2  | TIM15,CH1 | |             |                                  |
| VBAT_ADC_PIN               | PA0  |       |     |             |      ADC1                        |
| RSSI_ADC_PIN               | PA1  |       |     |             |      ADC1                        |
| BEEPER                     | PC15 |       |     |             |                                  |
| UART3 TX                   | PB10 |       |     |             |      will add pinout soon        |
| UART3 RX                   | PB11 |       |     |             |      will add pinout soon        |


## メーカー・販売店

https://www.banggood.com/Racerstar-Crazybee-F3-Flight-Controller-4-IN-1-5A-1S-Blheli_S-ESC-Compatible-Frsky-D8-Receiver-p-1262972.html

## デザイナー情報

## 管理者情報

## FAQ と周知の問題

 - FCボードの仕様では、DSHOT600対応と謳っていますが、Type-L(BB1 24MHz)のESCを使用しているため、DSHOT300しか確実に対応していません。そのため、DSHOT600を適用した場合にはESCの制御信号がどれだけ正確なものとなるかは未知数です。これについての過去の議論は https://www.rcgroups.com/forums/showthread.php?3036325-Racerstar-Crazybee-F3-Ultimate-Micro-AIO-FC%21-1S-5A-BlheliS-Frsky-Flysky-OSD/page3 を参照してください。
- 工場出荷時のデフォルトのジャイロ / PIDループ演算周波数は8KHz / 2KHzとなっています。ですがこれは不安定になる可能性があり、4KHz / 4KHz以下を推奨との報告がありますので、こちらも参考としてください。


Betaflight 3.3.X(工場出荷時)の具体的な情報：

- DSHOTブザー機能は機能しません。
- タートルモード(Flip over after Crash)が有効な場合、FCボードはフェイルセーフのタイムアウトが1s (10 * 0.1s) 以上の場合にのみ作動します。タイムアウトが1s以下に設定されている場合、モーターがすぐにスピンアップして停止する状態が確認され、その後、機体ははアームできなくなります。これの問題は、BF3.4以降で修正されました。
- BetaflightはF3チップのサポートをBF4.0.6にて終了しました。そのため、BF4.0.6を採用することを推奨致します。


FRSKY バージョン:

- FrSky送信機(Taranisシリーズ)にバインドするためには、non-eu OpenTXバージョンを適用している必要があります。また工場出荷時のBetaflightの受信モードは『FRSKY_X』の場合が多いので、必要に応じて忘れずに設定してください。
- FrSky_X(8/16ch)、FrSky_D(8ch)はテレメトリー機能を無効している場合においては、Crash flip / Dshotビーコンとの組み合わせも含め、信頼性の高い動作が確認されています。テレメトリー機能を無効にしても、RSSIやバッテリー電圧などの基本的なテレメトリー情報はOSDに送信されます。
- FrSky_Dテレメトリー機能は、センサー数(BARO、GPS、...)に応じ時折信号のドロップアウトを引き起こし、信号タイミングと出力がずれててしまいます。(BF3.4以降にてバグフィクスされました)
- FrSky_Xテレメトリー機能は、テレメトリー生成コードのバグのためハードロックアップを引き起こします。(BF4.0.6にてバグフィクスされました https://github.com/betaflight/betaflight/pull/8702)


## その他の情報
   ユーザマニュアル: http://img.banggood.com/file/products/20180209021414Crazybeef3.pdf

