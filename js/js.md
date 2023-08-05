
### 자바스크립트

- **자바스크립트의 특징은?**
    - 자바스크립트는 HTML, CSS와 함께 웹을 구성하는 요소 중 하나로 웹 브라우저에서 동작하는 유일한 프로그래밍 언어입니다.
    - 자바스크립트는 개발자가 별도의 컴파일 작업을 수행하지 않는 **인터프리터 언어입니다.**
        
        **인터프리터는 소스코드를 즉시 실행하고** **컴파일러는 빠르게 동작하는 머신 코드를 생성하고 최적화한다.** 이를 통해 컴파일 단계에서 추가적인 시간이 필요함에도 더욱 빠르게 코드를 실행할 수 있다.
        
    - 자바스크립트는 **런타임에 컴파일되며 실행 파일이 생성되지 않고 인터프리터의 도움 없이 실행할 수 없기 때문에 컴파일러 언어라고 할 수는 없습니다.**

### 변수

- **var 키워드의 문제점은?**
    - 변수 중복 선언을 허용하여 변수값이 의도치 않게 재할당되어 변경됩니다.
    - 함수 레벨 스코프
    - 변수 호이스팅
- **var 키워드는 let 키워드와 차이점은?**
    
    
    1. 변수 중복 선언 금지
    
    2. 블록 레벨 스코프
    3. 변수 호이스팅
    4. 전역 객체와 let
    채
    
- **const 키워드**
    
    상수를 선언하기 위해 사용하지만 반드시 상수만을 위해 사용하지 않는다. let 키워드와 대부분 동일하므로 let과의 차이점을 살펴본다.
    
    ```jsx
    1. 선언과 초기화
    2. 재할당 금지
    3. 상수
    ```
    
    - const 키워드로 선언한 변수는 **반드시 선언과 동시에 초기화**해야 한다. 그렇지 않을 경우 문법 에러(SyntaxError)가 발생한다.
    - 원시 값은 변경 불가능한 값이므로 재할당 없이 값을 변경할 수 있는 방법이 없기 때문이다.
- **클로저(closure)란**
    - 외부 함수가 종료되어 소멸된 후에도 내부 함수가 외부 함수의 지역변수를 여전히 참조할 수 있는 현상
    - 어떻게?
        - 자바스크립트 함수가 선언될 때 자신의 상위 스코프 환경을 기억하고 있기 때문에
    - 사용하는 이유?
        - 외부 함수가 소멸되고 난뒤에 내부 함수가 무방비하게 전역 변수를 참조해버리는 의도치 않은 전역 오염 바이
    - 단점
        - 메모리 누수 : 외부 함수의 지역 변수가 메모리에 계속 살아 있음
    - 해결법
        - 클로저 사용이 끝난 후 변수에 명시적으로 null을 할당해 가비지 컬렉터가 정리하도록 함
    - 
- **호이스팅(hoisting)이란**
    
    호이스팅은 변수와 함수 선언을 코드 상단으로 끌어올린 것처럼 코드 실행 전에 선언된 변수와 함수들이 메모리에 할당되어 준비되는 것을 의미합니다.
    
    • **`let`**과 **`const`**를 사용하여 변수를 선언하면 호이스팅에 의해 선언은 되지만, TDZ(Temporal Dead Zone)에 빠지므로 초기화 이전에는 변수에 접근할 수 없습니다.
    
- **이벤트 루프(event loof)란**
    
    
- **TDZ(Temporal Dead Zone)이란?**
    
    스코프의 시작 지점부터 초기화 시작 지점까지 변수를 참조할 수 없는 일시적 사각지대 구간을 의미합니다.
    
- **깊은복사와 얕은 복사**

### 배열

- **자바스크립트의 배열은 자료구조의 배열과 같나요?**
    
    자바스크립트의 배열은 일반적인 배열의 동작을 흉내낸 특수한 객체입니다.
    
    일반적인 배열은 하나의 데이터 타입으로 통일되어 있고 **동일한 크기의 메모리 공간**이 **연속**적으로 나열된 밀집 배열입니다.
    
    자바스크립트의 배열의 각각의 메모리 공간의 **크기는 동일하지 않아도 되며**, **연속적으로 이어져 있지 않을 수** 도 있습니다. (희소배열이라고도 합니다.)
    
