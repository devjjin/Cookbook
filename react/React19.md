## React19 소식

### 1. React 컴파일러
- React를 위한 컴파일러 개발중, 연구 단계는 끝났으며 오픈소스로 출시 준비중
- `useMemo`, `useCallback` 자동 최적화
- instagram.com도 React 컴파일러가 컴파일함

### 2. 액션
- 클라이언트-서버 데이터 전송을 도와주는 "액션" 추가
- `useFormStatus`, `useFormState`, `useOptimistic` 훅 추가
- 폼 개발 경험이 더 좋아질 것으로 기대

### 3. React Canary(테스트 버전)의 새 기능
- 지시자: `"use client"`, `"use server"` 지시자 추가 (Next.js의 그것)
- 메타 데이터: `<title />` 등 메타 태그를 어디서든 작성할 수 있게 지원 (React Helmet이 해주던 일)
- 에셋 로딩: `<style>`, `<link>`, `<script>` 태그 사용 시 리소스 완전 로드 및 초기화까지 React가 내용 표시 지연 처리. 페이지 불완전 로드 방지 및 빠른 페이지 로딩을 도와줌
- 액션: 앞에서 설명한 내용과 동일

### 4. React 다음 버전
- 곧 react@canary 배포 예정
- React 19 출시 준비 중 (출시일 미정)


출처 : https://react.dev/blog/2024/02/15/react-labs-what-we-have-been-working-on-february-2024
