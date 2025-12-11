## Common Instructions (작성 중)
- 사용자와 대화 시에는 한국어를 사용한다. 단, 코드, 주석은 영어로 작성한다.
- README.md 등 Markdown 문서 작성 시, 언어는 사용자가 지정한 언어로 작성하나, 이미 작성된 내용이 있다면 해당 언어를 따른다.
- 사용자가 명시적으로 요청 시에는 해당 언어를 사용한다.
(다듬기 필요) - 파일을 수정할 때에는 전체 삭제 후 새 버전을 넣는 것이 아닌, 부분 삭제 후 교체 방식을 사용한다.
- Tab size는 각 언어 별 설정을 따른다.
- 패키지 설치 시 특정 버전이 필요한 경우 사용자가 명시적으로 요청하지 않는 한 최신 안정 버전을 사용한다.
- 코드는 가능한 한 최신 문법과 기능을 사용한다.
- 하나의 파일에 모든 코드를 작성하지 않는다. 적절히 파일 및 디렉토리 분리를 수행한다.

## Language-Specific Instructions

### Typescript / Yarn
- 패키지 매니저는 Yarn을 사용한다.
- package.json을 직접 수정하는 것을 엄격히 금지하며, yarn add/remove 명령어를 통한 패키지 설치/제거만 허용된다.
- 단, 실행 script 추가, name, version, author 설정 등 민감하지 않은 작업에 대해서는 직접 수정이 허용된다.
- 코드 실행은 yarn <script> 형태로 한다.
- Tab size는 4로 설정한다.

### Python / UV
- 패키지 매니저로 uv를 사용한다.
- pip 명령어를 사용하거나, 직접 requirements.py나 pyproject.toml을 직접 수정하지 않는다.
- uv add, remove 등 명령어를 사용하여 패키지를 추가/제거하라.
- 코드 실행은 uv run으로 해라.
- Tab size는 4로 설정한다.

### Terraform (작성 중)
- Tab size는 2로 설정한다.

## Framework-Specific Instructions

### React / Next (작성 중)
- css는 vanilla-extract를 사용한다.
- Tailwind css를 사용하지 않는다.

### NestJS (작성 중)
- DBMS는 <>를 사용하며, ORM은 Sequelize를 사용한다.
- 캐시는 Redis를 사용한다.
- 서버 프레임워크는 Nestjs + Typescript를 사용한다.

### FastAPI  (작성 중)

### AWS CloudFormation (작성 중)

## Part-Specific Instructions

### Frontend part (작성 중)

### Backend part (작성 중)
- 코드 중복을 최소화하여 개발한다.
- 확장성, 유지보수성, 테스트 가능성을 고려하여 설계한다.
- 모듈화된 구조를 사용한다.

### Cloud part (작성 중)