- **배열의 메서드는 어떤 종류가 있나요?**
    
    배열은 크게 두 종류로 나눌 수 있습니다.
    
    - `① 원본 배열을 **직접 변경**하는 메서드`
    - `② 원본 배열을 직접 변경하지 않고 **새로운 배열을 생성하여 반환**하는 메서드`가 있다.
    
    ES5부터 도입된 배열 메서드는 대부분 원본 배열을 직접 변경하지 않지만 초창기 배열 메서드는 원본 배열을 직접 변경하는 경우가 많다. 원본 배열을 직접 변경하는 메서드는 외부 상태를 직접 변경하는 부수효과가 있으므로 사용할 때 주의해야 한다. 가급적 원본 배열을 직접 변경하지 않는 메서드를 사용하는 편이 좋다.
    
    ```
    Array.isArray 🌟
    Array.prototype.indexOf 🌟
    Array.prototype.push (원본 배열을 변경한다 - 부수효과 o)
    Array.prototype.pop (원본 배열을 변경한다 - 부수효과 o)
    Array.prototype.unshift (원본 배열을 변경한다 - 부수효과 o)
    Array.prototype.shift (원본 배열을 변경한다 - 부수효과 o)
    Array.prototype.concat 🌟
    Array.prototype.splice 🌟 (원본 배열을 변경한다 - 부수효과 o)
    Array.prototype.slice 🌟
    Array.prototype.join 🌟 (원본 배열을 변경한다 - 부수효과 o)
    Array.prototype.reverse 🌟 (원본 배열을 변경한다 - 부수효과 o)
    Array.prototype.fill 🌟 (원본 배열을 변경한다 - 부수효과 o)
    Array.prototype.includes 🌟
    ```
    
- **고차 함수에 대해서 아나요?**
    
    고차 함수(Higher-Order Function, HOF)는 **함수를 인수로 전달받거나 함수를 반환하는 함수**를 말한다.
    
    자바스크립트의 함수는 **일급 객체**이므로 함수를 값처럼 인수로 전달할 수 있으며 반환할 수도 있다.
    
    고차 함수는 외부 상태의 변경이나 가변(mutable) 데이터를 피하고 불변성(immutability)을 지향하는 함수형 프로그래밍에 기반을 두고 있다.
    
    함수형 프로그래밍은 순수 함수와 보조 함수의 조합을 통해 로직 내에 존재하는 조건문과 반복문을 제거하여 복잡성을 해결하고 변수의 사용을 억제하여 상태 변경을 피하려는 프로그래밍 패러다임이다.
    
    함수형 프로그래밍은 순수 함수를 통해 부수 효과를 최대한 억제하여 오류를 피하고 프로그램의 안정성을 높이려는 노력의 일환이라고 할 수 있다.
    
- **forEach 메서드와 map메서드의 차이점에 대해 알고 있나요?**
    
    

### 원시 값과 객체 비교

- **동적 타이핑을 지원하는 자바스크립트에서 데이터 타입을 2개로 나누는 이유는?**
    
    
- **값에 의한 전달(Call-by-value)이란?**
    - 변수에 원시 값을 갖는 변수를 할당하면 할당받는 변수(copy)에는 할당하는 변수(score)의 원시 값이 복사되어 전달된다. 이를 **'값에 의한 전달'** 이라 한다.
    - **다른 메모리 공간에 저장된 별개의 값**이다. 따라서 score 변수의 값을 변경해도 copy 변수의 값에는 어떠한 영향도 주지 않는다.
        
        !https://github.com/junh0328/prepare_frontend_interview/raw/main/images/11_4.jpg
        
- **참조에 의한 전달이란?**

### 스코프

- **스코프란 무엇인가요?**
    
    스코프는 **식별자가 유효한 범위**를 의미합니다.
    
    자바스크립트는 **변수를 참조할 때 어떤 값을 참조할지를 스코프를 통해 결정**합니다.
    
