# llama.cpp Local LLM Experiment

## Overview

`llama.cpp`를 활용해 로컬 환경에서 LLM을 실행하고, 실행 옵션과 모델 설정에 따른 동작 및 성능 차이를 실험하고 기록하는 프로젝트다.

앞서 [WebRTC Conference Practice](https://github.com/Sangseon/ts-0001-ai-webrtc-practice)에서 Codex를 활용해 TypeScript 기반 SFU 화상회의를 단계별로 구현했다. 이를 계기로 동일한 요구사항을 로컬 LLM으로도 구현할 수 있을지 확인하고자 한다.

본 프로젝트에서는 비교 개발에 앞서 로컬 LLM 실행 환경을 직접 구축하고, 모델별 실행 성능과 하드웨어 자원 사용량을 확인한다. 이후 별도 프로젝트에서 동일한 요구사항을 독립적으로 구현하고, Codex와 로컬 LLM의 개발 과정 및 결과를 비교할 계획이다.

## Experiment Scope

- 로컬 LLM 실행 환경 구축
- 모델 다운로드 및 실행
- `llama.cpp` 실행 옵션별 동작 확인
- 모델별 실행 성능과 리소스 사용량 측정
- 실행 결과 및 실험 내용 기록

## Environment

### Hardware

| Component | Specification              |
| --------- | -------------------------- |
| CPU       | 8C / 16T                   |
| RAM       | DDR5 32GB                  |
| GPU       | NVIDIA GeForce RTX 5070 Ti |
| VRAM      | 16GB GDDR7                 |
| OS        | Windows 11                 |
| Storage   | NVMe SSD                   |

### Models

실험에 사용할 모델 목록이다.

| Model                  | Model Type | Parameter Size | Quantization | Model File Size |
| ---------------------- | ---------- | -------------: | ------------ | --------------: |
| Gemma-4-12B-it-Q8_0    | Main       |            12B | Q8_0         |         12.86GB |
| Qwen3.8-27B-UD-IQ3_XXS | Main       |            27B | IQ3_XXS      |         11.86GB |
| Qwen3.8-27B-UD-IQ3_S   | Main       |            27B | IQ3_S        |         12.97GB |
| Qwen3.8-27B-UD-Q3_K_XL | Main       |            27B | Q3_K_XL      |         14.07GB |
| Qwen3.8-27B-Q4_K_M     | Main       |            27B | Q4_K_M       |         17.74GB |
| mtp-Qwen3.8-27B-Q4_0   | MTP        |            TBD | Q4_0         |          2.30GB |

**Format:** GGUF

### Benchmark

모델별 실행 성능과 리소스 사용량을 측정하고 기록한다.

| Model | Prompt Tokens | Generated Tokens | Prompt Processing (tok/s) | Generation Speed (tok/s) | Generation Time | Peak VRAM |
| ----- | ------------: | ---------------: | ------------------------: | -----------------------: | --------------: | --------: |
| TBD   |           TBD |              TBD |                       TBD |                      TBD |             TBD |       TBD |

## Notes

실험 환경과 모델 정보는 실제 구성 이후 업데이트한다.
