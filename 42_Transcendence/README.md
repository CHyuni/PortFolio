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