---

##  OLED 공통층 형성을 위한 소형 roll-to-roll 슬롯다이 코터

1. **롤투롤(Roll-to-roll) 공정**  
   - 필름을 롤 형태로 언와인더에서 풀어내고, 슬롯다이로 코팅 후 와인더로 다시 감는 방식.  
   - 고속 연속 생산에 유리하며, 필름 장력 및 속도 제어가 핵심.

2. **슬롯다이 코팅**  
   - 슬롯다이 헤드를 통해 액상 재료(잉크, 코팅액 등)를 균일하게 도포.  
   - 위치 제어와 토크(장력) 제어, 그리고 속도 제어가 조합되어 균일 두께를 유지.

3. **PLC 기반 자동화**  
   - PLC(Programmable Logic Controller)를 통해 모터, 센서, 드라이버를 통합적으로 제어.  
   - 에러 발생 시 즉시 경고를 띄우고, 안전한 공정 중단 혹은 재시작 시퀀스를 수행.


---

## Position, Speed, Torque Control
 
필름의 장력 유지, 슬롯다이 위치 설정, 롤 속도 제어.

1. **Torque control (QD77 1축)**  
   - 필름(unwinder/winder)에서 장력을 유지.  
   

2. **Position control (QD75 1축)**  
   - 슬롯다이 헤드를 원하는 위치로 이동.  
  

3. **Speed control (QD75 2축)**  
   - 롤 속도 유지.  
  

---

## Error

1. **Torque control**  
   - 에러번호: `D1110`  
   - 경고번호: `D1111`  
   - **주요 원인**: 장력 센서 이상, 토크 설정 범위 초과 등

2. **Position control**  
   - 에러번호: `D2110`  
   - 경고번호: `D2111`  
   - **주요 원인**: 슬롯다이 위치 센서 오류, 오버트래블 감지 등

3. **Speed control**  
   - 에러번호: `D3110`  
   - 경고번호: `D3111`  
   - **주요 원인**: 속도 피드백 신호 이상, 모터 드라이버 경고 등

---

## Hardware

슬롯다이 코팅 공정에서 사용되는 주요 하드웨어 목록은 다음과 같습니다:

- **리니어 모터**: `FSL40E50 05C7BCB57`  
  - 슬롯다이 헤드를 정밀하게 이동시키는 데 사용

- **리니어 드라이버**: `FMDD50D40NOM`  
  - 리니어 모터 구동용 드라이버

- **(winder) Motor**: `HG-JR203`  
  - 언와인더/와인더 축에서 필름 이송 시 사용

- **(winder) 드라이버**: `MR-J4-200B`  
  - 모터 제어 드라이버 (장력, 속도 제어 등)

- **(winder) Motor**: `SGM7J-04AFA21`  
  - 추가 와인더 축 또는 서브 축에 사용 가능

- **(winder) 드라이버**: `SGD7S-2R8A00A`  
  - 모터 제어 드라이버

- **(winder) 감속기**: `PGX62-H-010`  
  - 모터 출력축에 연결해 토크 증대 및 속도 제어 정밀도 향상

- **POWER**: `Q61P`  
  - PLC 전원 공급 모듈

- **BASE**: `Q33B`  
  - PLC 메인 베이스 (슬롯 구조)

- **CPU**: `Q03UDVCPU`  
  - PLC 메인 CPU, 전체 공정 제어 로직 처리

- **(터치디스플레이) HMI**: `TOPRW0700WD`  
  - 공정 모니터링, 설정 변경 등에 사용

- **심플모션모듈**: `QD77MS2`  
  - 간단한 모션 제어(토크, 위치, 속도) 설정 및 제어에 사용

- **위치결정모듈**: `QD75D2N`  
  - 위치 결정 제어(고속 카운터, 엔코더 입력 등) 지원



