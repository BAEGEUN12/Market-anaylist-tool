# Market Analyst Tool


<img width="1206" height="677" alt="image" src="https://github.com/user-attachments/assets/12046886-e2c1-4c19-97f2-be61dc5adacf" />

### <시장분석UI예시>
## 기본 정보

- **학번:** 22212027  
- **이름:** 배근웅  

---

##  GitHub Repository

- https://github.com/BAEGEUN12/Market-anaylist-tool
## Contents

- [1. Business purpose](#1-business-purpose)
- [2. System context diagram](#2-system-context-diagram)
- [3. Use case list](#3-use-case-list)
- [4. Concept of operation](#4-concept-of-operation)
- [5. Problem statement](#5-problem-statement)
- [6. Glossary](#6-glossary)
- [7. References](#7-references)
## 1. Business Purpose 

최근 주식 투자에 대한 관심이 크게 증가하면서 많은 사람들이 주식 시장에 참여하고 있다.  
이러한 관심 증가는 모바일 트레이딩 시스템(MTS)의 보편화, 온라인 정보 접근성 향상, 저금리 환경으로 인한 투자 대안 탐색 등의 요인에 의해 촉진되었다.

그러나 상당수의 개인 투자자들은 충분한 지식이나 체계적인 분석 없이 감에 의존하거나 단순한 정보만을 기반으로 투자하는 경우가 많다.  
이로 인해 비효율적인 투자 판단이나 손실이 발생할 가능성이 높아지고 있으며, 주식 분석에 대한 접근성과 이해도를 높이는 도구의 필요성이 커지고 있다.
특히, 금융 시장에서는 데이터와 수학적 모델을 기반으로 한 알고리즘 트레이딩이 널리 활용되고 있으며, 이는 감정에 의존하지 않고 객관적인 기준을 통해 투자 의사결정을 수행한다는 특징을 가진다.
예를 들어월가(Wall Street)에서는 수학적 알고리즘과 데이터 기반 모델을 활용한 정교한 매매 시스템이 활용되고 있으며, 이는 감정에 의존하지 않고 객관적인 분석을 통해 투자 의사결정을 수행한다는 점에서 높은 효율성을 보인다.
비록 이러한 구체적인 알고리즘은 공개되어 있지 않지만, 데이터 기반 분석과 정량적 접근 방식 자체는 개인 투자자에게도 충분히 적용 가능한 개념이다.

본 프로젝트는 이러한 알고리즘 기반 투자 방식의 원리를 바탕으로, 일반 사용자도 쉽게 활용할 수 있는 주식 분석 시스템을 구현하는 것을 목표로 한다.
본 프로젝트의 목적은 다음과 같다:

- 사용자가 주식 종목을 입력하면 관련 데이터를 자동으로 수집
- 차트 및 데이터를 시각적으로 제공
- AI 기반 분석을 통해 추세 및 의견(매수/매도/관망)을 제시
- 초보자도 쉽게 이해할 수 있도록 직관적인 분석 결과 제공

이를 통해 사용자는 보다 체계적이고 합리적인 투자 판단을 내릴 수 있으며,  
주식 시장에 대한 접근성을 향상시킬 수 있다.

####  Background(근거자료)개인투자자의 주식 관심도 증가 연합뉴스 https://www.yna.co.kr/view/AKR20210326105600030
### Expected Benefit

- 초보 투자자의 의사결정 지원
- 데이터 기반 투자 습관 형성
- 주식 분석 접근성 향상

## 2.System context diagram
<img width="1169" height="568" alt="image" src="https://github.com/user-attachments/assets/6d09eefd-95e3-48c8-9429-9e0ed5f990b2" />
 System Interaction

● User → System  
: 사용자는 주식 종목명을 입력하고 분석을 요청한다.

● System → Stock API  
: 시스템은 해당 주식의 데이터를 요청한다.

● Stock API → System  
: 주식 데이터 및 과거 데이터가 시스템으로 전달된다.

● System → Gemini API  
: 시스템은 데이터를 Gemini API에 전달하여 분석을 요청한다.

● Gemini API → System  
: AI는 추세 및 투자 의견을 생성하여 반환한다.

● System → User  
: 시스템은 차트와 분석 결과를 사용자에게 제공한다.

 ####  <단 판단의 근거가되는 Rsi, 엘리어트 파동, 패턴, 큰 시간선에서 작은 시간선 등은 명확하게 AI가 판단할 수 있는 기준점 제시를 해야함>
## 3. Use Case List

### UC-01: Enter Stock Name
- Actor: User
- Description: 사용자가 분석을 원하는 주식 종목명을 입력한다.

---

### UC-02: Request Stock Data
- Actor: System
- Description: 시스템이 외부 Stock API를 통해 해당 주식의 데이터를 요청한다.

---

### UC-03: Display Stock Chart
- Actor: System
- Description: 수집된 데이터를 기반으로 주식 차트를 사용자에게 시각적으로 제공한다.

---

### UC-04: Request AI Analysis
- Actor: System
- Description: 수집된 주식 데이터를 Gemini API에 전달하여 분석을 요청한다.

---

### UC-05: Generate Analysis Result
- Actor: Gemini API
- Description: AI가 주식 데이터를 분석하여 추세 및 투자 의견을 생성한다.

---

### UC-06: Display Analysis Result
- Actor: System
- Description: 분석 결과(추세, 매수/매도/관망 의견)를 사용자에게 표시한다.

---

### UC-07: View Analysis Result
- Actor: User
- Description: 사용자가 시스템이 제공한 분석 결과를 확인한다.



## 4. Concept of Operation (운용 개념)

본 주식 분석 시스템은 사용자가 주식 데이터를 보다 쉽게 이해하고, 합리적인 투자 판단을 내릴 수 있도록 지원하기 위해 설계되었다.  
사용자는 간단한 입력만으로 주식 데이터를 조회하고, AI 기반 분석 결과를 확인할 수 있다.

---

### 4.1 개요 (Overview)

본 시스템은 클라이언트 기반으로 동작하며, 외부 API와 직접 통신하여 기능을 수행한다.  
주식 데이터는 외부 Stock API를 통해 수집되며, 수집된 데이터는 AI(Gemini API)를 통해 분석된다.

전체 동작은 다음과 같은 단계로 이루어진다:
- 사용자 입력
- 데이터 수집
- 데이터 분석
- 결과 출력

---

### 4.2 동작 흐름 (Operational Flow)

1. 사용자가 분석하고자 하는 주식 종목명 또는 코드를 입력한다.
2. 시스템은 외부 Stock API에 요청을 보내 해당 주식의 데이터를 가져온다.
3. 시스템은 주가 데이터 및 과거 데이터를 수신한다.
4. 수집된 데이터를 분석에 적합한 형태로 가공한다.
5. 가공된 데이터를 Gemini API에 전달하여 분석을 요청한다.
6. Gemini API는 데이터를 기반으로 추세 및 투자 의견을 생성한다.
7. 시스템은 분석 결과를 수신한다.
8. 시스템은 주식 차트와 함께 분석 결과를 사용자에게 시각적으로 제공한다.
9. 사용자는 결과를 확인하고 투자 판단에 활용한다.

---

### 4.3 시스템 환경 (System Environment)

- 본 시스템은 웹 브라우저 환경에서 실행된다.
- 별도의 서버 없이 클라이언트에서 직접 API를 호출한다.
- 주식 데이터 및 분석은 외부 API(Stock API, Gemini API)에 의존한다.

---

### 4.4 가정 및 제약사항 (Assumptions and Constraints)

- 사용자는 인터넷에 연결되어 있어야 한다.
- 외부 API가 정상적으로 동작해야 한다.
- API 호출 횟수 제한이 존재할 수 있다.
- 본 시스템은 투자 참고용 분석을 제공하며, 실제 투자 결과를 보장하지 않는다.

---

### 4.5 기대동작(Expected Behavior)

- 사용자 입력에 대해 빠르게 응답해야 한다.
- 분석 결과는 직관적이고 이해하기 쉽게 제공되어야 한다.
- 잘못된 입력이나 API 오류 발생 시 적절한 안내 메시지를 제공해야 한다.
## 5. Problem Statement (문제 정의)

### Overview

본 주식 분석 시스템은 사용자가 별도의 전문 지식 없이도 주식 데이터를 이해하고,  
분석 결과를 통해 보다 합리적인 투자 판단을 내릴 수 있도록 지원하는 것을 목적으로 한다.

현재 많은 개인 투자자들은 충분한 분석 없이 직관이나 단편적인 정보에 의존하여 투자 결정을 내리는 경우가 많으며,  
이로 인해 비효율적인 투자 및 손실이 발생할 가능성이 높다.

본 시스템은 다음과 같은 목적을 달성해야 한다:

- 주식 데이터를 정확하게 수집 및 제공
- 사용자에게 직관적인 차트 및 분석 결과 제공
- AI 기반 분석을 통한 투자 판단 지원
- 초보자와 일반 사용자 모두가 쉽게 접근 가능한 시스템 제공

---

### 1) Problem #1

주식 데이터의 정확성이 보장되어야 한다.  
데이터 수집 과정에서 오류나 누락이 발생할 경우, 사용자에게 잘못된 정보를 제공하게 되어 잘못된 투자 판단으로 이어질 수 있다.

특히, 외부 API로부터 데이터를 수집하는 과정에서 지연이나 오류가 발생할 수 있으며,  
이는 시스템의 신뢰성을 저하시킬 수 있는 중요한 요소이다.

---

### 2) Problem #2

AI 분석 결과의 일관성과 신뢰성이 확보되어야 한다.  
명확한 분석 기준 없이 AI가 데이터를 해석할 경우, 동일한 데이터에 대해서도 서로 다른 결과가 도출될 수 있다.

따라서, 이동평균선, RSI 등의 명확한 분석 기준을 설정하고 이를 기반으로 AI가 분석을 수행하도록 설계해야 한다.

---

### 3) Problem #3

사용자 정보 및 시스템 보안 문제가 발생할 수 있다.  
특히 API 키와 같은 민감한 정보가 노출될 경우, 외부에서 무단으로 시스템을 사용할 가능성이 있다.

또한, 향후 사용자 데이터를 저장하거나 확장 기능을 추가할 경우 개인정보 보호 및 보안 문제가 발생할 수 있으며,  
이에 대한 적절한 보안 대책이 필요하다.
## 6. Glossary (용어 정의)

● Stock  
: 기업의 소유권을 나타내는 증권으로, 주식 시장에서 거래된다.

● Stock API  
: 주식 가격, 거래량, 과거 데이터 등의 금융 정보를 제공하는 외부 서비스이다.

● Gemini API  
: Google에서 제공하는 AI 서비스로, 데이터 분석 및 자연어 기반 결과를 생성한다.

● Stock Analysis  
: 주식 데이터를 기반으로 시장의 흐름, 추세, 투자 가능성을 평가하는 과정이다.

● Trend (추세)  
: 주식 가격이 일정 기간 동안 상승, 하락, 또는 횡보하는 방향성을 의미한다.

● Buy / Sell / Hold  
: 투자 판단을 나타내는 용어로, 각각 매수, 매도, 관망을 의미한다.

● Moving Average (이동평균선)  
: 일정 기간 동안의 평균 주가를 계산하여 가격 흐름을 파악하는 지표이다.

● RSI (Relative Strength Index)  
: 주식이 과매수 또는 과매도 상태인지 판단하는 기술적 지표이다.

● Frontend  
: 사용자가 직접 상호작용하는 인터페이스(웹 화면)를 의미한다.

● Server  
: 데이터를 처리하고 외부 API와 통신하는 시스템 구성 요소이다.

● API (Application Programming Interface)  
: 서로 다른 소프트웨어 간에 데이터를 주고받을 수 있도록 하는 인터페이스이다.

● Data Processing  
: 수집된 데이터를 분석에 적합한 형태로 정리하고 변환하는 과정이다.
## 7. References 

1. Statista – Retail Investing Trends  
https://www.statista.com/topics/4414/retail-investing/

2. Google Gemini API Documentation  
https://ai.google.dev/

3. Investopedia – Stock Market Basics  
https://www.investopedia.com/terms/s/stockmarket.asp

