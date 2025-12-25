# Megatron-LM Dependencies List

This document lists all dependencies used in the Megatron-LM repository.

## Core Dependencies (pyproject.toml)

### Build System Requirements
- setuptools>=80.0.0 (for pyproject.toml build-system)
- pybind11
- packaging>=24.2

### Main Dependencies
- torch
- numpy
- packaging>=24.2

### Optional Dependencies - MLM
- flask-restful
- sentencepiece
- tiktoken
- wandb
- transformers

### Optional Dependencies - Dev
- nvidia-modelopt[torch] (sys_platform != 'darwin')
- transformer-engine[pytorch,core_cu13]>=2.9.0a0,<2.11.0
- nvidia-resiliency-ext
- tqdm
- einops~=0.8
- tensorstore~=0.1 (!=0.1.46, !=0.1.72)
- nvtx~=0.2
- multi-storage-client~=0.27
- opentelemetry-api~=1.33.1
- mamba-ssm~=2.2
- causal-conv1d~=1.5
- nv-grouped-gemm~=1.1
- megatron-energon[av_decode]~=6.0
- av
- flashinfer-python
- wget
- onnxscript
- fastapi~=0.50
- datasets

### Optional Dependencies - LTS
- tqdm
- einops~=0.8
- tensorstore~=0.1 (!=0.1.46, !=0.1.72)
- nvtx~=0.2
- multi-storage-client~=0.27
- opentelemetry-api~=1.33.1
- mamba-ssm~=2.2
- causal-conv1d~=1.5
- nv-grouped-gemm~=1.1
- megatron-energon[av_decode]~=6.0
- av
- flashinfer-python
- wget
- onnxscript
- fastapi~=0.50
- datasets

## Dependency Groups

### Test Dependencies
- coverage
- nltk
- wrapt
- pytest==8.3.5
- pytest-mock
- pytest-cov
- pytest-random-order
- pytest-asyncio
- pygithub
- pydantic
- tensorboard
- pyyaml
- nemo-run

### Documentation Dependencies
- sphinx
- sphinx-autobuild
- sphinx-autodoc2
- sphinx-copybutton
- myst_parser
- nvidia-sphinx-theme

### Build Dependencies
- setuptools<80.0.0 (for dependency-groups build)
- packaging>=24.2
- hatchling
- pybind11
- Cython>=3.0.0
- torch
- nvidia-mathdx

### Linting Dependencies
- ruff~=0.9.0
- black==24.4.2
- isort==5.13.2
- flake8==7.1.0
- pylint==3.2.6

### CI Dependencies
- python-gitlab
- slack-sdk
- pandas

