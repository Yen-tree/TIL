# netconf, yang 세미나 준비

- 참조
    - [시스코 [칼럼] NETCONF-YANG의 이유있는 탄생!](https://gblogs.cisco.com/kr/netconf-yangs-birth-with-reason/amp/)
    - [https://devage.info/77/](https://devage.info/77/)

# 배경

### 변화하는 네트워크 흐름

- 클라우드, 빅데이터, IoT 등의 등장으로 점차 네트워크가 단순히 안정적으로 연결하는 것을 넘어 새로운 기술의 기반이 되는 플랫폼으로서의 중요성이 커지고 있음
- 새로운 서비스를 얼마나 빨리 효과적으로 적용하느냐가 중요해짐. 장비 중심, 모니터링 중심의 네트워크 관리에서 서비스 중심의 네트워크 관리로 옮겨가고 있음.

### 더 효과적인 장비 configuration에 대한 고민

- 시시각각 변화하는 기술을 빠르게 장비에 적용할 수 있는 효과적인 장비 configuration에 대한 고민
- 기존 장비 configuration 방법인 SNMP, CLI은 한계가 있음
    1. 설정에 적합하지 않은 데이터 구조
        - SNMP는 모니터링 목적으로 설계된 프로토콜로 configuration에는 적합하지 않음
    2. 안정성
        - SNMP는 UDP 기반이라 안정성이 떨어짐
    3. 성능
        - SNMP, CLI 스크립트는 대형 네트워크에서 많은 장비에 효과적이게 새로운 설정을 적용하는 것에 약함

⇒ 그 결과 오로지 **configuration에만 중점을 둔 프로토콜인 NETCONF**와 + **데이터 모델링 언어인 YANG**을 표준화함

- 네트워크 관리의 핵심이 네트워크 자동화로 옮겨가고 있음

# NETCONF

**network configuration protocol**

장비 설정, configuration에만 중점을 둔 프로토콜

- TCP/SSH 위에서 정의되는 응용 계층 프로토콜

# YANG

- 데이터 모델링 **언어**
    - 데이터를 **정의**함 (DB의 스키마 같은 개념!)
    - NETCONF 기반의 멀티벤더 장비 설정을 위한 효과적인 데이터 모델링 언어