- **스코프의 종류를 설명해주세요.**
    
    스코프는 **전역 스코프**와 **지역 스코프**로 나뉩니다.
    
    전역 스코프는 코드의 가장 바깥 영역의 스코프이고, 지역 스코프는 특정 지역 내부에서만 사용되는 스코프입니다.
    
    전역 스코프는 어디에서든 참조할 수 있고, 지역 스코프는 해당 함수와 그 하위 함수에서만 참조할 수 있습니다.
    
- **렉시컬 스코프에 대해 설명해주세요.**
    
    렉시컬 스코프는 함수를 어디서 ‘**정의**’했는지에 따라 **상위 스코프가 정적으로 결정**되는 방식입니다. 
    
    다른 말로 **정적 스코프**라고도 합니다.
    
    cf. **동적 스코프**는 함수가 ‘호출’되는 시점에 동적으로 상위 스코프를 결정합니다.
    
- **전역 변수로 선언했을 때의 문제점이 있나요?**
    - 전역 변수는 코드 어디서든 참조할 수 있고 할당할 수 있는 유효범위가 넓습니다. (암묵적 결합)
    - 그리고 생명 주기도 길기 때문에 오랫동안 변경될 수 있습니다.
    - 자바스크립트는 하나의 전역 스코프를 공유하기 때문에 다른 파일에서 동일한 이름의 전역 변수를 사용한다면 예상하지 못한 결과를 얻을 수도 있습니다.
    - 또 전역 변수를 참조하기 위해서는 스코프체인의 끝에 있기 때문에 검색 속도가 약간 느리다는 문제점이 있습니다.

### 이벤트

- **이벤트 전파(propagation)**
    
     **계층적 구조에 포함되어 있는 HTML 요소에 이벤트가 발생할 경우 연쇄적 반응이 일어나는 현상**입니다.
    
- **이벤트 전파 단계(캡처링, 버블링)**
    
    전파되는 방향에 따라 3단계로 구분할 수 있습니다.
    
    - **캡처링** 단계 : **자식** 요소에서 발생한 이벤트가 **부모** 요소부터 시작하여 **이벤트를 발생시킨 자식** 요소까지 도달하는 것
    - 타깃 단계 : 이벤트가 이벤트 타깃에 도달
    - **버블링** 단계: **자식** 요소에서 발생한 이벤트가 **부모** 요소로 전파되는 것
    
    **주의할 것은 버블링과 캡처링은 둘 중에 하나만 발생하는 것이 아니라 캡처링부터 시작하여 버블링으로 종료한다는 것이다.** 즉, 이벤트가 발생했을 때 캡처링과 버블링은 순차적으로 발생한다.
    
- **이벤트 위임(delegation)**
    
    **연속되는 태그에 대해서 공통적으로 이벤트를 줘야할 때 우리가 이벤트 핸들러를 바인딩할 해당 요소의 부모 요소에게 이를 위임하여 이벤트를 진행하는 것** 을 이벤트 위임 (event delegation) 이라 합니다.
    
- **e.preventDefault**
    
    e.preventDefault 메서드는 **요소 태그의 기본 동작을 중단시키는 메서드**입니다.
    
- **e.stopPropagation**
    
    e.stopPropagation 메서드는 **어느 한 요소를 이용하여 이벤트를 처리한 후 이벤트가 부모 요소로  전파되는 것을 중단시키기 위한 메소드**
    
    이벤트 객체의 경우 상위 태그에도 같은 이벤트가 존재한다면 (예를 들면 click 어트리뷰트가 두 요소 모두 존재하는 경우) 상위 태그의 해당 콜백 함수를 호출하는 특징이 있습니다.
    
- **디바운스(debounce)**
    
    즉 디바운스는 **짧은 시간 간격으로 발생하는 이벤트를 그룹화해서 마지막에 일정 시간이 경과된 이후 한 번만 이벤트 핸들러가 호출되도록 한다.**
    
