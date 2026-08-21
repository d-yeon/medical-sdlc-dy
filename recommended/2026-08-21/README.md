# Daily Paper Recommendations — 2026-08-21

## 검색 개요
- **연구 기준일**: 2026-08-21 (REQUESTED_DATE로 지정됨)
- **실제 검색창**: 처음 2026-08-21 하루, 이후 7일(2026-08-14~2026-08-20), 최종 30일(2026-07-22~2026-08-20) 창까지 확대해 검색. 하루/7일 창에서는 결과가 없어 30일 창에서 관련 논문을 찾음.
- **검색 쿼리**: `chest X-ray deep learning multi-institutional`

## 코호트 개요 (기관 단위 집계만, 환자 단위 값 없음)
- 총 272건의 흉부 X선 판독 레코드, 5개 기관(INST01–05)에서 48~62건씩 고르게 분포.
- 성별: 남 136 / 여 136, 연령대는 9~87세, 평균 남 48.7세 / 여 54.3세.
- 촬영 자세: PA 184건, AP 88건.
- 진료 유형: 외래 84, 입원 74, 원격진료 62, 응급 52.
- 소견 라벨(findings_label): No Finding 145건이 최다, 이어서 Infiltration 21, Atelectasis 16, Nodule 7, Fibrosis 6, Effusion 6, Cardiomegaly 5, Pneumothorax 5 등 다수의 저빈도·복합 소견이 존재 (예: Effusion|Infiltration 5, Atelectasis|Infiltration 4).
- 모든 레코드는 합성(is_synthetic=true) 데이터.

## 선정된 논문 3편

### 1. CLEAR: an auditable foundation model for radiology grounded in clinical concepts
(Nature Biomedical Engineering, 2026-07-22)
- **관련성**: 미국·유럽·아시아 4개 외부 코호트로 검증된 개념 기반 흉부 X선 파운데이션 모델로, 우리 코호트처럼 다기관·소견 불균형 데이터에서 모델 신뢰성을 점검하는 프레임워크로 참고 가능.
- **한계**: 우리 데이터(272건)는 CLEAR 학습·검증 규모(수십만 건)에 비해 매우 작아 직접적인 재현 검증은 불가능.
- 링크: https://doi.org/10.1038/s41551-026-01741-4

### 2. Grounding Radiology Report Findings into Medical Image Segmentation (CF2Seg)
(npj Digital Medicine, 2026-07-28)
- **관련성**: 판독문 텍스트만으로 병변 위치를 분할하는 기법으로, 우리 데이터의 report_text/clinical_info 필드와 복합 소견 구조(Effusion|Infiltration 등)에 적용 가능성이 있음.
- **한계**: 픽셀 단위 전문가 주석이 없어 분할 정확도 자체는 우리 데이터로 검증 불가.
- 링크: https://doi.org/10.1038/s41746-026-03051-0

### 3. Multicenter evaluation of four large language models for automated spine imaging diagnosis
(npj Digital Medicine, 2026-08-08)
- **관련성**: 3개 기관 20,277건 판독문 기반 LLM 비교 연구로, 저빈도 질환에서 정밀도가 크게 저하되는 롱테일 문제를 지적. 우리 코호트의 저빈도 소견(Nodule, Fibrosis, Pneumothorax 등) 분포와 구조적으로 유사.
- **한계**: 척추 영상 대상 연구로 흉부 X선인 우리 데이터와 신체 부위·병리가 다름.
- 링크: https://doi.org/10.1038/s41746-026-03133-z

## 검토 축 (axes)
- **기관 간 일반화**: 여러 기관에서 수집된 데이터에 대한 모델 성능 안정성.
- **레이블 롱테일/희귀 소견**: 저빈도 소견에서의 성능 저하 문제.
- **판독문-영상 연계 활용**: 자유기술 판독문을 영상 분석에 활용하는 방법.

## 주의사항
본 추천은 자동 검색 및 코호트 수준 집계에 기반한 것으로, 실제 임상 적용 여부는 반드시 담당 의사의 검토를 거쳐야 합니다.
