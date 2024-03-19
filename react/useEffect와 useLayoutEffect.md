## useLayoutEffect vs useEffect 

![image](https://github.com/devjjin/Cookbook/assets/38846447/c075a5bf-c2fc-4713-8c79-bb9c194d1383)


### useEffect
- useEffect는 컴포넌트들이 render와 paint 된 후(렌더링 이후) 비동기적으로 실행
- paint 이후 실행되기 때문에 useEffect 내부에 DOM 에 영향을 주는 코드가 있을 경우, 화면을 다시 그리므로 사용자 입장에서는 화면 깜빡임을 보게됨
- 이펙트 함수와 DOM 화면이 복잡해지면 렌더링 시간이 복잡해지거나, 상태값이 이펙트에 의존할 경우 화면이 깜박이는 현상을 겪을 수 있어 사용성을 해칠 수 있음

render→paint→useEffect 

### useLayoutEffect
- DOM이 업데이트 직후 동기적으로 실행
- useEffect의 깜빡임 문제를 해결하기 위해 등장한 훅임
- useEffect와 훅의 형태는 완전히 동일하지만, DOM을 그리기 전 useLayoutEffect가 실행됨
- render→useLayoutEffect→paint순으로 실행
HTML 영역을 화면에 그린다 👉 **useEffect 실행** 👉 state 호출 👉 HTML을 재렌더링
- useLayoutEffect는 컴포넌트들이 render 된 후 실행되며, 그 이후에 paint 가됨
- undefined를 반환함


### 실행순서
1) React에서는 컴포넌트를 마운팅한 후 해당 컴포넌트를 렌더링한다.
2) 마운팅 단계에서는 useState와 useReducer 등의 훅이 동작한다.
3) 이후 렌더링이 완료되면 DOM에 업데이트를 반영하고 LayoutEffect가 실행된다.
4) 그 다음에 브라우저에서 paint 과정이 일어나게 되고, paint 과정 이후에 비로소 useEffect가 실행된다.
