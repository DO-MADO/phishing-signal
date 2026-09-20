# 출처 및 라이선스

이 공개 저장소는 피싱 신호등의 제품 설명과 검증 결과를 소개합니다. 문서와 시각화는 출품자가 새로 작성한 해설이며, 수치는 기존 배포 기록의 집계를 재구성했습니다. 연구 데이터·평가 원문·학습 체크포인트·ONNX 바이너리는 이 저장소에 포함하지 않습니다.

## 기반 모델과 변경 사항

| 항목 | 출처 |
|---|---|
| 기반 모델 | [KLUE RoBERTa base](https://huggingface.co/klue/roberta-base/tree/02f94ba5e3fcb7e2a58a390b8639b0fac974a8da) |
| 원저작자 | KLUE 프로젝트, Sungjoon Park 외 |
| 연구 | [KLUE: Korean Language Understanding Evaluation](https://arxiv.org/abs/2105.09680) |
| 원본 revision | `02f94ba5e3fcb7e2a58a390b8639b0fac974a8da` |
| 라이선스 | [Creative Commons Attribution-ShareAlike 4.0 International](https://creativecommons.org/licenses/by-sa/4.0/), [KLUE 공식 고지](https://github.com/KLUE-benchmark/KLUE#license) |

피싱 신호등은 기반 모델을 Dangerous / Safe / Hold 분류에 맞게 추가 학습했습니다. 현재 제품의 `c3_v2 / epoch3` 체크포인트를 ONNX로 변환하고, 가중치를 FP16으로 저장하면서 FP32 연산을 유지합니다. Tokenizer는 기존 KLUE 어휘를 유지한 채 Transformers 5.16.1에서 재직렬화했습니다.

프로젝트의 파생 모델 가중치·ONNX 실행물·Tokenizer에는 **CC BY-SA 4.0**을 적용합니다. 원저작자 귀속, 라이선스 연결, 변경 사실, 적용되는 동일조건 배포 요구를 보존합니다. 이 저장소의 문서에 적용되는 조건이 모델의 라이선스를 대신하지 않습니다. KLUE 원저작자가 이 제품을 보증하거나 추천한다는 뜻도 아닙니다.

현재 실행물 식별값은 [검증 기록](evaluation.md#4-확인한-실행물)에 공개합니다. 이전에 사용한 RoBERTa small 모델의 고지나 이전 모델의 성능을 현재 base 모델의 설명으로 혼용하지 않습니다.

## 브라우저 추론 실행기

- 구성요소: `onnxruntime-web` 1.29.0
- 원저작자·프로젝트: Microsoft 및 [ONNX Runtime 기여자](https://github.com/microsoft/onnxruntime)
- 라이선스: [MIT License · v1.29.0](https://github.com/microsoft/onnxruntime/blob/v1.29.0/LICENSE)
- 사용 방식: WebAssembly backend, 단일 스레드의 브라우저 로컬 추론

ONNX Runtime의 MIT 라이선스와 모델의 CC BY-SA 4.0은 서로 다른 구성요소에 적용됩니다.

## 학습 자료의 출처 관리

출시 기록은 선택된 **3,450행의 미해결 source ID 0건**을 확인하고, 프로젝트 작성 기록과 공공누리 제1유형(KOGL1) 등 출처별 이용 근거를 관리했다고 기록합니다. 상업 학습, 파생 가중치 배포, 저장소 원문 재배포는 각각 구분해 검토했습니다.

이 숫자는 출처 관리 대상의 규모이며, 전체가 학습 분할에 들어갔다는 뜻은 아닙니다. 또한 권리 기록을 갖췄다는 사실을 별도 법률 의견이나 사람에 의한 전체 의미 검수로 표현하지 않습니다. 참고 기관이 서비스의 정확성을 보증하는 것으로 표시하지 않습니다.

이 저장소는 학습·평가 자료의 재배포 권한을 제공하지 않습니다. 공개용 예시는 제품 설명을 위해 별도로 작성한 합성 문구이며, 실제 피해자의 연락이나 평가 원문을 복제하지 않습니다.
