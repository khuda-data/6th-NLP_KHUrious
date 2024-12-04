# ❓ **KHUrious**  
**경희대학교 외국인 전용 ChatBot 서비스**  

---

## 📌 **1. 프로젝트 소개**  
**KHUrious**는 경희대학교 외국인 재학생을 위한 통합 정보 제공 Chatbot 서비스입니다.  
경희대학교 관련 학사 정보, 학교 행사, 동아리 활동 등 외국인 학생들이 쉽게 접근하기 어려운 정보를 효율적으로 제공함으로써, 정보 비대칭 문제를 해결하고자 개발되었습니다.

---

## 📊 **2. 국내 주요 Chatbot 도입 사례 및 성과**  


![5](https://github.com/user-attachments/assets/0b5a88c2-7d65-4fe3-a2cc-b512895f17b5)

국내 주요 챗봇 도입 사례를 살펴보면 다음과 같은 성과를 확인할 수 있습니다:  
- **비용 절감:** 반복적이고 단순한 행정 업무를 자동화하여 운영 비용 절감  
- **업무 효율성 향상:** 실시간 정보 제공을 통해 업무 처리 시간 단축  
- **접근성 강화:** 다양한 플랫폼을 통해 사용자 접근성 향상  
- **조직 이미지 제고:** 혁신적 서비스 제공으로 조직의 긍정적 이미지를 강화  

이를 바탕으로 **KHUrious**는 경희대학교 외국인 학생들을 대상으로 정보를 통합적으로 제공하고, 행정 업무 효율성을 높이는 데 기여할 수 있습니다.  

---

## 🌍 **3. 외국 유학생 전용 Chatbot의 필요성**  

![6](https://github.com/user-attachments/assets/38e8888f-5be7-4dce-8475-dbe2da66b916)


### 📈 **외국인 학생 규모**  
- 2023년 기준, 경희대학교는 국내 대학 중 외국인 유학생 수 2위 (4,636명)를 기록했습니다.  


### 🔍 **정보 접근성 문제와 비대칭성**  
- 경희대학교에는 182개의 다양한 홈페이지가 존재하며, 외국인 학생들은 필요한 정보를 찾는 데 어려움을 겪고 있습니다.  
- 대부분의 웹사이트와 정보가 **국문 중심**으로 구성되어 있어, 외국인 학생들에게 언어적·문화적 장벽으로 작용합니다.  
- 교내 **내국인 중심 네트워크 및 정보 전달 시스템**에 접근하는 데 한계가 있어, 외국인 학생들은 필요한 정보를 제때 얻지 못하고 중요한 기회를 놓치는 경우가 발생합니다.  
- 이러한 이유로 **외국인 학생과 한국인 학생 간의 정보 비대칭성**이 심화되고 있으며, 학사 행정, 학교 행사, 동아리 활동 등의 기회에서 격차가 발생합니다.  

---
### 🛠 **KHUrious의 해결 방안**  
**KHUrious**는 대규모 언어 모델(LLM)을 활용하여 학생들이 하나의 플랫폼에서 쉽고 간편하게 정보를 검색할 수 있도록 설계되었습니다.  
- **통합 플랫폼 제공:** 학사 정보, 동아리 활동, 학교 행사 등을 통합적으로 검색 가능  
- **정보 격차 해소:** 외국인 학생과 한국인 학생 간의 정보 접근성 차이 완화  

---

## 🔄 **4. 데이터 수집과 전처리 파이프라인**  

![SW_Festival_KHUrious_8](https://github.com/user-attachments/assets/96b21dc8-fc96-4f20-b11b-62e8c330cd3f)

### 🌐 **경희대학교 웹사이트 데이터 수집 프로세스**  
1. **Base URL 확보**  
   - 경희대학교 공식 웹사이트(https://www.khu.ac.kr)를 기준으로 웹 스크래핑을 수행하여, 트리 형태로 뻗어 있는 URL을 추출합니다.

2. **추출한 URL 파싱**  
   - 수집한 URL을 다시 스크래핑하여 HTML 원본 소스를 확보하고 세부 정보를 분석합니다.

3. **규칙성 파악**  
   - HTML에서 필요한 정보를 추출하기 위해 특정 규칙(id="cont", class="sub_page" 등)을 기반으로 데이터를 수집합니다.

4. **텍스트 저장**  
   - 수집한 데이터를 영어 번역 및 JSON 형식으로 저장하여 효율적인 관리가 가능하도록 했습니다.

---

### 📱 **경희대학교 인스타그램 데이터 수집 프로세스**  
1. **인스타그램 ID 조사**  
   - 경희대학교와 관련된 여러 계정을 조사하고 주요 정보를 제공하는 계정을 선별합니다.  

2. **게시물과 캡션 추출**  
   - Instagram API를 활용해 주요 계정의 게시물과 캡션을 수집합니다.

3. **텍스트 요약**  
   - OCR 기술과 T5 모델을 활용해 이미지 속 텍스트를 추출 및 요약합니다.  

4. **비정형 데이터 OCR**  
   - 이미지 기반 비정형 데이터를 텍스트로 변환하여 분석 가능하도록 정리합니다.  

---

### 💾 **결과물**  
- 모든 데이터는 JSON 형식으로 저장되며, 메타 정보와 함께 정리됩니다.  
- 예: 커리큘럼 정보, 학사 일정, 학생회 공지 등이 경희대 질문에 최적화된 답변 제공에 활용됩니다.

---

##  🧠 **모델링**


### 🔄 **Continual Pretraining (CPT)**  

![SW_Festival_KHUrious_13](https://github.com/user-attachments/assets/8e02bb9f-9a5e-4741-ab0c-e2f1854e87e7)

Continual Pretraining은 경희대학교의 도메인 지식을 학습하기 위해 다양한 데이터를 수집하고 이를 최적화된 방식으로 학습시키는 과정입니다. 이를 통해 경희대학교 특화 챗봇이 사용자 질문에 보다 정확하고 맥락에 맞는 답변을 제공할 수 있도록 설계되었습니다.  

수집된 데이터를 기반으로 지속적 학습(Continual Learning)을 수행하여, 경희대학교와 관련된 도메인 지식을 모델에 주입합니다.  

---

### 🚀 **최적화 및 모델 적용** 
CPT를 효과적으로 수행하기 위해 다음과 같은 최적화 기술을 적용했습니다:  
1. **Unsloth 모델 사용**  
   - 경량화된 모델을 활용해 학습 속도를 높이고 효율성을 극대화합니다.  

2. **LoRA(Low-Rank Adaptation) 적용**  
   - 대규모 언어 모델의 효율적 학습을 위해 LoRA 기법을 도입하여 적은 자원으로도 고성능을 유지합니다.

3. **4-Bit Quantization**  
   - 모델 메모리 사용량을 줄이고 연산 효율성을 높이기 위해 4비트 양자화를 적용합니다.

4. **하이퍼파라미터 설정**  
   - 최적 성능을 위해 다음과 같은 하이퍼파라미터를 조정했습니다:  
     - Learning Rate  
     - Epoch  
     - Max Sequence Length  
     - Batch Size  
     - Embedding Learning Rate  

---

### 🛠️**Supervised Fine-Tuning (SFT)**  

![SW_Festival_KHUrious_19](https://github.com/user-attachments/assets/a93faa89-76a4-4691-8edc-7218ac31792f)

Supervised Fine-Tuning(SFT)은 Continual Pretraining(CPT)을 통해 학습된 모델에 구체적인 질문-답변 데이터를 학습시켜, 챗봇의 답변 정확성을 높이는 과정입니다.  

SFT를 통해 경희대학교 관련 질문에 대해 적합하고 세부적인 답변을 제공할 수 있도록 모델을 미세 조정합니다.

---

1. **QA 데이터 구축**  
   - 경희대학교와 관련된 질문 및 답변 데이터셋을 구축하고, 데이터는 모델이 이해할 수 있도록 특정 구조(JSON 형식 등)로 정리됩니다.  
   - **예시:**  
     - 질문: "When can students apply for a double major or minor?"  
     - 답변: "Students can apply for a double major or minor from **September 23 to September 27, 2024**. This application period coincides with the course withdrawal period, allowing students the flexibility to adjust their academic plans."

2. **지도 학습 방식으로 모델 학습**  
   - 구축된 QA 데이터를 활용해 모델을 미세 조정하여 경희대학교 관련 질문에 대한 맥락을 학습합니다.

3. 🚀 **최적화 기술 적용**  
   - **Unsloth 모델:** 경량화된 모델을 활용하여 학습 속도와 효율성을 극대화합니다.  
   - **LoRA(Low-Rank Adaptation):** 기존 LLM에 추가 학습이 가능하도록 LoRA 기법을 적용합니다.  
   - **4-Bit Quantization:** 모델 크기를 줄이고 성능을 유지하며 자원 소비를 최소화합니다.  
   - **하이퍼파라미터 조정:**  
     - Learning Rate  
     - Epoch 
     - Max Sequence Length  
     - Batch Size  

---

### **CPT와 SFT의 차이점**  

1. **목적**  
   - **CPT (Continual Pretraining):**  
     - 새로운 데이터와 도메인 지식을 모델에 주입하고, 기존 지식과의 균형을 유지하며 학습을 지속하는 과정.  
     - 경희대의 방대한 데이터를 일반적인 도메인 학습 모델로 통합하는 데 초점을 맞춤.  
   - **SFT (Supervised Fine-Tuning):**  
     - 모델이 특정 질문-답변 패턴에 최적화되도록 세부적으로 조정하는 과정.  
     - 경희대와 관련된 질문에 더 정확하고 구체적인 답변을 제공하는 데 초점.

2. **학습 데이터**  
   - **CPT:**  
     - 크롤링한 학과 정보, 인스타그램 데이터, PDF 문서 등 비구조적 데이터.  
   - **SFT:**  
     - 질문-답변 형태의 구조화된 데이터.

3. **학습 방식**  
   - **CPT:**  
     - 지속적인 학습(Continual Learning)을 통해 도메인 적합성을 강화.  
   - **SFT:**  
     - 지도 학습(Supervised Learning)을 통해 특정 작업(QA)에 최적화.

4. **결과물**  
   - **CPT:**  
     - 경희대 특화 지식이 반영된 언어 모델.  
   - **SFT:**  
     - 질문에 대한 높은 정밀도와 적합성을 가진 QA 시스템.

--- 
**KHUrious**는 외국인 학생들이 경희대학교에서 편리하고 효율적으로 학업 및 캠퍼스 생활을 누릴 수 있도록 돕는 혁신적인 서비스입니다.  
**경희대학교의 Curious한 정보를 KHUrious가 모두 알려드립니다!**

## 🌈 **팀원**  

| <img src="https://avatars.githubusercontent.com/u/175034551?v=4" width="100"/> | <img src="https://avatars.githubusercontent.com/u/176892182?v=4" width="100"/> | <img src="https://avatars.githubusercontent.com/u/143325502?v=4" width="100"/> | <img src="https://avatars.githubusercontent.com/u/151055302?v=4" width="100"/> |  
|:---:|:---:|:---:|:---:|  
| [권도현](https://github.com/riverblue72) | [박찬희](https://github.com/chanyi24) | [오윤진](https://github.com/koyojin) | [이상엽](https://github.com/KHUSangYub) |  

---

