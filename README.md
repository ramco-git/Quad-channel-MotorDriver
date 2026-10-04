# Quad-channel-MotorDriver (超はんだもりもり森鴎外!）

クアッドチャネルのDCブラシ付きモータードライバ基板です。内臓MCUにSTM32F405RGT6を使用し、4つのエンコーダ入力と1つのUART、1つのclassic CANに対応しています。すべての通信線は5Vトレラントピンに接続されています。エンコーダはインクリメンタル式にのみ対応し、自己ゼロ校正も可能です。内部でのPID制御が可能なほか、外部から直接PWMとDIR信号を入力して動作させることもできます。

## 仕様
・MCUにSTM32F405RGT6を使用し、回転数、位置制御を基板単体で可能です。
| 機能 | 個数 | 備考 |
|-:|-|-|
| モータードライバ | 4 | 35V、連続10A(なお性能試験を行っていないため、詳細は不明) |
|　MCU | 1 | STM32F405RGT6 |
| ユーザーLED | 1 | RGBの一体型チップ |
| ユーザーボタン | 1 | CANのID設定などに使用 |


## 信号線とマイコンのピンアサイン、コネクタの種類、番号
 
| 機能 | ピン | コネクタ種類 | パッドナンバー | 備考 |
|-:|-|-|-|-|
| CAN | TX(PB9) RX(PB8) | JST-XA_4 | J18,J19 | 
| UART | TX(PB10) RX(PB11) | DF1BZ_4 | J6 |
| Encoder-1 | A(PA8) B(PA9) Z(PC0) | JST-PA_5 | J1 | TIM1 |
| Encoder-2 | A(PA0) B(PA1) Z(PC1) | JST-PA_5 | J2 | TIM2 |
| Encoder-3 | A(PA6) B(PA7) Z(PC2) | JST-PA_5 | J3 | TIM3 |
| Encoder-4 | A(PB6) B(PB7) Z(PC3) | JST-PA_5 | J4 | TIM4 |
| PWM-1(From built in MCU | PWM(PC6) DIR(PB12) | - | - | TIM8-CH1 |
| PWM-2(From built in MCU | PWM(PC7) DIR(PB13) | - | - | TIM8-CH2 |
| PWM-3(From built in MCU | PWM(PC8) DIR(PA10) | - | - | TIM8-CH3 |
| PWM-4(From built in MCU | PWM(PC9) DIR(PA11) | - | - | TIM8-CH4 |
| PWM-1(From external input) | - | - | J14 | - |
| PWM-2(From external input) | - | - | J15 | - |
| PWM-3(From external input) | - | - | J16 | - |
| PWM-4(From external input) | - | - | J17 | - |
| Power-IN | 12V(Not connected) 5V(2) GND(3)
| ユーザーLED | Red(PB14) Green(PA3) Blue(PB15) | | D2 | TIMに接続されている |
| ユーザーボタン | (PC15) | - | SW2 | - | プルアップ入力 |

## 名前の由来
大電流に対応させるため、銅線を基板にはんだ付けした。その結果、基板がはんだだらけになってしまった。「超」はんだもりもり森鷗外!が誕生した。
