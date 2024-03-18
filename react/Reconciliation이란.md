## Reconciliation(재조정)

<img src="https://github.com/devjjin/Cookbook/assets/38846447/3cf441bc-e340-43fd-ac02-cad808fa0b8b" width="500" height="300"/>

- Virtual DOM 을 사용하여 UI 업데이트를 처리하는 과정 중 하나
- DOM 을 비교 후 변경된 부분만 실제 DOM에 적용하는 과정

### 장점
- **돔 조작 최소화** : 변경된 부분만 DOM에 적용하므로 불필요한 돔 조작 최소화해 성능 향상
- **최적화된 렌더링** : 변경된 부분만 업데이트 하므로 전체 UI를 다시 렌더링 할 필요 없으므로
- **사용자 경험 향상** : 빠른 UI업데이트 React는 변경된 부분만을 업데이트하고, 실제 DOM 조작을 최소화하여 웹 애플리케이션의 렌더링 속도를 빠르게