### No PyPI Wheels (Custom Sources)
- flash_mla (git+https://github.com/deepseek-ai/FlashMLA)
- emerging_optimizers (git+https://github.com/NVIDIA-NeMo/Emerging-Optimizers.git)

## Megatron Core Requirements (megatron/core/requirements.txt)
- torch
- packaging

## Megatron FSDP Dependencies (megatron/core/distributed/fsdp/src/pyproject.toml)
- torch
- einops
- packaging

## ModelOpt Requirements (examples/post_training/modelopt/requirements.txt)
- diskcache
- datasets
- jsonlines
- nvidia-modelopt
- omegaconf
- pulp
- tensorstore (!=0.1.46, !=0.1.72)
- torchprofile
- transformers
- zarr

## ModelOpt SSM Requirements (examples/post_training/modelopt/requirements_ssm.txt)
- mamba-ssm>=2.2.5
- causal-conv1d (git+https://github.com/Dao-AILab/causal-conv1d)

## Docker Image Dependencies

### Multimodal Example (examples/multimodal/Dockerfile)
- einops
- einops-exts
- sentencepiece
- braceexpand
- webdataset
- packaging
- transformers
- datasets
- accelerate
- timm
- pytest-cov
- pytest_mock
- nltk
- wrapt
- zarr
- tensorstore==0.1.45
- black
- isort
- click==8.0.2
- pycocoevalcap
- megatron-energon
- mistral-common
- tiktoken
- CLIP (git+https://github.com/openai/CLIP.git)
- open_clip_torch
- open-flamingo[eval]

### Mamba Example (examples/mamba/Dockerfile)
- triton==2.1.0
- sentencepiece==0.1.99
- flask-restful
- causal-conv1d (git+https://github.com/Dao-AILab/causal-conv1d.git, v1.2.2.post1)
- mamba-ssm (git+https://github.com/state-spaces/mamba.git, v2.0.3)

### ModelOpt Example (examples/post_training/modelopt/Dockerfile)
- jsonlines
- omegaconf
- flask
- flask_restful
- fire
- nltk
- tiktoken
- blobfile
- datasets
- transformers
- triton==3.3.1
- mamba-ssm (git+https://github.com/state-spaces/mamba.git)
- causal-conv1d (git+https://github.com/Dao-AILab/causal-conv1d.git)
- nvidia-modelopt

### Retro Tool (tools/retro/docker/Dockerfile)
- faiss-gpu
- transformers
- google-api-python-client
- sentencepiece
- h5py
- nltk
- einops

### Llama Nemotron VL Example (examples/multimodal/llama_3p1_nemotron_nano_vl_8b_v1/Dockerfile)
- numpy
- einops
- einops-exts
- sentencepiece
- braceexpand
- webdataset
- packaging
- transformers
- datasets
- accelerate
- timm
- pytest-cov
- pytest_mock
- nltk
- wrapt
- black
- isort
- pylint
- mypy
- click
- mistral-common
- tiktoken
- CLIP (git+https://github.com/openai/CLIP.git)
- fairscale
- fire
- blobfile
- mmf
- open_clip_torch
- open-flamingo[eval]
- zarr
- tensorstore==0.1.45
- megatron-energon[av_decode] (git+https://github.com/NVIDIA/Megatron-Energon.git)
- causal-conv1d (git+https://github.com/Dao-AILab/causal-conv1d.git)
- mamba-ssm (git+https://github.com/state-spaces/mamba.git)

## Pre-commit Hooks (.pre-commit-config.yaml)
- black (24.4.2)
- pylint (v3.2.6)
- isort (5.13.2)

## UV Tool Sources
- flash_mla: git+https://github.com/deepseek-ai/FlashMLA (rev: 9edee0c022cd0938148a18e334203b0aab43aa19)
- transformer-engine: git+https://github.com/NVIDIA/TransformerEngine.git (rev: release_v2.10)
- nemo-run: git+https://github.com/NVIDIA-NeMo/Run.git (rev: 01a9a8ba360f7b2908728ad0516e0ad9d936966d)
- emerging_optimizers: git+https://github.com/NVIDIA-NeMo/Emerging-Optimizers.git (rev: fb1add873e7851ec34b48581ea1b15761b73d189)

## Additional CI/Docker Dependencies
- nvidia-nvshmem-cu13
- DeepEP (git+https://github.com/deepseek-ai/DeepEP.git, branch: hybrid-ep)
- jet-api
- jet-client~=3.0
- one-logger

---

## Complete Alphabetical Dependency List

Below is a deduplicated alphabetical list of all unique dependencies:

1. accelerate
2. av
3. black
4. blobfile
5. braceexpand
6. causal-conv1d
7. click
8. CLIP
9. coverage
10. Cython
11. datasets
12. DeepEP
13. diskcache
14. einops
15. einops-exts
16. emerging_optimizers
17. faiss-gpu
18. fairscale
19. fastapi
20. fire
21. flake8
22. flash_mla
23. flashinfer-python
24. flask
25. flask-restful
26. google-api-python-client
27. h5py
28. hatchling
29. isort
30. jet-api
31. jet-client
32. jsonlines
33. mamba-ssm
34. megatron-energon
35. mistral-common
36. mmf
37. multi-storage-client
38. mypy
39. myst_parser
40. nemo-run
41. nltk
42. numpy
43. nv-grouped-gemm
44. nvidia-mathdx
45. nvidia-modelopt
46. nvidia-nvshmem-cu13
47. nvidia-resiliency-ext
48. nvidia-sphinx-theme
49. nvtx
50. omegaconf
51. one-logger
52. onnxscript
53. open-flamingo
54. open_clip_torch
55. opentelemetry-api
56. packaging
57. pandas
58. pulp
59. pybind11
60. pycocoevalcap
61. pydantic
62. pygithub
63. pylint
64. pytest
65. pytest-asyncio
66. pytest-cov
67. pytest-mock
68. pytest-random-order
69. python-gitlab
70. pyyaml
71. ruff
72. sentencepiece
73. setuptools
74. slack-sdk
75. sphinx
76. sphinx-autobuild
77. sphinx-autodoc2
78. sphinx-copybutton
79. tensorboard
80. tensorstore
81. tiktoken
82. timm
83. torch
84. torchprofile
85. tqdm
86. transformer-engine
87. transformers
88. triton
89. wandb
90. webdataset
91. wget
92. wrapt
93. zarr
