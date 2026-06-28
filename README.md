
## 프로젝트 소개

<div align=center>
<img width="648" height="384" alt="image" src="https://github.com/user-attachments/assets/727543cd-7113-499f-bc43-4c8bed469e51" />

<img src="https://img.shields.io/badge/unity-%23000000.svg?&style=for-the-badge&logo=unity&logoColor=white" /> <img src="https://img.shields.io/badge/firebase-%23FFCA28.svg?&style=for-the-badge&logo=firebase&logoColor=black" />  

[**게임 홈페이지**](https://kimchanghyun325.github.io/Gangtaegom-site/ "둥둥 아일랜드 공식 홈페이지 바로가기")
 | 
[**게임 다운로드**](https://devel-rocket.itch.io/doongdoongisland "둥둥 아일랜드 배포 사이트 바로가기")
 | 
[**공식 유튜브**](https://www.youtube.com/@GangTaeGom_Official "둥둥 아일랜드 공식 유튜브 바로가기")

<br>
'둥둥 아일랜드(DDIsland)'는 윈도우 기반 방치형 위젯 게임입니다.
<br>
</div>




## 팀원 소개
<div align=center>

| 포지션 | 이름 | 담당 업무 | GitHub / Contact |
| :--- | :--- | :--- | :--- |
| **개발** | **신현섭 (팀장)** | • 데스크탑 위젯 시스템<br>• 데이터 파서 에디터 툴 구현<br>• 로컬라이제이션<br>• 로컬 데이터(PlayerPrefs) 데이터 관리<br>• 메인 UI & 게임 설정창 & 음반 시스템 구현 & 게임 매니저 | [@hyunsup98](https://github.com/hyunsup98) |
| 개발 | 전지후 (부팀장) | • 상점, 거래 시스템<br>• 장식, 코스튬 적용 기능<br>• 레시피 기능 구현 | [@jeonjyu](https://github.com/jeonjyu) |
| 개발 | 채종안 | • 플레이어 업그레이드 시스템<br>• 도감 기능<br>• 호수창 인테리어 기능<br>• 섬 꾸미기 UI 구현 | [@ChaeJongAn](https://github.com/ChaeJongAn) |
| 개발 | 함승빈 | • 물고기 AI<br>• 섬 오브젝트 꾸미기 기능<br>• 서버 데이터(Firebase Realtime DB) 관리<br>• 도움말, 우편함 기능 | [@Complex-Answer](Complex-Answer (Good Reply)) |
| 개발 | 강한결 | • 플레이어 AI<br>• 퀘스트 기능<br>• 인벤토리 기능<br>• 재화 획득 연출 | [@oppa073-hub](https://github.com/oppa073) |
| 기획 | 고하나 (팀장) | • 리소스 총책임자<br>• 음반 시스템 기획 | [@B1iss3y](https://github.com/B1iss3y) |
| 기획 | 김창현 (부팀장) | • 자율 행동 기획<br>• 화면 및 환경 시스템 기획<br>• 물고기 기획<br>• 연출 기획 | [@kimchanghyun325](https://github.com/kimchanghyun325?tab=repositories) |
| 기획 | 공성식 | • 게임 마케팅 담당<br>• 플레이어 캐릭터 기획<br>• 플레이어 업그레이드 시스템 기획<br>• 도움말 기획  | [@Kong_Seong_Sik](https://github.com/tjdtlr1235-sudo) |
| 기획 | 최명호 | • 섬 & 호수 꾸미기 기획<br>• 상호작용 기능(상자, 우편함 등의 오브젝트) 기획  | [@myeongho-choi](https://github.com/myeongho-choi) |
| 기획 | 조경석 | • 데이터 테이블 관리<br>• 상점 시스템 기획<br>• 퀘스트 기능 기획<br>• 컨셉 기획 | [@CHO KYEONGSEOK](CITY-ZENSSS (CHO KYEONGSEOK)) |
| 기획 | 나하준 | • UI 총책임자<br>• 비주얼 가이드 기획<br>• 도감 시스템 기획 | [@zasxdf171712-debug](https://github.com/zasxdf171712-debug) |
| QA | 이종곤 | • TQA<br>• White QA | [@jonggon1104-cpu](https://github.com/jonggon1104-cpu) |

</div>
<br>

## 사용 기술 스택

- Engine & Language : `Unity 3D`, `C#`
- Graphics & Pipeline : `URP`
- Library & Plugins : `DOTWeen`, `UniWinController`
- Version Control : `Github`


## 담당 기능
💡 **클래스명을 클릭하면 해당 소스 코드로 이동합니다.**

### 1. 데이터 파서 자동화 툴
- [`TableSOGeneratorWindow`](Assets/0.Scripts/CSVParser/Editor/TableSOGeneratorWindow.cs)
  - Unity Editor 메뉴에서 CSV 경로와 SO 저장 경로를 지정하고, 파싱 및 SO 생성을 실행하는 에디터 툴 구현 클래스
  - EditorPrefs를 사용해 경로 저장, 
 
- [`TableSOGenerator`](Assets/0.Scripts/CSVParser/Editor/TableSOGenerator.cs)
  - CSV 테이블을 파싱해 데이터용 ScriptableObject 클래스와 Database 클래스를 자동 생성하고, CSV 데이터를 실제 SO 에셋으로 주입하는 핵심 생성 로직
  - 파싱 과정: `에디터 창에서 경로 지정` → `CSV 헤더를 읽어서 컬럼 정보로 변환` → `Scriptable Object 클래스 코드를 생성` → `실제 값이 들어간 Scriptable Object 생성`

- [`CsvClassData`](Assets/0.Scripts/CSVParser/Editor/CsvClassData.cs)
  - CSV 헤더, 컬럼 타입, 데이터 개수 등 파싱 결과를 담는 데이터 컨테이너

 - [`TableBase`](Assets/0.Scripts/CSVParser/Table/TableBase.cs) & [`TableDatabase`](Assets/0.Scripts/CSVParser/Table/TableDatabase.cs)
  - 데이터 파서 툴을 이용해 생성된 DataSO와 DatabaseSO가 공통으로 상속받는 기반 클래스
  - DataSO에서는 데이터의 고유 ID를 반환하도록 하는 추상 메서드 구현, DatabaseSO에서는 인덱서를 통해 ID 기준 조회가 가능하도록 구현


### 2. 데스크탑 위젯 시스템
- [`WindowCore`](Assets/0.Scripts/WindowController/WindowCore.cs)
  - Win32 API를 래핑한 UniWinController 라이브러리를 활용하여 창 위치, 크기, 투명도 등을 처리하는 저수준 윈도우 제어 클래스
  - 라이브러리에서 지원하지 않는 작업 표시줄 대응 등의 기능은 직접 Win32 API 함수를 P/Invoke하여 구현
 
- [`WindowController`](Assets/0.Scripts/WindowController/WindowController.cs)
  - 투명 창, 클릭 통과, 최상단 고정 여부, 모니터 전환 등 데스크탑 위젯처럼 동작하는 윈도우 제어 기능을 관리 및 설정
  - 인스펙터를 통해 간단하게 운영체제 관련 기능 설정 가능


### 3. 다국어 지원 (Localization)
- [`LocalizationManager`](Assets/0.Scripts/System/LocalizationManager.cs)
  - 현재 언어 설정에 맞춰 문자열 테이블에서 텍스트를 반환하고, 사용 기기 시스템 언어 기반 초기 언어 설정을 담당

- [`UI_BaseLocalization`](Assets/0.Scripts/UI/LocalizedText/UI_BaseLocalizedText.cs)
  - LocalizationManager.cs의 언어 변경 이벤트를 구독해 UI 텍스트를 자동으로 갱신하는 Localize UI 부모 클래스

- [`UI_DropdownText`](Assets/0.Scripts/UI/LocalizedText/UI_DropdownText.cs)
  - 드롭다운 옵션 텍스트를 현재 언어에 맞춰 갱신하는 Localize 전용 클래스


### 4. 오브젝트 풀링
- [`ObjectPoolManager`](Assets/0.Scripts/DesignPattern/ObjectPooling/ObjectPoolManager.cs)
  - 풀 초기 크기, 최대 크기, 생성 위치 등 공통 설정을 제공하는 오브젝트 풀링 기반 클래스

- [`SinglePoolManager`](Assets/0.Scripts/DesignPattern/ObjectPooling/SinglePoolManager.cs)
  - 단일 프리팹을 대상으로 풀을 관리하는 제네릭 오브젝트 풀 클래스

- [`MultiPoolManager`](Assets/0.Scripts/DesignPattern/ObjectPooling/MultiPoolManager.cs)
  - 여러 프리팹 타입을 이름별 풀로 분리해 관리하는 제네릭 오브젝트 풀 클래스


### 5. 사운드 매니저 및 음반 시스템
- [`SoundManager`](Assets/0.Scripts/System/SoundManager.cs)
  - BGM(배경음), SFX(효과음), AMB(환경음), Preview(미리듣기) 사운드 타입 별 재생과 볼륨/음소거 설정, 사운드 페이드 효과, SFX(효과음) 풀 관리 등의 기능을 통합 관리하는 매니저 클래스
  - 코루틴을 이용해 페이드 재생 효과, 효과음 풀 정리, 재생 완료 체크 등의 지연 처리
  - 코루틴 객체와 `WaitForSeconds` 등 반복 사용되는 YieldInstruction을 미리 캐싱해 GC 할당을 최소화

- [`UI_Record`](Assets/0.Scripts/UI/Record/UI_Record.cs)
  - 음반 UI의 진입점으로 BGM/AMB 재생 리스트를 관리하고, 기본 음반 재생을 시작하는 역할

- [`UI_BGMList`](Assets/0.Scripts/UI/Record/List/UI_BGMList.cs)
  - BGM 음반 재생, 재생 타입 설정(반복/셔플), 다음/이전 곡 재생, 정렬/필터링 옵션 등 배경음 재생의 통합적인 기능을 담당

- [`UI_AMBList`](Assets/0.Scripts/UI/Record/List/UI_AMBList.cs)
  - AMB 음반 재생, 정렬/필터링 옵션, 재생/일시정지 등 환경음 재생의 통합적인 기능을 담당

- [`UI_Playlist`](Assets/0.Scripts/UI/Record/PlayList/UI_Playlist.cs)
  - 사용자 플레이리스트 생성, 이름 변경, 삭제, 현재 플레이리스트 표시 등 음반 재생 목록 관련 기능을 담당

- [`RecordComparer`](Assets\0.Scripts\UI\Record\Compare\RecordComparer.cs)
  - 음반 리스트 정렬을 위한 IComparer<RecordDataSO> 구현체


### 6. 설정창 & 로컬 데이터 관리
- [`UI_Settings`](Assets/0.Scripts/UI/Settings/UI_Settings.cs)
  - 언어, 사운드, 위젯 관련 설정 등 게임의 전반적인 설정을 관리

- [`PlayerPrefsDataManager`](Assets/0.Scripts/System/PlayerPrefsDataManager.cs)
  - 언어, 볼륨, 음소거, 위젯 관련 설정 등의 로컬 설정값을 PlayerPrefs로 저장/로드
  - 로컬 데이터 저장 전용 정적 클래스를 통해 데이터 저장 로직을 중앙화 및 유지보수성 향상
  - 외부에서는 프로퍼티를 통해 접근하도록 하여 코드의 안정성과 확장성 증가

- [`DataManager`](Assets/0.Scripts/System/Data/DataManager.cs)
  - 각 데이터별 DatabaseSO를 참조하는 전역 데이터 관리 클래스
  - 게임 내 시스템들이 데이터에 일관되게 접근할 수 있도록 중앙 진입점 역할 수행
 
### 7. 화면 컨트롤러 (섬&호수 화면 이동/크기 조절)
- [`CameraController`](Assets/0.Scripts/System/Camera/CameraController.cs)
  - 섬 화면 UI의 이동/크기 조절에 따라 섬 3D 오브젝트를 비추는 카메라를 컨트롤하는 클래스
  - 섬 화면 UI의 위치 비율과 스케일 비율을 기준으로 카메라 시야 범위와 오프셋을 동기화

- [`UI_IslandWindow`](Assets/0.Scripts/UI/Window/UI_IslandWindow.cs)
  - 섬 화면 UI 관련 조작을 관리 (화면 이동, 크기 조절 등)

- [`UI_WaterWindow`](Assets/0.Scripts/UI/Window/UI_WaterWindow.cs)
  - 호수 화면 UI 관련 조작을 관리 (UI 켜기/끄기, UI 높이 조절 등)

### 8. 공통 유틸리티 및 보조 시스템
- [`ExtensionManager`](Assets/0.Scripts/Util/ExtensionManager.cs)
  - 반복적으로 사용되는 기능을 확장 메서드로 분리하여 코드 재사용성 증가
 
- [`Singleton`](Assets/0.Scripts/DesignPattern/Singleton/Singleton.cs)
  - 매니저 클래스에서 공통으로 사용할 수 있는 제네릭 기반 싱글턴 클래스 구현

- [`InteractObject`](Assets/0.Scripts/InteractObject/InteractObject.cs) & [`IInteract`](Assets/0.Scripts/Interface/Interact/IInteract.cs)
  - 게임 내 오브젝트와 플레이어/시스템 간의 상호작용 처리를 위한 인터페이스와 이를 상속받는 추상 클래스 구현












