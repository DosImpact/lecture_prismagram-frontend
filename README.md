# 4 Frontend Setup

# 4.0 CRA Cleanup and Installation (5:45)

- 환경 설치

- yarn add styled-components react-router-dom prop-types react-helmet styled-reset
- yarn add react-apollo-hooks apollo-boost graphql graphql-tag
- yarn add react-toastify

# 4.1 GlobalStyles and Theme (12:06)

- Styles - 글로벌 스타일 컴포넌트 적용
- Theme컴포넌트 기능!! : 색상을 따로 빼서 -> ThemeProvider 컴포넌트 사용. from "styled-component"

# 4.2 React Router (9:15)

# 4.3 Apollo Client (12:06)

- Apollo - Client 아폴로 클라이언트 연결해줌, LocalState를 리덕스 대신 사용할거임, 로그인 처리.

# 4.4 First Hooks Query (8:0

- 아폴로 훅 사용해보기. gql이 원래는 graphql-tag에서 가져왔는데, apollo-boost에서 가져왔네, 클라이언트도,
- useQuery는 쿼리문을 넣고, data,error,loading 을 반환 const { data, error, loading } = useQuery(GET_DOGS);
- 쿼리문에 @client를 통해, localState에 접근한다.

```js
...
import { gql } from "apollo-boost";
import { useQuery } from "react-apollo-hooks";

const QUERY = gql`
  {
    isLoggedIn @client
  }
`;

export default () => {
  const { data } = useQuery(QUERY);
  console.log(data);
  return (
    <>
      <ThemeProvider theme={Theme}>
        <>
          <AppRouter isLoggedIn={false} />
          <GlobalStyles />
        </>
      </ThemeProvider>
    </>
  );
};
```

# 추가학습 리액트 훅

- 결론적으로, 훅은 함수형 컴포넌트에서도 state를 사용할수 있게 해주는것이다.
- useState랑 useEffect from "react" 변수 변경, 그리고 API 에서 데이터를 요청할때 사용함.
- useState는 배열로 2개원소 리턴 예제:

```js
import React, { useState } from "react";
import "./styles.css";

export default function App() {
  const [count, setCount] = useState(0);
  const [email, setEmail] = useState("");
  const updateEmail = e => {
    const {
      target: { value }
    } = e;
    setEmail(value);
  };
  return (
    <div className="App">
      <h2>Start editing to see some magic happen!</h2>
      {count}
      <button onClick={() => setCount(count + 1)}>PLUSE</button>
      <button onClick={() => setCount(count - 1)}>MINUS</button>
      <input placeholder="email" onChange={updateEmail} />
      {email}
    </div>
  );
}
```

# 5 Frontend: Authorization Routes

# 5.0 Auth Route UI part One (6:50)

- 훅을 써서 Container,Presenter를 되도록 줄이겠지만, 필요하다면 사용해도 된다.
- Auth.js 작업

# 5.1 Footer and Auth UI part Two (5:00)

# 5.2 Footer and Auth UI part Three (5:00)

# 5.3 Auth Form with Hooks (10:36)

# 5.4 requestSecret Mutation and Refactor (12:03)

# 5.5 Toastify and createAccount Mutation (14:17)

# 5.6 createAccount Mutation part Two (13:03)

# 5.7 createAccount Mutation part Three (8:30)

# 5.8 confirmSecret + Log In Mutation (16:03)
