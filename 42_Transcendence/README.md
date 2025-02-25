# 42_Transcendence 🗓️ (24.12 - 25.02)

팀원

* CHyuni (Django 백엔드 개발, Django REST Framework를 사용한 API 개발, React 기반 프론트엔드 연동 및 Websocket을 이용한 실시간 통신 기능 구현)
* 1107c (Django 백엔드 개발, ELK 스택 기반 로그 분석 시스템 구축 및 모니터링 환경 구축, Websocket을 이용한 실시간 통신 기능 구현)
* joejaeyoung (Solidity 기반 스마트 컨트랙트 개발 및 배포)
* skyshr (React 기반 사용자 인터페이스 개발 및 유지보수)

## 프로젝트 내용
Django 기반 웹 Ping Pong 게임 사이트 개발

* Docker로 환경 독립적인 배포 구현
* REST API 설계 및 개발
* WebSocket으로 실시간 유저상호작용 구현


![홈화면](./image/home.png)
<ul>
    <li>로그인: 42 ID를 이용한 OAuth 2.0 인증 (42 일원 전용). Google 로그인은 테스트용이며, DB 내 ID로 접근.</li>
    <li>인증: 로그인 필수 사용자 프로필 API 제공.
        <ul>
            <li>미인증 시: 401 Unauthorized 반환.</li>
            <li>인증 시: 200 OK 및 사용자 프로필 반환.</li>
        </ul>
    </li>
    <li>로그인 상태 관리: 반환된 프로필 정보를 활용. 미로그인 시 홈 화면에 로그인 페이지 표시.</li>
</ul>

![로그인완료](./image/0.png)
<ul>
    <li>로그인 완료시의 화면.
        <ul>
            <li>로그인 완료 시 서버의 전체 소켓에 연결.</li>
            <li>서버소켓으로 실시간 유저 현황 및 상태 관리.</li>
        </ul>
    </li>
</ul>

![상대방프로필화면](./image/1.png)
<ul>
    <li>상대방 프로필 화면.
        <ul>
            <li>선택한 유저의 레이팅, 승패 및 상태 등을 확인할 수 있는 프로필 화면.</li>
            <li>해당 프로필 화면에서 커스텀 게임 요청 및 친구 추가, 블록, 채팅과 같은 상호작용 가능</li>
            <li>상대방과의 상호작용은 서버 소켓을 통한 실시간성 확립</li>
        </ul>
    </li>
</ul>

![친구추가](./image/2.png)
<ul>
    <li>친구 추가 요청 시 상대방 유저에게 ToastMessage로 알림 후 Pending Users에 응답요청을 생성</li>
        <ul>
            <li>수락 시 해당 유저가 Friends 에 추가</li>
            <li>거절 시 상대방 및 해당 유저 Pending Users 목록에서 요청 제거(따로 알림을 주진 않음)</li>
        </ul>
    </li>
</ul>