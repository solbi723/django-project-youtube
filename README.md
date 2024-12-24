# django-youtube-restapi
## (1) Project Settings

- Github

## Model 구조 => ORM
(1) User
- email
- password
- nickname
- is_business

(2) Video
- title
- description
- link
- views_count
- thumbnail
- video_file: link
- User: FK

ex) 파일(이미지, 동영상)
=> 장고에 부하가 걸림.
=> S3 Bucket(저렴, 속도가 빠름) -> 결과물: 링크

(3) Reaction
- User: FK
- Video: FK
- reaction (like, dislike, cancel) => 실제 youtube rest api

(4) Comment
- User: FK
- Video: FK
- content
- like
- dislike

(5) Subscription
- User: FK => subscriber (내가 구독한 사람)
- User: FK => subscribed_to (나를 구독한 사람)

(6) Common
- created_at
- updated_at

## * Docker란?
Docker는 애플리케이션의 배포와 실행을 컨테이너라는 가상화 기술을 통해 쉽게 관리할 수 있도록 하는 오픈 소스 플랫폼입니다.
## * Docker 구성요소
1. Docker Engine
Docker를 구동하는 핵심 소프트웨어로, 다음과 같은 부분으로 구성됩니다:

 - Docker Daemon: 컨테이너 관리 및 실행 담당.
 - Docker CLI (Command Line Interface): Docker 명령어를 실행하는 도구.
 - REST API: Docker와 상호작용하기 위한 인터페이스.
2. Docker Hub
컨테이너 이미지의 저장소로, 이미지 검색, 공유, 배포 가능.

## * Docker Image와 Docker Container
- Docker Image

  - 애플리케이션과 실행에 필요한 모든 것을 포함한 불변의 템플릿.
  - 예: 특정 환경에서 동작하도록 구성된 설치 패키지.

- Docker Container

  - Docker Image를 실행한 실행 가능한 인스턴스.
  - 경량화되어 있으며, OS 수준에서 격리된 독립된 환경 제공.
  - 예: 실행 중인 애플리케이션 프로세스.
