# React + TS Slack clone

Will update readme, with my note <br>

return 안에 있는 애들은 useCallback 이용해야 최적화된다. 불필요한 리렌더 없다.

useMemo : 함수 값을 캐싱<br>
useCallback : 함수 자체를 캐싱<br>


axios 장점 : server, client 동일 문법 사용 가능 <br>
<pre>
CORS 트러블 슈팅 : 브라우저에서 서버로 요청보내면 터짐
서버 <> 서버 는 CORS에러 안뜸
webpack.config.js >>  
devServer : { 
    proxy : {
        '/api/':{
            changeOrigin: true,
            target: 'http://localhost:3095'
        }
    }
}
i.e) front >> loaclhost:3090(front 'server') >> localhost:3095(back 'server')
</pre>
<pre>
POST 내용 안보이게 하려면 https로 배포
</pre>
<pre>
useSWR : redux를 대체할 수 있을정도로 강력
npm i swr
const { data:userData (changename), error, revalidate(서버에서 최신인지 확인), mutate(React내에서 데이터 변경해서 가지고 있고 싶다.)} = useSWR
withCredentials : login 했을때는 쿠키 같이 보내기 위해 사용해라

</pre>
<pre>
?. :: optional chaning? 
</pre>
<pre>
<strong>/:workspace : route parameter >> useParams</strong>
</pre>
<pre>
event 같은 상호작용, 기능이 있다? > component
단순 style만 있다? > styled component
</pre>
<pre>
optimistic UI e.g) mutate

loadable-component >> code splitting >> opmization  필요할때만 import 해서 실행 (dynamic import)
</pre>

<pre>
websocket : ws
socket.io : ws, http

memo : 부모가 리렌더 되더라도, 자식의 state가 바뀌지 않았다면 해당 자식은 re-render 되지 않는다.
</pre>