- **쓰로틀링(throttling)**
    
     짧은 시간 간격으로 이벤트가 연속해서 발생하더라도 일정 시간 간격으로 이벤트 핸들러가 최대 한 번만 호출되도록 한다.
    
    쓰로틀은 짧은 시간 간격으로 연속해서 발생하는 이벤트를 그룹화해서 일정 시간 단위로 이벤트 핸들러가 호출되도록 호출 주기를 만든다.
    
    쓰로틀은 scroll 이벤트 처리나 무한 스크롤 UI 구현 등에 유용하게 사용
    

### 비동기

- **자바스크립트 엔진**
    
    자바스크립트 엔진은 단 하나의 실행 컨텍스트 스택 구조를 갖습니다.
    
    **한 번에 하나의 태스크(작업, 일)만 실행할 수 있는 싱글 스레드 방식으로 동작합니다.**
    
    실행 컨텍스트의 최상위 요소인 ‘실행 중인 실행 컨텍스트’를 제외한 모든 실행 컨텍스트는 모두 실행 대기 중인 태스크들이며, 대기 중인 태스크들은 현재 실행중인 실행 컨텍스트가 pop되어 제거되면 비로소 시작합니다.
    
    구글 v8 자바스립트 엔진은 2개 영역으로 구분된다.
    
    **1) 콜 스택 (call stack)**
    
    - 소스코드(전역 코드 및 함수 코드 등) 평가 과정에서 생성된 실행 컨텍스트가 추가되고 제거되는 스택 자료구조인 실행 컨텍스트 스택이 바로 콜 스택이다.
    - 함수를 호출하면 함수 실행 컨텍스트가 순차적으로 콜 스택에 푸시되어 순차적으로 실행된다. 자바스크립트 엔진은 단 하나의 콜 스택을 사용하기 때문에 최상위 실행 컨텍스트(실행 중인 실행 컨텍스트)가 종료되어 콜 스택에서 제거되기 전까지는 다른 어떤 태스크도 실행되지 않는다.
    
    **②힙 (heap)**
    
    - 힙은 **객체가 저장되는 메모리 공간**이다. 콜 스택의 요소인 실행 컨텍스트는 힙에 저장된 객체를 참조한다.
    - 메모리에 값을 저장하려면 먼저 값을 저장할 메모리 공간의 크기를 결정해야 한다. 객체는 원시 값과는 달리 크기가 정해져 있지 않으므로 할당해야 할 메모리 공간의 크기를 런타임에 결정(동적 할당)해야 한다. 따라서 객체가 저장되는 메모리 공간인 힙은 구조화되어 있지 않다는 특징이 있다.
    
    이처럼 콜 스택과 힙으로 구성되어 있는 자바스크립트 엔진은 단순히 태스크가 요청되면 콜 스택을 통해 요청된 작업을 순차적으로 실행할 뿐이다. 비동기 처리에서 ① 소스코드의 평가와 ② 실행을 제외한 모든 처리는 자바스크립트 엔진을 구동하는 환경인 브라우저 또는 Node.js가 담당한다.
    
    **3) 태스크 큐 (task queue/event queue/callback queue)**
    
    - setTimeout이나 setInterval과 같은 비동기 함수의 콜백 함수 또는 이벤트 핸들러가 일시적으로 보관되는 영역이다.
    
    4) 마이크로태스크 큐(
    
    - 태스크 큐와는 별도로 프로미스 후속 처리 메서드의 콜백 함수가 일시적으로 보관되는 마이크로태스크 큐도 존재한다.
- **동기 vs 비동기**
    - **동기(synchronous)**:
        - **현재 실행 중인 태스크가 종료될 때까지 다음에 실행될 태스크가 대기하는 방식**
        - 장점:  ****태스크를 **순서대로** 하나씩 처리하므로 **실행 순서가 보장**
        - 단점 : 앞선 태스크가 종료될때까지 이후 태스크들이 **블로킹됨**
    - **비동기(asynchronous)**
        - 현재 실행중인 태스크가 종료되지 않은 상태라 해도 **다음 태스크를 곧바로 실행**하는 방식
        - 장점 : 블**로킹이 발생하지 않음**
        - 단점 : **태스크의 실행 순서가 보장되지 않음.**
        - **① setTimeout/ setInterval ② HTTP 요청 ③ 이벤트 핸들러**
        - **콜백 함수, 프로미스 및 async/await 함수**를 제공하여, 작업이 완료될 때까지 기다리지 않고 다른 작업을 수행할 수 있음
- **콜백 함수?**
    
    다른 함수가 실행을 끝낸 뒤 실행되는 함수입니다.  다른 코드에 인자로 넘겨줌으로써 그 제어권도 함께 위임한 함수입니다. 
    
- **Promise란?**
    
    프로미스는 **자바스크립트 비동기 작업을 처리하는 객체로 es6에 도입된 기능**입니다. 
    
    **‘특정 코드의 실행이 완료될 때까지 기다리지 않고 다음 코드를 먼저 수행하는 특징**’이 있습니다.
    
    성공한 경우 resolve 를 호출해 결과를 반환하고, 실패한 경우 reject를 호출해  에러를 반환하며, 콜백지옥의 문제점을 해결할 수 있습니다. 
    
    `new Promise()`로 프로미스를 생성하고 종료될 때까지 pending, fulfilled, rejected의  3가지 상태를 갖습니다.
    
- **Promise의 상태를 설명해봐라.**
    - `new Promise()`로 프로미스를 생성하고 종료될 때까지 pending, fulfilled, rejected의  3가지 상태를 갖습니다.
    - **‘Pending(대기)’ 상태**는 Promise는 최초로 생성되어 비동기 처리 로직이 아직 완료되지 않은 상태입니다.
    - **Fulfilled(이행)상태**는 비동기 처리가 완료되어 프로미스 결과값을 반환해준 상태입니다.
    - **Rejected(실패)상태**는 비동기 처리가 실패하거나 오류가 발생한 상태입니다.
- **async/await 함수란?**
    
    async/await 함수는 JavaScript의 최신 기능 중 (ES8) 하나로 promise를 쉽게 사용할 수 있도록 해줍니다.
    
    기존 동기식 처리의 단점을 보완하고 가독성을 높혀주는 코드를 만들 수 있습니다.
    
    async 함수는 항상 프로미스를 반환하며, await 키워드를 사용하여 비동기 작업의 완료를 기다립니다. 
    
    async 함수에서 에러를 발생시킬 때는 throw를 사용하고, 에러를 잡아낼 때에는 try/catch 문을 사용합니다.
    
- **promise와 async/await의 차이점은?**
    
    **에러핸들링**과 **코드 가독성** 두가지 측면에서 차이점이 있습니다.
    
    먼저 promise는 catch()메소드를 이용해 에러핸들링을 하고, async/awiat는 에러 핸들링 대신 try-catch()문을 활용합니다.
    
    또, promise의 경우 .then()으로 결과를 반환하다보니 코드의 가독성이 좋지 않은데 비해, async/await의 경우 코드의 흐름을 읽기 쉬우며 가독성이 좋습니다.
    
- **이벤트 루프(event loop)**
    
      이벤트 루프는 **실행 대기 중인 비동기 함수가 있으면 해당 함수를 호출하고, 실행이 완료될 때까지 다음 비동기 함수를 호출**합니다. 따라서, 여러 개의 비동기 함수가 실행될 때 이들 함수는 동시에 실행되며, **이벤트 루프에 의해 비동기 함수의 실행 순서가 제어**됩니다.
    
- **마이크로태스크 큐**
    
    **마이크로태스크 큐** 는 **태스크큐** 와 별도의 큐로 **후속 처리 메서드의 콜백 함수가 일시 저장**된다.
    
    그 외의 비동기 함수 **① setTimeout/ setInterval ② HTTP 요청 ③ 이벤트 핸들러** 의 콜백 함수나 이벤트 핸들러는 태스크 큐에 일시 저장된다.
    
- **태스크 큐와 마이크로태스크 큐 중 어떤 것이 먼저 실행되나요?**
    
    **마이크로태스크 큐**는 태스크 큐보다 우선순위가 **높다.**
    
    따라서 이벤트 루프에서 마이크로태스크 큐에 쌓인 태스크를 먼저 콜 스택에 올려준 뒤, 태스크 큐에 잔여 태스크를 콜 스택에 올린다.