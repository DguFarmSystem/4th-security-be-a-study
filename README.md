# 🔐 BE-A 팀 과제 리포지토리

## 📚 학습 목표

> 기존 프로젝트에서 보안 강화를 위한 노력을 돌아보고,  
> 실제 보안 논문을 기반으로 웹 보안 적용 방안을 탐색합니다.

---

## 🗂️ 아카이브 가이드

📌 레포지토리 주소:  
🔗 [4th-security-be-a-study](https://github.com/DguFarmSystem/4th-security-be-a-study)

### ✅ 제출 방식

1. 본인 이름으로 된 개인 폴더를 생성합니다.  
   예: `김보안/`

2. 해당 폴더 내에 아래와 같은 방식으로 파일 업로드
   - `.md` 파일 (마크다운 작성)
   - `.pdf` 파일 (논문 요약 정리본 등)
   - 개인 블로그 링크 첨부도 가능 (링크만 적어도 OK!)

---

## 🔍 보안 논문 리스트 및 요약

### 1. ⭐️ 멀티모달 비식별화를 통한 개인정보 보안 강화

📄 [Protecting Privacy in Multimodal Large Language Models.pdf](https://github.com/user-attachments/files/19485231/Protecting.Privacy.in.Multimodal.Large.Language.Models.pdf)

#### 🧭 핵심 요약
- **목표**: MLLM에 `unlearning` 기법을 적용하여 프라이버시 보호
- **문제점**: 벤치마크 및 알고리즘 구현의 이론적/기술적 난이도
- **적용 예시**: `KL Minimization` 기반 공개 코드를 활용한 개인정보 보호 강화
- **기대효과**: 개인정보 노출 최소화 + 모델 성능(utility) 유지

---

### 2. 🔍 웹 방화벽 로그 분석을 통한 공격 분류

📄 [웹 방화벽 로그 분석을 통한 공격 분류.pdf](https://github.com/user-attachments/files/19485247/default.pdf)


#### 🧭 핵심 요약
- **목표**: WAF 로그 기반 공격 유형 분류 모델 구축 (AutoML, CNN 등 활용)
- **적용 예시**: 오픈소스 기반 모델 비교 및 로그 전처리 → 공격 유형 자동 분류
- **기대효과**: 웹 공격 유형을 자동 탐지 → 보안 효율 향상

---

### 3. 🔬 사이버공격 융합 동향 분석을 위한 보안 자동화

📄 [사이버공격 융합 동향 분석을 위한 딥러닝 기반 보안 취약점 분석 자동화.pdf](https://github.com/user-attachments/files/19485252/default.pdf)


🔗 [MITRE ATT&CK Framework](https://attack.mitre.org)

#### 🧭 핵심 요약
- **목표**: 보안 문서 기반 NLP 모델로 취약점 분석 자동화 + ATT&CK 연계
- **문제점**: 데이터셋 확보 어려움 / 프레임워크 운용 난이도
- **적용 예시**: 일부 전술/기법 시각화 → 웹 보안에 통합 적용
- **기대효과**: 최신 공격 기법 파악 + 취약점 시각화 → 실시간 대응

---

### 4. 🛡️ 접근 제어 취약점 탐지 및 예방 기법 (난이도 하)

📄 [A Survey of Prevent and Detect Access Control Vulnerabilities.pdf](https://github.com/user-attachments/files/19485258/A.Survey.of.Prevent.and.Detect.Access.Control.Vulnerabilities.pdf)


#### 🧭 핵심 요약
- **목표**: 웹 접근 제어(RBAC 등) 강화 기법 설계
- **문제점**: 예외 케이스 존재, 프레임워크 의존성 높음
- **적용 예시**: OWASP ZAP 등으로 보안 스캐닝 → 취약점 확인 및 보완
- **기대효과**: OWASP Top 10 문제 직접 해결 → 실무 감각 향상

---

## 📅 과제 일정

| 날짜 | 학습 내용 |
|------|-----------|
| **1일차 ~ 4일차** | 기존 프로젝트에서 보안을 위해 구현했던 내용 또는 아쉬웠던 점 정리하여 업로드 |
| **5일차 ~ 6일차** | 위 논문 리스트 중 **1개 이상 선택**하여 요약 및 웹 프로젝트 적용 방안 정리 |
| **7일차 (4월 7일 예정)** | 정리한 내용을 바탕으로 **팀원 간 지식 공유 세션 진행** |

---

## 📥 제출 예시

📁 김보안/day1_my_security_review.md

- `.md`로 깔끔하게 정리
- `.pdf`는 별도 제작 시 첨부
- 블로그로 정리한 경우 링크 파일만 업로드해도 OK!

---

🎓 **실제 보안 논문을 읽고 웹 프로젝트에 적용해보는 실전형 과제입니다.**  
꼼꼼히 읽고 고민해보며, 팀원들과 인사이트도 함께 나눠봐요 💬  
보안은 어렵지만… 함께 하면 재밌어질 거예요! 💪



