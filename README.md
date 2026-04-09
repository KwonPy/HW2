<div align="center">

# 🏯 수원 데이트 큐레이터

### *전통의 낭만부터 도심의 트렌드까지, 수원의 모든 순간을 잇다*

<img src="docs/banner.png" width="520" alt="수원 데이트 큐레이터 배너" />

<br/>

**AI 기반 맞춤형 수원 데이트 코스 추천 서비스**

[![Python](https://img.shields.io/badge/Python-3.11-3776AB?logo=python&logoColor=white)](https://python.org)
[![FastAPI](https://img.shields.io/badge/FastAPI-0.100+-009688?logo=fastapi&logoColor=white)](https://fastapi.tiangolo.com)
[![Docker](https://img.shields.io/badge/Docker-Containerized-2496ED?logo=docker&logoColor=white)](https://docker.com)
[![CI/CD](https://img.shields.io/badge/CI%2FCD-GitHub_Actions-2088FF?logo=githubactions&logoColor=white)](https://github.com/features/actions)
[![Gemini](https://img.shields.io/badge/Gemini_API-LLM_Powered-8E75B2?logo=google&logoColor=white)](https://ai.google.dev)

</div>

---

## 📌 프로젝트 소개

**수원 데이트 큐레이터**는 사용자의 취향 키워드를 분석하여 수원 지역(행궁동, 광교, 수원역 등)의 핫플레이스를 조합한 **최적의 데이트 코스**를 추천하는 웹 서비스입니다.

> 💡 5단계 설문으로 취향을 파악하고, AI가 맞춤 코스를 큐레이팅합니다!

---

## 🔧 핵심 기능

| 기능 | 설명 |
|:---|:---|
| 🎯 **5단계 키워드 설문** | 지역 → 목적 → 분위기 → 액티비티 → 식음료 순서로 취향 수집 |
| 📊 **TF-IDF 코사인 유사도 매칭** | 사용자 키워드와 DB 장소 태그를 벡터화하여 유사도 기반 랭킹 |
| 🤖 **Gemini LLM 스토리텔링** | 특이사항 입력 시 AI가 스토리텔링형 맞춤 코스 생성 |
| ⚡ **키워드 기반 폴백** | 특이사항 없이도 유사도 Top 3 장소를 카드 형태로 즉시 추천 |
| 🐳 **Docker 컨테이너 배포** | 원커맨드 실행 가능한 컨테이너화 |
| 🔄 **GitHub Actions CI/CD** | Push → 자동 빌드 → Docker Hub → Self-hosted Runner 배포 |

---

## 🏗️ 시스템 아키텍처

```
사용자 (브라우저)
    │
    ▼
┌──────────────────────────────────────┐
│  FastAPI Server (Port 8000)          │
│  ├── /static  → 프론트엔드 (HTML/JS) │
│  └── /api/v1  → 추천 API 엔드포인트  │
│       ├── TF-IDF 코사인 유사도 엔진   │
│       └── Gemini LLM 재랭킹          │
└──────────────┬───────────────────────┘
               │
    ┌──────────┴──────────┐
    │   SQLite Database   │
    │   (장소 메타데이터)   │
    └─────────────────────┘
```

---

## 🛠️ 기술 스택

| 분류 | 기술 |
|:---|:---|
| **Backend** | FastAPI (Python 3.11) |
| **Frontend** | Vanilla HTML/CSS/JS (Glassmorphism UI) |
| **ML Engine** | scikit-learn (TF-IDF + Cosine Similarity) |
| **LLM** | Google Gemini API |
| **Database** | SQLite + SQLAlchemy ORM |
| **DevOps** | Docker, Docker Compose |
| **CI/CD** | GitHub Actions + Self-hosted Runner |

---

## 📂 프로젝트 구조

```
HW2/
├── app/
│   ├── main.py                 # FastAPI 엔트리포인트
│   ├── api/endpoints/          # API 라우터
│   ├── services/               # 추천 엔진 비즈니스 로직
│   └── schemas/                # Pydantic 데이터 모델
├── frontend/
│   ├── index.html              # 메인 UI
│   ├── style.css               # 글래스모피즘 스타일
│   └── app.js                  # 프론트 로직
├── models/                     # SQLAlchemy ORM 모델
├── db/                         # DB 연결 및 시드 데이터
├── Dockerfile                  # 컨테이너 빌드 설정
├── docker-compose.yml          # 멀티 컨테이너 오케스트레이션
└── .github/workflows/main.yml  # CI/CD 파이프라인
```

---

## 📄 License

This project is for educational purposes (경희대학교 오픈소스SW 과제).

<div align="center">


</div>
