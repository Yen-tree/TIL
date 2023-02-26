# netconf, yang 세미나 준비

- 참조
  - [시스코 [칼럼] NETCONF-YANG의 이유있는 탄생!](https://gblogs.cisco.com/kr/netconf-yangs-birth-with-reason/amp/)
  - [NETCONF and YANG](https://devage.info/77/)

# 배경

### 변화하는 네트워크 흐름

- 클라우드, 빅데이터, IoT 등의 등장으로 점차 네트워크가 단순히 안정적으로 연결하는 것을 넘어 새로운 기술의 기반이 되는 플랫폼으로서의 중요성이 커지고 있음
- 새로운 서비스를 얼마나 빨리 효과적으로 적용하느냐가 중요해짐. 장비 중심, 모니터링 중심의 네트워크 관리에서 서비스 중심의 네트워크 관리로 옮겨가고 있음.
- 클라우드나 SDN (software defined network), NFV (network funciton virtualization) 등 기존 HW 기반 on-premise 중심에서 탈피한 새로운 개념의 네트워크 환경이 대두되면서, 관리가 필요한 네트워크 노드의 수와 종류가 비교할 수 없이 커지고 네트워크 설정의 자동화의 필요성이 높아졌다. NETCONF와 YANG은 이러한 환경에 적합한 네트워크 관리 프로토콜로 정의되었다.

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

> IETF? RFC?
> IETF(Internet Engineering Task Force): 국제 인터넷 표준화 기구
> RFC(Request for Comments): IETF에서 제공, 관리하는 문서. 거의 모든 인터넷 표준은 RFC로 문서화 되어있음.

# NETCONF

**network configuration protocol**

장비 설정, configuration에만 중점을 둔 프로토콜

- TCP/SSH 위에서 정의되는 응용 계층 프로토콜
- xml 형식

# YANG

yet another next generation
YANG is a language used to describe data models of network devices.

- 데이터 모델링 **언어**
- 데이터의 구조를 **정의**함 (DB의 스키마 같은 개념!)
- NETCONF 기반의 멀티벤더 장비 설정을 위한 효과적인 데이터 모델링 언어
  > YANG RFC문서
  > https://www.rfc-editor.org/rfc/rfc6020

## Language Concept

- module base
  > The module is the base unit of definition in YANG.
- Module과 Submodule 이름은 일반적인 prefix name과 충돌하지 않도록 작성할 것을 권장.
- server 안에서 모든 module 이름은 유일(unique)해야한다.

## 예약어

### Module & Submodule

- YANG의 Top level은 Module 혹은 Submodule로만 존재할 수 있음.
- module 이름은 파일명과 반드시 일치해야한다.

- Module
  - 재사용 할 수 없는 module.
  - import로 불러옴. 정의한 걸 손대지 않고 그대로 가져와 씀
- Submodule
  - module을 나눠놓은 개념..? volume을 쪼개놨다.
  - 재사용이 가능한 module을 정의하고 싶을 때. 살을 더 붙여서 사용할 수 있음.
  - include로 불러옴. 가져와서 재사용, 확장해서 씀.
  - 어떤 모듈에 속해있는지 belongs-to 속성을 가짐

### Leaf & Leaf-List

- Leaf
  - 더 이상 하위 개체를 갖고 있지 않은 노드.
- Leaf-List
  - 여러 개

### Container & List

- Container
  - 여러 개의 Leaf들을 grouping해 정의
- List
  - Container 안에 여러개가 존재할 때 List로 넣음
  - 반드시 갖고 있는 Leaf 중 하나는 key로 정의돼야함

### Grouping

- 확장 가능한 container 형태.
- 속성을 추가로 정의해 개념을 재사용/확장할 수 있다.
- use로 재사용
- ex) '사람' -> '학생', '직장인' 등으로 확장

### Config & State Data

- Config Data

  - read write
  - (default) config true -> config가 가능한 데이터
  - ex) interface의 name, ip address, subnetmask 등

- State Data

  - read-only
  - config false -> state data. 조회만 가능한 데이터
  - ex) interface의 packet count 등 show하는 정보들이 state data.

- 하위 leaf들은 기본적으로 parent의 속성을 물려받는다

### type & typedef

- type
  - 예제
  ```
  leaf gender {
    type enumeration {
        enum male;
        enum fevale;
    }
    config false;
    default female;
    description "gender";
  }
  ```
- typedef
  - type을 직접 정의해서 쓸 때 사용
  - 여러 군데에서 재사용할 수 있다.

### choices

- choice. 여러 옵션 중 하나를 선택하는 것.
- choice에 따라 컨테이너의 형태가 유연하게 바뀐다.
- choice에 의해서 말단 leaf들이 바뀔 수 있다.

### augment

### rpc & action & notification

- rpc
  - module 바로 하위 레벨에서 정의함
  - 변화, operation을 수행할 수 있도록 해줌
  - module안에서 할 수 있는 behavior를 정의할 때
  - module wide
- action
  - 어떤 action -> operation 수행
  - 특정 container에 dependency
- notification
  - 어떤 operation이 수행됐을 때 알려주는 것

## 궁금한 것

- module
  - namespace랑 prefix가 뭘까

## pyang

> 공식 github https://github.com/mbj4668/pyang
> pyang is a YANG validator, transformator and code generator, written in python. It can be used to validate YANG modules for correctness, to transform YANG modules into other formats, and to write plugins to generate code from the modules.
> YANG모델을 python module로 바꿔주는 툴

### 실행하는 법

#### basic validation

```
pyang 파일명.yang
```

syntactically correct한지 확인할 수 있음.
문법적 오류가 없으면 출력이 없고, 오류가 있으면 error 내용이 출력된다.

#### VIEW THE SCHEMA TREE

```
pyang -f tree ultraconfig-interfaces.yang
```

출력

```
module: ultraconfig-interfaces
  +--rw interfaces
     +--rw interface* [name]
     |  +--rw name           string
     |  +--rw address        dotted-quad
     |  +--rw subnet-mask    dotted-quad
     |  +--rw enabled?       boolean
     +--ro interface-state* [name]
        +--ro name           string
        +--ro oper-status    enumeration
```

- rw: readwrite
- ro: read-only
- ?: optional leaf

## YANG & YIN

YANG -----pyang으로 compile-----> YIN (netconf에서 쓰는 xml 형태)
