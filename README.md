# 8-Sensor Environmental Monitoring Board(2026.01.02~01.13)
**8종 센서 통합 환경 모니터링 보드 (Arduino Mega Shield)**

> 대기질·기상 8종 센서를 하나의 보드에 통합한 환경 모니터링 시스템.
> I2C·UART·아날로그·RS485 등 서로 다른 인터페이스를 핀 충돌 없이 정리하고,
> Arduino Mega 쉴드 형태의 커스텀 PCB로 설계했습니다.

<img src="https://github.com/user-attachments/assets/4afbdc7a-31b7-4157-955c-13662517119f" alt="완성 보드 3D 앞면" width="60%">

## 개요
대기질과 기상 환경을 동시에 측정하기 위해 8종의 센서를 통합한 보드입니다.
센서마다 통신 방식과 전원 요구가 달라, 이를 한 보드에서 충돌 없이
운용하도록 핀 배치·전원 계통·통신 채널을 설계했습니다.

## 통합 센서
| 분류 | 센서 | 측정 항목 | 인터페이스 |
|---|---|---|---|
| 대기질 | MQ-4 | 메탄(CH₄) | Analog |
| 대기질 | MQ-131 | 오존(O₃) | Analog |
| 대기질 | MH-Z19C | 이산화탄소(CO₂) | UART |
| 대기질 | PMS9103M | 미세먼지 | UART |
| 대기질 | SGP40 | VOC | I2C |
| 환경 | GY-BME280 | 온·습도·기압 | I2C |
| 기상 | RS485 풍향계 | 풍향 | RS485 |
| 기상 | RS485 풍속계 | 풍속 | RS485 |

## 설계 포인트
- **다중 인터페이스 통합**: I2C(주소 공유) · UART ×3(Serial1~3) · 아날로그 · RS485를 한 보드에 정리
- **전원 계통 분리**: 5V 로직 / 12V 센서(RS485) 전원 구분
- **Mega 쉴드 구조**: Arduino Mega에 결합하는 쉴드 형태, 육각형 커스텀 외형
- **핀맵 문서화**: 센서별 핀 배치를 표로 정리해 조립·디버깅 편의 확보

## 완성된 보드

| 앞면 (3D) | 뒷면 (3D) |
|:---:|:---:|
| <img src="https://github.com/user-attachments/assets/4afbdc7a-31b7-4157-955c-13662517119f" alt="3D 앞면" width="100%"> | <img src="https://github.com/user-attachments/assets/fd4f30b6-88eb-43f2-8890-0b92058b3fcd" alt="3D 뒷면" width="100%"> |

## 설계 과정

1. 센서별 인터페이스·전원 요구 분석 및 핀맵 설계
2. 배선도 작성 → 회로 설계 (스키매틱)
3. PCB 레이아웃 — Mega 쉴드 형태, 육각형 외형
4. 3D 뷰로 부품 배치·풋프린트 검증

| 핀맵 | 배선도 |
|:---:|:---:|
| <img src="https://github.com/user-attachments/assets/604fae71-3669-4aca-bf29-917c0f4d8e17" alt="핀맵 표" width="100%"> | <img src="https://github.com/user-attachments/assets/95e67b04-8a5a-4baa-9e12-87cac1b05582" alt="배선도" width="100%"> |

| 회로 설계 (Schematic) | PCB 레이아웃 |
|:---:|:---:|
| <img src="https://github.com/user-attachments/assets/304ad394-a76e-4aa4-b7c8-93e291a11905" alt="스키매틱" width="100%"> | <img src="https://github.com/user-attachments/assets/7a00b910-c744-43b7-9cfb-89a637af9ebe" alt="PCB 레이아웃" width="100%"> |

## 회고
- 서로 다른 통신 방식의 센서 다수를 한 보드에 통합하는 시스템 설계 경험
- 핀 충돌·전원 계통을 사전에 문서화(핀맵)해 조립 단계 시행착오 최소화
