MAC OS 기준으로 작성

cmake 설치
brew install cmake

llama.cpp 빌드

  실리콘 맥 전용 최적화 cmake (단 실행한 실리콘맥에 맞게 최적화진행되어서 코드 이식성 하락함.)
  cmake -B build -S . -DLLAMA_METAL=ON -DLLAMA_BUILD_SERVER=ON -DLLAMA_NATIVE=ON

  그외
  cmake -B build -S . -DLLAMA_METAL=ON -DLLAMA_BUILD_SERVER=ON

  cmake --build build -j

====
sample_test_1 에서 진행한 모델: Meta-Llama-3-8B-Instruct
sample_test_2 에서 진행할 모델: Qwen2.5-7B-Instruct

모델은 허깅페이스(https://huggingface.co/)에서 다운로드를 진행한다.

./build/bin/llama-server \
  -m models/qwen2.5-7b-instruct-q4_k_m-00001-of-00002.gguf
