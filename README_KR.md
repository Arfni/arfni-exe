# 버전 릴리스

![latest release](https://img.shields.io/github/v/release/Arfni/arfni-exe)

# **1. 설치 방법 (Installation)**

### **1️⃣ 설치 프로그램 실행**

**Arfni 1.0.0 Setup** 아이콘을 더블 클릭하여 설치를 시작합니다.

![화면 캡처 2025-11-11 172645.png](/images/%ED%99%94%EB%A9%B4_%EC%BA%A1%EC%B2%98_2025-11-11_172645.png)

---

### **2️⃣ 환영 화면 (Welcome Screen)**

설치 마법사가 실행되면 **Next** 버튼을 눌러 진행합니다.

설치 시작 전에 실행 중인 다른 프로그램은 모두 종료하는 것을 권장합니다.

![image.png](/images/image.png)

---

### **3️⃣ 라이선스 동의 (License Agreement)**

라이선스 내용을 꼼꼼히 읽어주세요.

약관에 동의한다면 **I Agree**를 선택하고 다음 단계로 진행합니다.

![image.png](/images/image%201.png)

---

### **4️⃣ 설치 위치 선택 (Choose Installation Location)**

Arfni를 설치할 폴더를 선택합니다.

기본 경로를 사용하거나 **Browse** 버튼을 눌러 다른 위치를 선택할 수 있습니다.

설정이 완료되면 **Install** 버튼을 눌러 설치를 시작합니다.

![image.png](/images/image%202.png)

---

### **5️⃣ 설치 완료 (Completing Installation)**

설치가 완료되면 다음과 같은 메시지가 표시됩니다.

**“Arfni 1.0.0 has been installed on your computer.”**

**Finish** 버튼을 눌러 설치 마법사를 종료합니다.

![image.png](/images/image%203.png)

# 2. 주요 기능 (Features)

## (1) 로컬 배포 (Local Deployment)

## 사전 준비사항 (Prerequisites)

로컬 배포를 시작하기 전에, 먼저 PC에 Docker Desktop이 설치되어 있어야 합니다.  
Arfni는 Docker Desktop이 설치되어 있다면 자동으로 실행을 시도합니다.  
만약 자동 실행에 실패할 경우, 사용자가 직접 Docker Desktop을 실행한 뒤 다시 진행해 주세요.

---

### 1️⃣ 새 프로젝트 생성 (Create New Project)

로컬 환경에서 배포를 시작하려면 **Create New Project** 버튼을 클릭하여 새 프로젝트를 생성합니다.

![image.png](/images/image%204.png)

---

### 2️⃣ 프로젝트 이름 및 폴더 설정 (Set Project Name and Folder)

프로젝트 이름과 프로젝트가 생성될 경로를 설정합니다.

![image.png](/images/image%205.png)

![local_3.png](/images/local_3.png)

---

### 3️⃣ 생성된 폴더 확인 (Verify Generated Folder)

지정한 경로에 생성된 폴더를 확인합니다.  
해당 경로에는 배포 및 캔버스 기록을 위해 `.arfni` 폴더와 `stack.yaml` 파일이 자동 생성됩니다.

---

![image.png](/images/image%206.png)

---

### 4️⃣ 배포용 앱 폴더 생성 (Create Apps for Deploy)

루트 경로에 `apps` 폴더를 만들고, 배포할 파일들을 그 안에 배치합니다.  
각 하위 폴더 이름은 캔버스에서 사용하는 블록 이름과 동일해야 합니다.

![image.png](/images/image%207.png)

![local_3.png](/images/local_3%201.png)

---

### 5️⃣ 드래그 앤 드롭 (Drag & Drop)

캔버스 화면으로 돌아가서, 배포하려는 요소들에 맞게 블록들을 드래그 앤 드롭하여 캔버스 위에 배치합니다.

![image.png](/images/image%208.png)

---

### 6️⃣ 속성 변경 (Change Properties)

각 블록을 클릭하여 속성을 설정할 수 있습니다.  
아키텍처에 맞게 포트, 환경 설정, 환경 변수 등을 구성합니다.

![image.png](/images/image%209.png)

![local_6.png](/images/local_6.png)

---

### 7️⃣ Stack.yaml 확인 (Check Stack.yaml)

하단 슬라이드 패널에서 자동으로 업데이트되는 `stack.yaml` 파일을 확인할 수 있습니다.  
변경 사항이 2초 동안 없으면 자동으로 저장됩니다.  
블록 배치와 환경 설정을 마친 후, 배포 전 마지막으로 `stack.yaml` 파일을 검토해 주세요.

![image.png](/images/image%2010.png)

---

### 8️⃣ 배포 실행 (Deploy)

우측 상단의 **Deploy** 버튼을 클릭하여 배포를 시작합니다.

![local_8_1.png](/images/local_8_1.png)

![image.png](/images/image%2011.png)

---

### 9️⃣ 배포 프로세스 (Deployment Process)

### 배포 단계 (Deployment Stages)

Deploy 버튼을 클릭하면 다음의 5단계를 거쳐 자동 배포가 진행됩니다.

1. **Preflight** - 배포 전 사전 점검
2. **Generate** - 설정 파일 생성
3. **Build** - 컨테이너 이미지 빌드
4. **Deploy** - 컨테이너 배포
5. **Health** - 헬스 체크 검증

> Tip: 배포 도중 언제든지 **Stop Deployment** 버튼을 눌러 배포를 중단할 수 있습니다.

![image.png](/images/image%2012.png)

### 자동 파일 생성 (Automatic File Generation)

`Dockerfile`, `docker-compose.yml` 등 필수 파일이 없는 경우, Arfni가 자동으로 생성해 줍니다.  
다만, **안정적인 배포를 위해 가급적 사전에 직접 설정 파일을 준비하는 것을 권장**합니다.

### 배포 최적화 (Deployment Optimization)

이미 존재하는 이미지 및 배포 환경이 있다면 최대한 재사용하며,  
변경 사항이나 새로운 요구사항이 있을 경우에만 필요한 부분만 다시 빌드 및 설치를 진행합니다.

![local_9_2.png](/images/local_9_2.png)

### 배포 완료 (Deployment Completion)

배포가 완료되면 팝업 창을 통해 다음 정보를 확인할 수 있습니다.

- 어떤 서비스들이 배포되었는지
- 제공되는 엔드포인트는 무엇인지

![local_9_3.png](/images/local_9_3.png)

## 참고사항 (Notes)

- Arfni는 Docker를 기반으로 배포를 수행하므로,  
  **로컬 환경에 Docker Desktop이 반드시 설치되어 있어야 합니다.**
- Docker Desktop이 설치되어 있다면, 시스템이 자동으로 실행을 시도합니다.
- 자동 실행에 실패할 경우, 직접 Docker Desktop을 실행하면  
  실행 이후 배포는 자동으로 진행됩니다.

![image.png](/images/image%2013.png)

---

## (2) 원격 배포 (Remote Deployment)

## 사전 준비사항 (Prerequisites)

원격 배포를 시작하기 전에 아래 조건들을 준비해야 합니다.

- 배포 대상 원격 서버에 대한 SSH 접속 권한
- 서버 인증을 위한 PEM 키 파일
- 하이브리드 모니터링 모드를 사용할 경우: 로컬 PC에 Docker Desktop 설치

---

### 1️⃣ 서버 설정 (Server Configuration)

**Remote Projects** 화면에서 **Select Server**를 클릭하여  
배포 대상 서버를 선택합니다.

![image.png](/images/image%2014.png)

---

### 1) 새 서버 추가 (Adding a New Server)

아직 등록된 서버가 없다면, 먼저 서버를 추가해야 합니다.  
**Add New Server** 버튼을 클릭해 배포 대상 서버를 서버 목록에 등록합니다.

![image.png](/images/image%2015.png)

다음 항목들을 설정합니다.

- **Server Name** - 서버를 식별하기 위한 이름
- **Server Address** - 서버의 IP 주소 또는 도메인
- **Username** - SSH 접속용 사용자 이름
- **PEM Key Path** - SSH 키 파일 경로

![스크린샷 2025-11-12 133252.png](/images/%EC%8A%A4%ED%81%AC%EB%A6%B0%EC%83%B7_2025-11-12_133252.png)

설정을 완료한 후:

1. **Test SSH Connection** 버튼을 눌러 연결이 정상적인지 확인합니다.
2. **Add Server** 버튼을 눌러 서버 정보를 저장합니다.

![스크린샷 2025-11-12 133636.png](/images/%EC%8A%A4%ED%81%AC%EB%A6%B0%EC%83%B7_2025-11-12_133636.png)

**서버 관리 (Managing Servers)**

저장된 서버를 클릭하면 해당 서버에서 프로젝트를 관리할 수 있습니다.  
서버 선택 후 **Create New Project**를 통해 프로젝트 생성을 진행합니다.

![스크린샷 2025-11-12 130505.png](/images/%EC%8A%A4%ED%81%AC%EB%A6%B0%EC%83%B7_2025-11-12_130505.png)

---

### 2️⃣ 새 프로젝트 생성 (Create New Project)

**Create New Project** 버튼을 클릭한 뒤,  
원격 서버에서 프로젝트가 생성될 경로와 프로젝트 이름을 설정합니다.

![remote_2_2_create.png](/images/remote_2_2_create.png)

![image.png](/images/image%2016.png)

---

### 3️⃣ 생성된 폴더 확인 (Verify Generated Folder)

지정한 경로에 생성된 폴더를 확인합니다.  
`.arfni` 폴더와 `stack.yaml` 파일이 자동으로 생성되어,  
배포 및 캔버스 기록에 사용됩니다.

![remote_3.png](/images/remote_3.png)

---

### 4️⃣ 배포용 앱 폴더 생성 (Create Apps for Deploy)

`apps` 폴더를 만들고, 배포할 파일들을 그 안에 배치합니다.  
각 폴더 이름은 캔버스에서 사용하는 블록 이름과 일치해야 합니다.

![local_4.png](/images/local_4.png)

![remote_4_2.png](/images/remote_4_2.png)

---

예를 들어, **FastAPI**의 경우 `requirements.txt` 파일이 필요하다면  
아래와 같이 필수 의존성을 포함해야 합니다.

이 파일은 **fastapi** 폴더 안에 위치해야 합니다.

```txt
fastapi==0.104.1
uvicorn[standard]==0.24.0
gunicorn
