# DagraacSystems

## 개요  
소소하지만 Unity3D 등의 C#을 사용하는 프로젝트에서 활용될 수 있도록 작업 중인 게임 개발 지원 라이브러리 입니다.  
여러가지 개발 관련 필요 기능들을 지원하여 프로젝트의 작업 생산성이 향상되도록 돕는 것이 목적입니다.  

## 현재 작업된 기능 목록
* ulong 고유식별자 생성기
  * 8byte 단위 고유식별자를 생성하고 보관하는 기능
* 테이블시스템 (Table)
  * 고유한 구조를 가진 XLSX 로 작성된 데이터시트를 JSON 으로 익스포트 해주고 코드에서 참조될 수 있도록 CS를 자동으로 생성해주는 익스포트 툴 (파이썬3로 작성)
  * 뽑아진 JSON과 CS를 곧바로 프로젝트에서 사용할 수 있도록 기본적인 필요 기능이 구현된 테이블 매니저 코드
  * 스트링테이블 구조에 기반한 간단한 로컬라이제이션 코드
* 통지시스템 (MessageBroker)
  * 각각의 콜백함수를 종류별로 등록하거나 등록해제하고 등록되어있는 콜백함수들을 종류별로 일괄 호출할 수 있는 코드
* 작업 처리시스템 (Process)
  * 작업단위 클래스를 상속받아 구현한 상황에 맞는 작업을 처리기를 통해 실행하는 것으로 작업이 수행됨.
  * 작업단위 클래스는 Execute => Update => Pause => Resume => Finish 로 생명주기를 가짐.
  * 처리기는 여러개를 만들 수 있고 작업단위 클래스는 반드시 1개의 처리기에서 1회만 실행됨. (동시에 여러개의 처리기에서 동일작업을 수행할 수 없음).
* 상태머신 (FSM)
  * Target에서 실행되는 Machine은 각각의 State를 가지고 있으며 실행되는 State에 셋팅된 Action을 수행하고 마찬가지로 State에 셋팅된 Transition을 통해 조건이 맞는 다른 State로 이동.
  * 작업처리기 기반.
