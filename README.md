## flutter_bricks 🧱

Flutter 프로젝트에서 CI / CD 설정을 빠르고 일관되게 생성하기 위한
Mason Brick 모음 레포지토리입니다.

PR CI, main merge CI, Fastlane 연동 등
실무에서 바로 쓰는 수준의 Flutter CI 템플릿을 목표로 합니다.

---

#### 🧱 Bricks List   

|Brick|Description|
|------|------|
|pr_ci|PR 생성 시 실행되는 Flutter CI (analyze + test)|

#### 🚧 추가 예정

- main merge CI
- Android / iOS 분리 빌드
- Fastlane 연동 CD
- 필수 설치 라이브러리 및 아키텍처 구조 생성


#### 📦 Requirements

- Flutter SDK
- Dart SDK
- Mason CLI
  - Mason CLI 설치 : `dart pub global activate mason_cli`
- 위의 사항 환경 변수 등록
- 설치 확인: `mason --version`

#### 🚀 How to Use (Flutter 프로젝트에서)
##### 1️⃣ Mason 초기화

Flutter 프로젝트 루트에서:
`mason init`


→ mason.yaml 생성됨

##### 2️⃣ Brick 등록
`mason add pr_ci --git-url https://github.com/Gunbam27/flutter_bricks.git --git-path pr_ci`   
→ 추가시 mason.yaml 자동으로 수정 됨


##### 3️⃣ CI 생성
`mason make pr_ci`


결과:

.github/   
└─ workflows/   
   └─ pr_ci.yml

##### 4️⃣ CI 실행 테스트

PR 생성 → GitHub Actions 실행

또는:

git push origin <branch>

---

#### 🧪 Brick 단독 테스트 방법

Brick 개발 중에는 실제 Flutter 프로젝트 없이도 테스트 가능합니다.

cd flutter_bricks
mason make pr_ci --output-dir test_output


결과:

test_output/   
└─ .github/   
└─ workflows/   
└─ pr_ci.yml

#### 🛠 Tech Stack

Dart & Flutter

GitHub Actions

Mason CLI(Template Engine)


#### 📄 License

MIT
