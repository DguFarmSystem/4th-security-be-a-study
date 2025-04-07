### 💡 JWT 토큰 - Redis를 활용한 Refresh Token 적용기

저는 기존 Access Token만 사용하는 방식으로 인증하던 서비스에서 보안을 위해 Refresh Token을 적용했던 경험에서 느꼈던 점들에 대해 공유드리려고 합니다. 

토큰을 안 써보신분도 있을 거 같아 간단히 설명드리면 아래의 역할을 수행합니다.
- Access Token : API 요청 시 인증을 위해 사용되는 토큰
- Refresh Token : Access Token이 만료되었을 때 새로운 Access Token을 발급받기 위해 사용


### 1️⃣ 그래서 Refresh Token 왜 쓰는건데

저는 기존에 클라이언트가 로그인하면 Access Token을 발급받고, API 요청 시 해당 Access Token을 사용하여 인증하는 방식을 사용했습니다. 이 방식에서는 로그아웃 시 클라이언트가 Access Token을 로컬 스토리지에서 삭제하지만, 만약 Access Token이 탈취되면 해당 토큰은 만료될 때까지 계속 사용할 수 있는 보안 취약점이 존재했습니다. 또한 위와 같은 이유로 Access Token의 만료 시간이 길게 설정되면 보안에 취약해지며, 반대로 만료 시간을 너무 짧게 설정하면 사용자가 그만큼 재로그인을 반복해야 하는 불편함이 있었습니다.


### 2️⃣  Redis를 활용한 Refresh Token 도입기
따라서 보안 강화를 위해 Access Token의 만료 시간을 짧게 설정(30분~1시간)하고, Refresh Token(7일~한달)을 사용해 새로운 Access Token을 발급하고 갱신하는 방식으로 보안을 강화했습니다. 또한, Refresh Token은 서버 Redis에 저장하여 관리함으로써, 클라이언트에서 Refresh Token이 탈취되는 위험을 방지할 수 있었습니다. 결론적으로는 Access Token의 만료 시간이 짧게 설정되어도, Refresh Token을 통해 새로운 Access Token을 발급할 수 있어 보안을 유지하면서도 사용자의 불편을 최소화할 수 있었습니다.

그리고 로그아웃 시에는 서버에서 Refresh Token을 무효화하고 클라이언트에서는 Access Token을 삭제하는데요, 이를 통해 중간에 Access Token이 탈취되더라도 갱신에 사용할 Refresh Token이 유효하지않기 때문에  탈취된 Access 토큰이 갱신되지 않도록 보장할 수 있습니다!


### 3️⃣ 아쉬웠던 점 & 적용해보고싶은 부분

그러나 현재  Refresh Token이 만료되어도 (⇒ Access Token 갱신은 불가 & 사용은 가능) Access Token은 만료될 때까지 여전히 유효하므로, 탈취된 Access Token이 짧은 시간 동안이지만 여전히 악용될 수 있는 문제가 있었습니다.

그래서 추가로 활용할 수 있는 부분이 JWT Blacklist인데, 이는 로그아웃 시 Access Token도 Blacklist에 추가하여 즉시 차단하는 방법입니다. 이를 통해 탈취된 Access Token이 만료되기 전에 즉시 사용할 수 없게 만들어 보안을 강화하는 방안도 적용해볼까 고민중입니다..💬 
