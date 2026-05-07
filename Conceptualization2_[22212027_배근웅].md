# Market Analyst Tool


<img width="1206" height="677" alt="image" src="https://github.com/user-attachments/assets/12046886-e2c1-4c19-97f2-be61dc5adacf" />

### <시장분석UI예시>
## 기본 정보

- **학번:** 22212027  
- **이름:** 배근웅  

---

##  GitHub Repository

- https://github.com/BAEGEUN12/Market-anaylist-tool/blob/main/Conceptualization2_%5B22212027_%EB%B0%B0%EA%B7%BC%EC%9B%85%5D.md
## Contents

* [1. Introduction](#)
* [2. Use case analysis](#)
* [3. Domain analysis](#)
* [4. User Interface prototype](#)
* [5. Glossary](#)
* [6. References](#)

## 1. introduction 
### 1.Executive Summary
최근 주식 투자에 대한 관심이 크게 증가하면서 많은 사람들이 주식 시장에 참여하고 있다.  
이러한 관심 증가는 모바일 트레이딩 시스템(MTS)의 보편화, 온라인 정보 접근성 향상, 저금리 환경으로 인한 투자 대안 탐색 등의 요인에 의해 촉진되었다.

그러나 상당수의 개인 투자자들은 충분한 지식이나 체계적인 분석 없이 감에 의존하거나 단순한 정보만을 기반으로 투자하는 경우가 많다.  
이로 인해 비효율적인 투자 판단이나 손실이 발생할 가능성이 높아지고 있으며, 주식 분석에 대한 접근성과 이해도를 높이는 도구의 필요성이 커지고 있다.
특히, 금융 시장에서는 데이터와 수학적 모델을 기반으로 한 알고리즘 트레이딩이 널리 활용되고 있으며, 이는 감정에 의존하지 않고 객관적인 기준을 통해 투자 의사결정을 수행한다는 특징을 가진다.
예를 들어월가(Wall Street)에서는 수학적 알고리즘과 데이터 기반 모델을 활용한 정교한 매매 시스템이 활용되고 있으며, 이는 감정에 의존하지 않고 객관적인 분석을 통해 투자 의사결정을 수행한다는 점에서 높은 효율성을 보인다.
비록 이러한 구체적인 알고리즘은 공개되어 있지 않지만, 데이터 기반 분석과 정량적 접근 방식 자체는 개인 투자자에게도 충분히 적용 가능한 개념이다.

본 프로젝트는 이러한 알고리즘 기반 투자 방식의 원리를 바탕으로, 일반 사용자도 쉽게 활용할 수 있는 주식 분석 시스템을 구현하는 것을 목표로 한다.
### 2.Business Goals

본 프로젝트는 정보의 불균형과 감정적 판단으로 인해 발생하는 개인 투자자의 손실을 방지하고, 데이터 기반의 객관적인 투자 문화를 확산시키는 것을 궁극적인 목표로 한다. 이를 위해 다음과 같은 세부 목표를 설정한다.

#### 1) 정보 접근성 제고 및 분석 진입장벽 완화
전문적인 금융 데이터는 일반인이 해석하기에 복잡하고 방대하다는 문제점이 있다. 본 시스템은 복잡한 원천 데이터(Raw Data)를 직관적인 지표와 시각화 도구로 변환하여 제공함으로써, 금융 지식이 부족한 초보 투자자도 시장의 흐름을 즉각적으로 파악할 수 있는 '분석의 대중화'를 지향한다.

#### 2) 데이터 기반의 정량적 분석 모델 구축
감정에 휘둘리는 매매 패턴은 개인 투자자 손실의 주요 원인이다. 본 프로젝트는 주가, 거래량,평균이동선 등 핵심 변수를 수학적 알고리즘으로 처리하여 객관적인 매수·매도 가이드를 제시한다. 

#### 3) 리스크 관리 최적화를 통한 손실 최소화
단순히 수익률을 높이는 것에 그치지 않고, 투자자가 감당할 수 있는 위험 범위를 설정하고 위험종목을 관리할 수 있는 기능을 구현한다. 

#### 4) 실무 중심의 직관적 UX/UI 구현
복잡한 수식과 코드 대신, 누구나 쉽게 조작할 수 있는 대시보드 형태의 인터페이스를 제공한다. 사용자가 특정 종목을 선택하면 시스템 내부의 알고리즘이 자동으로 분석을 수행하고, 그 결과를 일반적인 비즈니스 언어로 요약하여 제공함으로써 '이해 가능한 투자(Informative Investing)' 환경을 조성한다.

### 3. Technical Goals
구현할려고 하는 시스템에는 크게 Client 와 Server 가 있다 Server 에는 회원정보와 검색기록등 회원이 관심을 가지고 검색한 종목들이 있다. 이러한 정보는 관리자만 데이터 관리를 위해 수정이 가능하면 임의로 수정할수없다.또한 외부 API 를 이용해서 서비스를 제공하는 만큼 토큰 수가 문제가 될수 있는데 대안으로 멀티 API 키를 사용하거나 시맨틱 캐싱(이전에 입력했던 단어가 일치하거나 의미적으로 유사하면 API 키를 호출하지 않고 캐시된 답변을 활용하는 것), 지표 사전 계산(시스템(Python 등)에서 RSI, MACD, 이평선 등 수치를 미리 계산해서 결과값만 AI에게 전달)을 통해 토큰 문제를 해결한다.

## 2. Use case analysis
### 2.1. Use Case Diagram
 아래의 그림은 Market-analylist-tool 시스템의 Use case Diagram을 그림으로 나타낸 것이다.
 <img width="1203" height="775" alt="스크린샷 2026-04-29 192419" src="https://github.com/user-attachments/assets/09ba0130-293a-4f46-a18d-52fd8766b42b" />
 Use Case는 동명사로 정의 하였다. Actor는 
User와 Administrator, Stock API, Gemini API 총 네 개로 나타내었다. 그리고 각 기능별로 연관성에 따
라 include 관계나 exclude관계가 적용이 되었다.
### 아래는 각 Use Case의 ID와 Korean Name, Actor를 나타낸 표이다
| Use Case Name | Use Case ID | Korean Name | Actor |
| :--- | :---: | :--- | :--- |
| **Search Stock Analysis** | #1 | 주식 분석 조회 | User |
| **Login** | #2 | 로그인 | User, Administrator |
| **Evaluation value adjustment** | #3 | 평가 가치 조정 | Administrator |
| **Layout adjustment** | #4 | 레이아웃 조정 | Administrator |
| **Enter Stock Name** | #5 | 종목명 입력 | User |
| **Login Verification** | #6 | 로그인 검증 | User, Administrator |
| **Request Stock Data** | #7 | 주식 데이터 요청 | Stock API |
| **Request AI Analysis** | #8 | AI 분석 요청 | Gemini API |
| **Generate Analysis Result** | #9 | 분석 결과 생성 | Gemini API |

Use Case Description에서는 위에서부터 차례대로 각 Use Case에 대해 표로 
Description을 보여준다.

### 2.2. Use Case Description
   2.2.1 Log-in
| Use Case Name | Use Case ID | Korean Name | Actor |
| :--- | :---: | :--- | :--- |
| **Login** | #2 | 로그인 | Member, Administrator |

<br>

| Use Case #2 : Log-in | |
| :--- | :--- |
| **GENERAL CHARACTERISTICS** | |
| **Summary** | 등록을 한 회원과 관리자들은 로그인을 하여 직책에 맞는 기능을 사용할 수 있다. |
| **Scope** | Market anaylist tool|
| **Level** | User level |
| **Author** | Bae GeunWong |
| **Last Update** | May. 3. 2026 |
| **Status** | Under Review |
| **Primary Actor** | User, Administrator |
| **Secondary Actors** | Server |
| **Preconditions** | 회원등록을 마친 상태. |
| **Trigger** | 시스템에 로그인을 하기 위해서 ID와 Password를 입력하고 로그인 버튼을 눌렀을 때 |
| **Success Post Condition** | Server에 저장되어 있는 회원임을 인증된 경우 시스템의 모든 기능을 사용할 수 있다. |
| **Failed Post condition** | Server에 저장되어 있지 않은 회원일 경우 로그인이 되지 않는다. |

<br>

| MAIN SUCCESS SCENARIO | |
| :--- | :--- |
| **Step** | **Action** |
| **1** | 회원이 시스템을 사용하려고 로그인을 시도한다. |
| **2** | 로그인 화면에 있는 ID와 Password 입력칸에 자신의 ID와 Password를 입력한다. |
| **3** | 로그인 버튼을 누른다. |
| **4** | 시스템이 Server에서 가져온 회원 데이터베이스를 토대로 확인한다. |
| **5** | 로그인을 성공했다는 메시지를 보여주고 메인 화면으로 들어간다. |

<br>

| EXTENSION SCENARIOS | |
| :--- | :--- |
| **Step** | **Branching Action** |
| **2** | **2a. 등록하지 않은 회원일 경우.**<br>2a1. 등록하지 않은 회원이라고 메시지를 보여준다.<br>2a2. ID, Password 입력칸을 초기화한다.<br><br>**2b. ID는 맞는데 Password가 틀릴 경우.**<br>2b1. Password가 틀렸다는 메시지를 보여준다.<br>2b2. 해당 입력칸을 초기화한다. |
| **3** | 3a. 본 시스템에 등록되어 있지 않은 사용자의 경우 회원가입(Use Case ID : #1)을 반드시 수행해야만 한다. |
| **4** | **4a. 인터넷이 연결되어 있지 않아서 데이터베이스를 못 가져온 경우.**<br>4a1. 데이터베이스를 못 가져왔다는 메시지를 띄워준다. |

<br>

| RELATED INFORMATION | |
| :--- | :--- |
| **Performance** | ≤ 3 Seconds (로그인 버튼을 눌렀을 때 시스템 내부까지 들어가는 시간을 말한다.) |
| **Frequency** | None | 
| **Concurrency** | None |
| **Due Date** | 2017-05-31 |
| **Etc** | None |


### 2.2.2 Evaluation value adjustment

| Use Case Name | Use Case ID | Korean Name | Actor |
| :--- | :---: | :--- | :--- |
| **Evaluation value adjustment** | #3 | 평가 가치 조정 | Administrator |

<br>

| Use Case #3 : Evaluation value adjustment | |
| :--- | :--- |
| **GENERAL CHARACTERISTICS** | |
| **Summary** | 관리자가 Gemini AI의 매수/매도 판단 기초가 되는 평가 지표와 분석 기법을 최신 트렌드에 맞게 수정 및 업데이트한다. |
| **Scope** | Market analyst tool |
| **Level** | User level |
| **Author** | Bae GeunWong |
| **Last Update** | May. 5. 2026 |
| **Status** | Under Review |
| **Primary Actor** | Administrator |
| **Secondary Actors** | Gemini API, Server |
| **Preconditions** | 관리자 권한으로 로그인된 상태. |
| **Trigger** | 새로운 분석 기법 도입이나 기존 평가 지표의 수정이 필요하다고 판단될 때 |
| **Success Post Condition** | 변경된 평가 가치가 시스템에 반영되어 Gemini AI가 새로운 기준에 따라 분석 결과를 생성한다. |
| **Failed Post condition** | 설정값 저장 실패 시 기존 평가 가치 기준이 유지된다. |

<br>

| MAIN SUCCESS SCENARIO | |
| :--- | :--- |
| **Step** | **Action** |
| **1** | 관리자가 시스템 설정 메뉴의 '평가 가치 조정' 페이지에 접속한다. |
| **2** | 현재 설정된 AI 분석 지표(재무제표, 차트 분석, 뉴스 심리 등)의 가중치와 기법을 확인한다. |
| **3** | 최신 시장 트렌드와 분석 기법을 반영하여 평가 항목 및 수치를 수정한다. |
| **4** | '설정 적용' 버튼을 눌러 변경 사항을 저장한다. |
| **5** | 시스템이 변경된 기준을 Gemini API 연동 모듈에 전달하고 적용 완료 메시지를 출력한다. |

<br>

| EXTENSION SCENARIOS | |
| :--- | :--- |
| **Step** | **Branching Action** |
| **1** | **1a. 입력된 설정값이 유효하지 않은 범위일 경우.**<br>1a1. 오류 메시지를 보여주고 올바른 값 입력을 유도한다. |
| **2** | **2a. API 연동 오류로 인해 실시간 반영이 실패할 경우.**<br>2a1. 서버 로그에 오류를 기록하고 관리자에게 재시도 요청 알림을 띄운다. |

<br>

| RELATED INFORMATION | |
| :--- | :--- |
| **Performance** | 설정 저장 및 AI 기준 반영은 5초 이내에 완료되어야 한다. |
| **Frequency** | 분석 기법 업데이트 시(비정기적) |
| **Concurrency** | 관리자 단독 수행 (중복 수정 방지 필요) |
| **Due Date** | 2026-05-31 |
| **Etc** | Gemini AI의 분석 정확도와 직결되는 항목이므로 변경 전 백업이 권장됨. |

### 2.2.3 Layout adjustment

| Use Case Name | Use Case ID | Korean Name | Actor |
| :--- | :--- | :--- | :--- |
| **Layout adjustment** | #4 | 레이아웃 조정 | Administrator |

<br>

| Use Case #4 : Layout adjustment | |
| :--- | :--- |
| **GENERAL CHARACTERISTICS** | |
| **Summary** | 관리자가 사용자에게 보여지는 주식 분석 화면 및 리포트의 레이아웃 구성을 최적화하거나 수정한다. |
| **Scope** | Market analyst tool |
| **Level** | User level |
| **Author** | Bae GeunWong |
| **Last Update** | May. 5. 2026 |
| **Status** | Under Review |
| **Primary Actor** | Administrator |
| **Secondary Actors** | Server |
| **Preconditions** | 관리자 권한으로 로그인된 상태. |
| **Trigger** | 대시보드의 가독성 개선이 필요하거나 새로운 위젯/차트 배치가 필요할 때 |
| **Success Post Condition** | 변경된 레이아웃 설정이 데이터베이스에 저장되어 모든 사용자의 화면에 즉시 반영된다. |
| **Failed Post condition** | 저장 실패 시 이전 레이아웃 구성이 그대로 유지된다. |

<br>

| MAIN SUCCESS SCENARIO | |
| :--- | :--- |
| **Step** | **Action** |
| **1** | 관리자가 시스템 관리 UI의 '레이아웃 설정' 메뉴로 진입한다. |
| **2** | 현재 사용자에게 출력되는 분석 차트, 뉴스 피드, AI 요약문의 배치 상태를 확인한다. |
| **3** | 드래그 앤 드롭 또는 설정값을 통해 각 컴포넌트의 위치와 크기를 조정한다. |
| **4** | '미리보기'를 통해 변경된 레이아웃을 검토한 후 '적용' 버튼을 누른다. |
| **5** | 시스템이 새로운 레이아웃 템플릿을 저장하고 적용 완료 메시지를 보여준다. |

<br>

| EXTENSION SCENARIOS | |
| :--- | :--- |
| **Step** | **Branching Action** |
| **1** | **1a. 필수 출력 항목이 레이아웃에서 누락된 경우.**<br>1a1. 경고 메시지를 띄우고 필수 항목을 다시 배치하도록 안내한다. |
| **2** | **2a. 미리보기 단계에서 비정상적인 화면 왜곡이 발견될 경우.**<br>2a1. '초기화' 버튼을 눌러 마지막 저장 상태로 되돌린다. |

<br>

| RELATED INFORMATION | |
| :--- | :--- |
| **Performance** | 레이아웃 변경 사항은 저장 후 2초 이내에 사용자 인터페이스에 반영되어야 한다. |
| **Frequency** | UI 개선 및 업데이트 시 발생 |
| **Concurrency** | 관리자 단독 수행 (다수 관리자 동시 수정 시 마지막 저장 기준 적용) |
| **Due Date** | 2026-05-31 |
| **Etc** | 반응형 웹 디자인 규격을 준수하여 모바일과 데스크톱 환경을 모두 고려해야 함. |

### 2.2.4 Enter Stock Name

| Use Case Name | Use Case ID | Korean Name | Actor |
| :--- | :--- | :--- | :--- |
| **Enter Stock Name** | #5 | 종목명 입력 | User |

<br>

| Use Case #5 : Enter Stock Name | |
| :--- | :--- |
| **GENERAL CHARACTERISTICS** | |
| **Summary** | 사용자가 분석을 원하는 주식의 종목명 또는 종목 코드를 입력하여 시스템에 분석 대상을 전달한다. |
| **Scope** | Market analyst tool |
| **Level** | User level |
| **Author** | Bae GeunWong |
| **Last Update** | May. 5. 2026 |
| **Status** | Under Review |
| **Primary Actor** | User |
| **Secondary Actors** | Server, Stock API |
| **Preconditions** | 시스템 메인 화면에 접속한 상태. |
| **Trigger** | 사용자가 특정 종목에 대한 AI 분석 결과를 확인하고자 할 때 |
| **Success Post Condition** | 입력한 종목이 유효함이 확인되고, 해당 종목의 상세 분석 페이지로 이동한다. |
| **Failed Post condition** | 존재하지 않는 종목이거나 입력 오류 시 경고 메시지를 출력하고 재입력을 요구한다. |

<br>

| MAIN SUCCESS SCENARIO | |
| :--- | :--- |
| **Step** | **Action** |
| **1** | 사용자가 메인 화면의 검색창에 분석하고자 하는 종목명(예: 삼성전자) 또는 종목 코드를 입력한다. |
| **2** | 입력 시 실시간으로 연관 검색어 리스트가 출력된다. |
| **3** | 사용자가 리스트에서 원하는 종목을 선택하거나 'Enter' 키를 누른다. |
| **4** | 시스템이 Stock API를 통해 해당 종목의 존재 여부와 기본 정보를 대조한다. |
| **5** | 유효한 종목인 경우, 해당 종목의 데이터 로딩과 함께 분석 결과 화면으로 전환된다. |

<br>

| EXTENSION SCENARIOS | |
| :--- | :--- |
| **Step** | **Branching Action** |
| **1** | **1a. 아무것도 입력하지 않고 검색을 시도할 경우.**<br>1a1. "종목명을 입력해 주세요"라는 안내 메시지를 띄운다. |
| **2** | **2a. 존재하지 않는 종목명 또는 잘못된 코드를 입력한 경우.**<br>2a1. "검색 결과가 없습니다. 다시 확인해 주세요"라는 메시지를 출력한다. |

<br>

| RELATED INFORMATION | |
| :--- | :--- |
| **Performance** | 종목 검색 및 자동완성 리스트 출력은 1초 이내에 이루어져야 한다. |
| **Frequency** | 서비스 이용 시 수시로 발생 |
| **Concurrency** | 다수의 사용자가 동시에 검색 가능 |
| **Due Date** | 2026-05-31 |
| **Etc** | 국문 종목명뿐만 아니라 영문명 및 6자리 종목 코드 검색을 모두 지원해야 함. |


### 2.2.5 Login Verification

| Use Case Name | Use Case ID | Korean Name | Actor |
| :--- | :--- | :--- | :--- |
| **Login Verification** | #6 | 로그인 검증 | User, Administrator |

<br>

| Use Case #6 : Login Verification | |
| :--- | :--- |
| **GENERAL CHARACTERISTICS** | |
| **Summary** | 사용자가 입력한 계정 정보(ID, Password)를 서버 데이터베이스와 대조하여 유효한 사용자인지 검증한다. |
| **Scope** | Market analyst tool |
| **Level** | Sub-function level |
| **Author** | Bae GeunWong |
| **Last Update** | May. 5. 2026 |
| **Status** | Under Review |
| **Primary Actor** | User, Administrator |
| **Secondary Actors** | Server, Database |
| **Preconditions** | 사용자가 로그인 페이지에서 정보를 입력하고 로그인 버튼을 누른 상태. |
| **Trigger** | 로그인 시도가 감지되어 사용자 인증이 필요할 때 |
| **Success Post Condition** | 정보가 일치하여 사용자에게 시스템 접근 권한(세션 또는 토큰)을 부여한다. |
| **Failed Post condition** | 인증 실패 시 접근을 차단하고 실패 원인에 따른 오류 메시지를 출력한다. |

<br>

| MAIN SUCCESS SCENARIO | |
| :--- | :--- |
| **Step** | **Action** |
| **1** | 시스템이 전달받은 ID와 암호화된 Password를 확인한다. |
| **2** | 서버가 데이터베이스에 해당 ID가 존재하는지 조회한다. |
| **3** | 데이터베이스에서 가져온 암호화된 비밀번호와 입력된 비밀번호를 비교 검증한다. |
| **4** | 해당 계정의 활성화 상태 및 권한(User/Admin) 정보를 확인한다. |
| **5** | 검증 완료 후 인증 성공 결과를 상위 유스케이스(Log-in)로 반환한다. |

<br>

| EXTENSION SCENARIOS | |
| :--- | :--- |
| **Step** | **Branching Action** |
| **1** | **1a. 데이터베이스에 존재하지 않는 ID일 경우.**<br>1a1. 인증 실패 결과를 반환한다. |
| **2** | **2a. 비밀번호가 일치하지 않을 경우.**<br>2a1. 비밀번호 불일치 오류를 반환한다. |
| **3** | **3a. 계정이 잠겨있거나 비활성 상태인 경우.**<br>3a1. 계정 사용 제한 메시지를 반환한다. |

<br>

| RELATED INFORMATION | |
| :--- | :--- |
| **Performance** | 보안 검증 및 DB 조회는 1초 이내에 완료되어야 한다. |
| **Frequency** | 로그인 시도 시마다 매번 발생 |
| **Concurrency** | 다수의 사용자가 동시에 인증 요청 가능 |
| **Due Date** | 2026-05-31 |
| **Etc** | 비밀번호는 반드시 암호화(Hashing)된 상태로 비교되어야 하며, 보안을 위해 실패 원인을 지나치게 상세히 노출하지 않는다. |


### 2.2.6 Request Stock Data

| Use Case Name | Use Case ID | Korean Name | Actor |
| :--- | :--- | :--- | :--- |
| **Request Stock Data** | #7 | 주식 데이터 요청 | Stock API |

<br>

| Use Case #7 : Request Stock Data | |
| :--- | :--- |
| **GENERAL CHARACTERISTICS** | |
| **Summary** | 시스템이 외부 Stock API에 접속하여 특정 종목의 실시간 시세, 재무제표, 거래량 등 분석에 필요한 로우 데이터(Raw Data)를 호출한다. |
| **Scope** | Market analyst tool |
| **Level** | Sub-function level |
| **Author** | Bae GeunWong |
| **Last Update** | May. 5. 2026 |
| **Status** | Under Review |
| **Primary Actor** | Stock API |
| **Secondary Actors** | Server |
| **Preconditions** | 유효한 종목명 또는 종목 코드가 확인되어 데이터 요청 기능이 활성화된 상태. |
| **Trigger** | 사용자가 종목 분석을 요청하거나 시스템에서 주기적인 데이터 갱신이 필요할 때 |
| **Success Post Condition** | 외부로부터 필요한 데이터를 정상적으로 수신하여 시스템 서버 내 메모리 또는 DB에 적재한다. |
| **Failed Post condition** | API 연결 실패 또는 데이터 부재 시, 사용자에게 데이터 로딩 실패 알림을 전달한다. |

<br>

| MAIN SUCCESS SCENARIO | |
| :--- | :--- |
| **Step** | **Action** |
| **1** | 시스템 서버가 Stock API 서버에 인증 키(API Key)와 함께 데이터 요청 쿼리를 전송한다. |
| **2** | Stock API 서버에서 요청받은 종목의 최신 시장 데이터를 검색한다. |
| **3** | API 서버가 JSON 또는 XML 형식으로 종목 데이터를 시스템 서버에 반환한다. |
| **4** | 시스템 서버가 수신된 데이터를 파싱(Parsing)하여 분석에 적합한 형태로 변환한다. |
| **5** | 변환된 데이터를 다음 단계인 AI 분석 요청 유스케이스로 전달한다. |

<br>

| EXTENSION SCENARIOS | |
| :--- | :--- |
| **Step** | **Branching Action** |
| **1** | **1a. API 호출 횟수 제한(Rate Limit)을 초과한 경우.**<br>1a1. 잠시 후 재시도하도록 큐에 대기시키거나 사용자에게 지연 메시지를 출력한다. |
| **2** | **2a. 특정 항목(예: 최신 분기 재무제표)의 데이터가 누락된 경우.**<br>2a1. 가용한 최신 데이터를 가져오거나 누락된 상태로 분석을 진행하되, 사용자에게 주의 사항을 표시한다. |

<br>

| RELATED INFORMATION | |
| :--- | :--- |
| **Performance** | 외부 API 통신을 포함하여 전체 데이터 수신 과정은 2초 이내에 완료되어야 한다. |
| **Frequency** | 종목 검색 시 및 설정된 주기마다 실시간 발생 |
| **Concurrency** | API 제공업체의 동시 접속 제한 규정에 따름 |
| **Due Date** | 2026-05-31 |
| **Etc** | 유료 API 사용 시 트래픽 비용 최적화를 위해 캐싱(Caching) 전략을 병행해야 함. |

### 2.2.7 Request AI Analysis

| Use Case Name | Use Case ID | Korean Name | Actor |
| :--- | :--- | :--- | :--- |
| **Request AI Analysis** | #7 | AI 분석 요청 | Gemini API |

<br>

| Use Case #7 : Request AI Analysis | |
| :--- | :--- |
| **GENERAL CHARACTERISTICS** | |
| **Summary** | 수집된 주식 로우 데이터(Raw Data)와 관리자가 설정한 평가 가치 기준을 Gemini API에 전달하여 텍스트 및 수치 기반의 심층 분석을 요청한다. |
| **Scope** | Market analyst tool |
| **Level** | Sub-function level |
| **Author** | Bae GeunWong |
| **Last Update** | May. 5. 2026 |
| **Status** | Under Review |
| **Primary Actor** | Gemini API |
| **Secondary Actors** | Server |
| **Preconditions** | 주식 데이터 수집(Use Case #7)이 완료되고 유효한 API Key가 설정된 상태. |
| **Trigger** | 종목 데이터가 서버에 적재되어 AI의 판단(매수/매도/보유)이 필요한 시점 |
| **Success Post Condition** | Gemini API가 프롬프트를 수신하고 분석 프로세스를 시작한다. |
| **Failed Post condition** | API 호출 실패 또는 타임아웃 발생 시 사용자에게 분석 지연 알림을 전달한다. |

<br>

| MAIN SUCCESS SCENARIO | |
| :--- | :--- |
| **Step** | **Action** |
| **1** | 시스템 서버가 수집된 주식 데이터와 최신 평가 가치 가이드라인을 조합하여 프롬프트를 구성한다. |
| **2** | 시스템이 Google Generative AI 라이브러리를 통해 Gemini API에 분석 요청을 전송한다. |
| **3** | Gemini API가 전달받은 컨텍스트(데이터+기준)를 바탕으로 추론 프로세스를 수행한다. |
| **4** | 서버는 API의 응답을 대기하며 연결 상태를 유지한다. |
| **5** | 분석이 시작되었음을 시스템 로그에 기록하고 다음 유스케이스(결과 생성)로 제어권을 넘긴다. |

<br>

| EXTENSION SCENARIOS | |
| :--- | :--- |
| **Step** | **Branching Action** |
| **1** | **1a. 할당된 API 쿼터(Quota)를 초과한 경우.**<br>1a1. 사용자에게 일시적인 서비스 이용 제한을 알리고 대기 시간을 안내한다. |
| **2** | **2a. 전달된 데이터의 양이 토큰 제한을 초과할 경우.**<br>2a1. 데이터를 중요도 순으로 요약하여 프롬프트를 재구성한 뒤 재요청한다. |

<br>

| RELATED INFORMATION | |
| :--- | :--- |
| **Performance** | API 호출 및 프롬프트 전달은 1초 이내에 완료되어야 한다. |
| **Frequency** | 사용자별 종목 분석 요청 시마다 발생 |
| **Concurrency** | API 모델의 동시 처리 제한(RPM/TPM) 범위 내에서 수행 |
| **Due Date** | 2026-05-31 |
| **Etc** | 최신 트렌드 반영을 위해 분석 요청 시 관리자가 수정한 '평가 가치' 가이드라인이 최우선적으로 프롬프트에 포함되어야 함. |

### 2.2.8 Generate Analysis Result

| Use Case Name | Use Case ID | Korean Name | Actor |
| :--- | :--- | :--- | :--- |
| **Generate Analysis Result** | #9 | 분석 결과 생성 | Gemini API |

<br>

| Use Case #9 : Generate Analysis Result | |
| :--- | :--- |
| **GENERAL CHARACTERISTICS** | |
| **Summary** | Gemini API로부터 수신한 추론 데이터를 파싱하여 사용자에게 최적화된 형태의 매수/매도 판단 결과 및 심층 분석 리포트를 생성하고 출력한다. |
| **Scope** | Market analyst tool |
| **Level** | User level |
| **Author** | Bae GeunWong |
| **Last Update** | May. 5. 2026 |
| **Status** | Under Review |
| **Primary Actor** | Gemini API |
| **Secondary Actors** | Server, Database |
| **Preconditions** | AI 분석 요청(Use Case #7)에 대한 응답 데이터가 성공적으로 서버에 도달한 상태. |
| **Trigger** | AI의 연산이 완료되어 결과 데이터가 수신되었을 때 |
| **Success Post Condition** | 정제된 분석 결과가 사용자 화면에 출력되고, 추후 조회를 위해 데이터베이스에 저장된다. |
| **Failed Post condition** | 데이터 형식이 올바르지 않거나 생성 실패 시, 기본 안내 메시지를 출력하고 재시도를 유도한다. |

<br>

| MAIN SUCCESS SCENARIO | |
| :--- | :--- |
| **Step** | **Action** |
| **1** | 시스템 서버가 Gemini API로부터 전달받은 텍스트 및 수치 데이터를 수신한다. |
| **2** | 수신된 텍스트에서 매수/매도/보유 등급과 핵심 근거 문장을 추출하여 구조화한다. |
| **3** | 관리자가 설정한 레이아웃 가이드라인에 맞춰 분석 리포트의 시각적 컴포넌트를 구성한다. |
| **4** | 생성된 분석 결과물을 사용자의 웹/모바일 대시보드에 실시간으로 출력한다. |
| **5** | 분석 일시, 종목, 결과 데이터를 히스토리 관리를 위해 데이터베이스에 저장한다. |

<br>

| EXTENSION SCENARIOS | |
| :--- | :--- |
| **Step** | **Branching Action** |
| **1** | **1a. AI 응답 형식이 지정된 포맷(JSON 등)을 벗어난 경우.**<br>1a1. 시스템이 텍스트 클리닝 및 재구조화 로직을 실행하여 최대한 가용한 정보를 추출한다. |
| **2** | **2a. 분석 결과 생성 중 네트워크 끊김이 발생할 경우.**<br>2a1. 저장된 데이터를 바탕으로 사용자가 재접속 시 분석 완료 알림을 전송한다. |

<br>

| RELATED INFORMATION | |
| :--- | :--- |
| **Performance** | API 수신 후 리포트 구성 및 화면 출력까지 3초 이내에 완료되어야 한다. |
| **Frequency** | 분석 요청마다 1회 발생 |
| **Concurrency** | 다수의 사용자가 동시에 각기 다른 종목의 분석 결과를 수신 및 저장 가능 |
| **Due Date** | 2026-05-31 |
| **Etc** | 분석 결과에는 항상 'AI의 분석 결과는 투자 참고용이며 최종 책임은 투자자 본인에게 있다'는 경고 문구를 포함해야 함. |

## 3.Domain analysis
아래의 그림은 Domain Analysis 에서 나오는 Class 들의 관계를 앞으로 구현할 프로젝트를의 방향성에 맞게 제시한 것이다.
<img width="1024" height="531" alt="image" src="https://github.com/user-attachments/assets/8b71b7c1-7534-4f2c-9693-98c1d15ab1e7" />






