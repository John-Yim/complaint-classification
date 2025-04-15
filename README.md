# 🏛️ 민원 텍스트 분류 및 정부 부처 안내 시스템

본 프로젝트는 한국어 민원 텍스트를 입력받아  
총 **18개 카테고리 중 하나로 자동 분류**하는 모델을 개발한 실험 노트북 입니다.

최종적으로 SKT의 KoBERT 모델을 활용해 높은 정확도와 신뢰도 있는 분류 결과를 도출하였으며,  
Hugging Face Spaces를 통해 민원 텍스트를 분류하고 정부 부처 정보를 제공하는 실시간 데모 서비스도 제공 중입니다.

---

## 📁 주요 파일
- **출처**: AIHub의 [민원 업무 자동화 인공지능 언어 데이터](https://www.aihub.or.kr/aihubdata/data/view.do?currMenu=115&topMenu=100&dataSetSn=619) 사용
  
| 파일명 | 설명 |
|--------|------|
| `complaint_classification.ipynb` | 전체 실험 흐름 및 시각화 포함 |
| `complaint_classification.html` | 정적 HTML 버전 (다운로드 후 열람 추천) |
> 📝 학습된 모델 파일은 포함되어 있지 않으며,
> 본 노트북을 실행하면 동일한 모델 구조와 성능을 재현할 수 있습니다.

---

## 🧪 실험 구성 요약

- 텍스트 전처리 및 중복 제거 (text 기준, 최빈 category 유지)
- TF-IDF + LightGBM → Baseline 모델 성능 확보
- KoBERT, RoBERTa, KcELECTRA 모델 비교 실험
- 최종적으로 **KoBERT 모델 선정 및 fine-tuning 적용**

---

## 📊 최종 성능 요약 (KoBERT 기준)

- Accuracy: **93.8%**
- Macro F1-score: **92%**
- Weighted F1-score: **94%**
- 다수/소수 클래스 모두 안정적인 분류 성능 확보

---

## 🔗 데이터셋 정보

- 수집/가공: 공공 민원 텍스트 (구체적 출처 비공개)
- 클래스: 총 18종 (교통, 복지, 보건소, 자동차, 환경미화 등)
- 개인정보 필터링 후 중앙정부 기준으로 통합

---

## 🚀 데모 체험

- Hugging Face Demo (실시간 민원 분류 + 부처 정보 제공)  
  👉 [민원 텍스트 분류 및 정부 부처 정보 추천 시스템](https://huggingface.co/spaces/JohnYim0213/project-note)
