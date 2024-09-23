# LLM-Inference

- **Qwen2-MoE-57B-A14B-Instruct**, **2**张**A100 80GB**, **vLLM**, prompt_tokens=512, generated_tokens=128

| Benchmark | Requests per Second | Request Latency | Time to First Token | Inter Token Latency | Output Token Throughput |
| :---: | :---: | :---: | :---: | :---: | :---: |
| synchronous | 0.60 req/sec | 1.67 sec | 108.93 ms | 13.15 ms | 71.04 tokens/sec |
| asynchronous@1.27 req/sec | 0.00 req/sec | 0.00 sec | 0.00 ms | 0.00 ms | 0.00 tokens/sec |
| asynchronous@2.60 req/sec | 2.64 req/sec | 5.73 sec | 954.26 ms | 42.14 ms | 298.70 tokens/sec |
| asynchronous@1.94 req/sec | 2.82 req/sec | 20.61 sec | 14455.79 ms | 52.86 ms | 329.48 tokens/sec |
| asynchronous@3.27 req/sec | 3.15 req/sec | 5.57 sec | 133.07 ms | 46.03 ms | 372.05 tokens/sec |
| asynchronous@3.94 req/sec | 3.72 req/sec | 6.10 sec | 134.91 ms | 51.34 ms | 432.50 tokens/sec |
| asynchronous@4.61 req/sec | 4.37 req/sec | 6.74 sec | 135.41 ms | 56.41 ms | 511.91 tokens/sec |
| asynchronous@5.28 req/sec | 4.99 req/sec | 7.68 sec | 168.68 ms | 64.06 ms | 580.06 tokens/sec |
| asynchronous@5.95 req/sec | 5.56 req/sec | 8.06 sec | 151.98 ms | 67.87 ms | 648.10 tokens/sec |
| asynchronous@6.61 req/sec | 6.21 req/sec | 8.89 sec | 224.21 ms | 73.20 ms | 735.18 tokens/sec |
| throughput | 6.61 req/sec | 12.94 sec | 7201.07 ms | 50.12 ms | 762.60 tokens/sec |

- **Qwen2-MoE-57B-A14B-Instruct**, **4**张**A100 80GB**, **vLLM**, prompt_tokens=512, generated_tokens=128

| Benchmark | Requests per Second | Request Latency | Time to First Token | Inter Token Latency | Output Token Throughput |
| :---: | :---: | :---: | :---: | :---: | :---: |
| synchronous | 0.86 req/sec | 1.16 sec | 59.17 ms | 9.16 ms | 103.54 tokens/sec |
| asynchronous@3.17 req/sec | 3.11 req/sec | 2.62 sec | 82.49 ms | 21.32 ms | 370.10 tokens/sec |
| asynchronous@5.48 req/sec | 5.38 req/sec | 3.52 sec | 88.33 ms | 29.09 ms | 635.34 tokens/sec |
| asynchronous@7.79 req/sec | 7.57 req/sec | 4.43 sec | 96.01 ms | 36.37 ms | 902.13 tokens/sec |
| asynchronous@10.89 req/sec | 9.65 req/sec | 5.61 sec | 113.42 ms | 46.41 ms | 1144.13 tokens/sec |
| asynchronous@12.40 req/sec | 11.62 req/sec | 7.76 sec | 171.59 ms | 64.12 ms | 1374.91 tokens/sec |
| asynchronous@14.71 req/sec | 13.57 req/sec | 10.06 sec | 362.33 ms | 82.43 ms | 1598.08 tokens/sec |
| asynchronous@17.02 req/sec | 15.47 req/sec | 11.18 sec | 790.42 ms | 88.72 ms | 1812.07 tokens/sec |
| asynchronous@19.33 req/sec | 16.60 req/sec | 15.04 sec | 1958.73 ms | 111.07 ms | 1955.18 tokens/sec |
| asynchronous@21.64 req/sec | 16.61 req/sec | 15.14 sec | 2318.94 ms | 109.17 ms | 1955.27 tokens/sec |
| throughput | 21.64 req/sec | 12.96 sec | 2789.95 ms | 85.59 ms | 2562.78 tokens/sec |

- **Qwen2-MoE-57B-A14B-Instruct**, **4**张**L20 48GB**, **vLLM**, prompt_tokens=512, generated_tokens=128

| Benchmark | Requests per Second | Request Latency | Time to First Token | Inter Token Latency | Output Token Throughput |
| :---: | :---: | :---: | :---: | :---: | :---: |
| synchronous | 0.60 req/sec | 1.66 sec | 102.67 ms | 12.51 ms | 74.96 tokens/sec |
| asynchronous@1.60 req/sec | 1.55 req/sec | 4.34 sec | 107.70 ms | 33.33 ms | 194.63 tokens/sec |
| asynchronous@2.60 req/sec | 2.47 req/sec | 6.37 sec | 115.04 ms | 50.34 ms | 306.26 tokens/sec |
| asynchronous@3.60 req/sec | 3.36 req/sec | 8.24 sec | 117.62 ms | 65.02 ms | 418.99 tokens/sec |
| asynchronous@4.60 req/sec | 4.21 req/sec | 10.39 sec | 122.69 ms | 81.49 ms | 528.78 tokens/sec |
| asynchronous@5.59 req/sec | 4.94 req/sec | 13.75 sec | 128.63 ms | 108.80 ms | 618.56 tokens/sec |
| asynchronous@6.59 req/sec | 5.39 req/sec | 20.65 sec | 137.29 ms | 163.84 ms | 675.05 tokens/sec |
| asynchronous@7.59 req/sec | 5.48 req/sec | 31.32 sec | 164.91 ms | 248.44 ms | 686.80 tokens/sec |
| asynchronous@8.59 req/sec | 6.56 req/sec | 30.26 sec | 595.15 ms | 238.95 ms | 814.02 tokens/sec |
| asynchronous@9.59 req/sec | 7.72 req/sec | 30.48 sec | 2686.60 ms | 221.47 ms | 966.51 tokens/sec |
| throughput | 9.59 req/sec | 28.29 sec | 12336.68 ms | 126.95 ms | 1206.04 tokens/sec |

- **Qwen2-72B-Instruct**, **4**张**L20 48GB**, **vLLM**, prompt_tokens=512, generated_tokens=128

| Benchmark | Requests per Second | Request Latency | Time to First Token | Inter Token Latency | Output Token Throughput |
| :---: | :---: | :---: | :---: | :---: | :---: |
| synchronous | 0.15 req/sec | 6.58 sec | 341.05 ms | 49.39 ms | 19.20 tokens/sec |
| asynchronous@0.40 req/sec | 0.38 req/sec | 8.45 sec | 363.28 ms | 63.33 ms | 48.38 tokens/sec |
| asynchronous@0.65 req/sec | 0.60 req/sec | 9.81 sec | 367.59 ms | 73.93 ms | 76.74 tokens/sec |
| asynchronous@0.89 req/sec | 0.81 req/sec | 11.99 sec | 374.18 ms | 90.99 ms | 103.61 tokens/sec |
| asynchronous@1.14 req/sec | 1.02 req/sec | 13.67sec | 373.19 ms | 104.54 ms | 129.41 tokens/sec |
| asynchronous@1.38 req/sec | 1.23 req/sec | 16.86 sec | 374.24 ms | 131.03 ms | 154.53 tokens/sec |
| asynchronous@2.12 req/sec | 1.32 req/sec | 42.05 sec | 384.80 ms | 325.78 ms | 168.68 tokens/sec |
| asynchronous@1.63 req/sec | 1.33 req/sec | 22.24 sec | 374.85 ms | 170.33 ms | 170.45 tokens/sec |
| asynchronous@1.88 req/sec | 1.44 req/sec | 27.65 sec | 377.03 ms | 213.03 ms | 184.08 tokens/sec |
| asynchronous@2.37 req/sec | 1.40 req/sec | 46.71 sec | 2116.82 ms | 349.02 ms | 178.60 tokens/sec |
| throughput | 2.37 req/sec | 37.61 sec | 18838.55 ms | 147.87 ms | 301.51 tokens/sec |

- **Qwen2-72B-Instruct**, **4**张**A100 80GB**, **vLLM**, prompt_tokens=512, generated_tokens=128

| Benchmark | Requests per Second | Request Latency | Time to First Token | Inter Token Latency | Output Token Throughput |
| :---: | :---: | :---: | :---: | :---: | :---: |
| synchronous | 0.25 req/sec | 3.99 sec | 170.13 ms | 30.10 ms | 31.81 tokens/sec |
| asynchronous@0.95 req/sec | 0.92 req/sec | 4.70 sec | 186.39 ms | 35.86 ms | 115.61 tokens/sec |
| asynchronous@2.14 req/sec | 1.57 req/sec | 5.71 sec | 190.57 ms | 43.86 ms | 198.45 tokens/sec |
| asynchronous@3.04 req/sec | 2.23 req/sec | 6.65 sec | 193.15 ms | 51.36 ms | 280.45 tokens/sec |
| asynchronous@3.73 req/sec | 2.84 req/sec | 8.30 sec | 198.65 ms | 64.55 ms | 356.28 tokens/sec |
| asynchronous@5.37 req/sec | 3.49 req/sec | 9.74 sec | 198.39 ms | 75.67 ms | 439.75 tokens/sec |
| asynchronous@5.82 req/sec | 3.83 req/sec | 40.48 sec | 263.77 ms | 319.40 ms | 481.72 tokens/sec |
| asynchronous@6.43 req/sec | 3.99 req/sec | 12.39 sec | 206.21 ms | 96.47 ms | 503.42 tokens/sec |
| asynchronous@5.13 req/sec | 4.31 req/sec | 19.87 sec | 230.70 ms | 155.93 ms | 542.64 tokens/sec |
| asynchronous@6.52 req/sec | 4.45 req/sec | 40.69 sec | 1279.20 ms | 311.89 ms | 560.28 tokens/sec |
| throughput | 6.52 req/sec | 22.22 sec | 10585.28 ms | 92.68 ms | 820.45 tokens/sec |

- **Qwen2-72B-Instruct-AWQ**, **2**张**A100 80GB**, **vLLM**, prompt_tokens=512, generated_tokens=128

| Benchmark | Requests per Second | Request Latency | Time to First Token | Inter Token Latency | Output Token Throughput |
| :---: | :---: | :---: | :---: | :---: | :---: |
| synchronous | 0.33 req/sec | 3.04 sec | 271.30 ms | 21.94 ms | 41.50 tokens/sec |
| asynchronous@0.63 req/sec | 0.00 req/sec | 0.00 sec | 0.00 ms | 0.00 ms | 0.00 tokens/sec |
| asynchronous@1.22 req/sec | 0.00 req/sec | 0.00 sec | 0.00 ms | 0.00 ms | 0.00 tokens/sec |
| asynchronous@1.81 req/sec | 1.76 req/sec | 7.16 sec | 1221.93 ms | 47.64 ms | 220.15 tokens/sec |
| asynchronous@1.52 req/sec | 1.89 req/sec | 8.15 sec | 2470.27 ms | 45.56 ms | 236.56 tokens/sec |
| asynchronous@2.11 req/sec | 2.00 req/sec | 6.69 sec | 305.82 ms | 50.51 ms | 251.25 tokens/sec |
| asynchronous@2.40 req/sec | 2.23 req/sec | 8.99 sec | 295.25 ms | 69.52 ms | 277.78 tokens/sec |
| asynchronous@0.92 req/sec | 2.38 req/sec | 59.67 sec | 47749.75 ms | 93.79 ms | 302.54 tokens/sec |
| asynchronous@2.70 req/sec | 2.47 req/sec | 11.29 sec | 301.31 ms | 87.90 ms | 308.75 tokens/sec |
| asynchronous@3.00 req/sec | 2.54 req/sec | 19.58 sec | 323.69 ms | 154.16 ms | 316.64 tokens/sec |
| throughput | 3.00 req/sec | 32.95 sec | 21991.54 ms | 88.49 ms | 371.77 tokens/sec |

- **Qwen2-72B-Instruct-AWQ**, **4**张**A100 80GB**, **vLLM**, prompt_tokens=512, generated_tokens=128

| Benchmark | Requests per Second | Request Latency | Time to First Token | Inter Token Latency | Output Token Throughput |
| :---: | :---: | :---: | :---: | :---: | :---: |
| synchronous | 0.47 req/sec | 2.14 sec | 166.60 ms | 15.60 ms | 59.06 tokens/sec |
| asynchronous@0.95 req/sec | 0.00 req/sec | 0.00 sec | 0.00 ms | 0.00 ms | 0.00 tokens/sec |
| asynchronous@1.92 req/sec | 1.73 req/sec | 72.37 sec | 64685.62 ms | 61.02 ms | 217.53 tokens/sec |
| asynchronous@2.41 req/sec | 1.93 req/sec | 48.26 sec | 40852.96 ms | 58.72 ms | 243.79 tokens/sec |
| asynchronous@3.38 req/sec | 2.52 req/sec | 24.33 sec | 15534.01 ms | 70.08 ms | 316.45 tokens/sec |
| asynchronous@2.89 req/sec | 2.57 req/sec | 47.78 sec | 40333.59 ms | 59.95 ms | 319.90 tokens/sec |
| asynchronous@1.44 req/sec | 3.25 req/sec | 34.56 sec | 26211.54 ms | 66.75 ms | 406.38 tokens/sec |
| asynchronous@3.86 req/sec | 3.72 req/sec | 7.20 sec | 248.93 ms | 55.78 ms | 465.06 tokens/sec |
| asynchronous@4.35 req/sec | 4.03 req/sec | 9.93 sec | 231.41 ms | 77.68 ms | 503.26 tokens/sec |
| asynchronous@4.83 req/sec | 4.62 req/sec | 15.54 sec | 1296.91 ms | 114.34 ms | 578.04 tokens/sec |
| throughput | 4.83 req/sec | 18.78 sec | 11397.47 ms | 58.24 ms | 608.24 tokens/sec |

- **Qwen2-72B-Instruct-GPTQ-Int8**, **4**张**L20 48GB**, **vLLM**, prompt_tokens=512, generated_tokens=128

| Benchmark | Requests per Second | Request Latency | Time to First Token | Inter Token Latency | Output Token Throughput |
| :---: | :---: | :---: | :---: | :---: | :---: |
| synchronous | 0.24 req/sec | 4.17 sec | 329.85 ms | 30.09 ms | 30.59 tokens/sec |
| asynchronous@0.48 req/sec | 0.46 req/sec | 4.92 sec | 342.78 ms | 35.84 ms | 59.37 tokens/sec |
| asynchronous@0.71 req/sec | 0.69 req/sec | 5.34 sec | 342.78 ms | 39.39 ms | 87.50 tokens/sec |
| asynchronous@0.95 req/sec | 0.90 req/sec | 6.60 sec | 345.08 ms | 47.18 ms | 115.55 tokens/sec |
| asynchronous@1.19 req/sec | 1.11 req/sec | 8.68 sec | 350.07 ms | 63.83 ms | 140.81 tokens/sec |
| asynchronous@2.37 req/sec | 1.18 req/sec | 46.68 sec | 365.00 ms | 362.04 ms | 150.95 tokens/sec |
| asynchronous@1.42 req/sec | 1.31 req/sec | 9.81 sec | 349.53 ms | 74.25 ms | 167.76 tokens/sec |
| asynchronous@1.65 req/sec | 1.48 req/sec | 12.92 sec | 350.44 ms | 97.86 ms | 189.27 tokens/sec |
| asynchronous@1.89 req/sec | 1.65 req/sec | 16.23 sec | 352.28 ms | 124.92 ms | 210.00 tokens/sec |
| asynchronous@2.13 req/sec | 1.69 req/sec | 23.54 sec | 352.56 ms | 182.30 ms | 216.17 tokens/sec |
| throughput | 2.37 req/sec | 58.61 sec | 29018.12 ms | 232.41 ms | 302.06 tokens/sec |

- **Qwen2-72B-Instruct**, **8**张**A100 80GB**, **vLLM**, prompt_tokens=512, generated_tokens=128

| Benchmark | Requests per Second | Request Latency | Time to First Token | Inter Token Latency | Output Token Throughput |
| :---: | :---: | :---: | :---: | :---: | :---: |
| synchronous | 0.40 req/sec | 2.51 sec | 118.60 ms | 18.83 ms | 50.58 tokens/sec |
| asynchronous@1.67 req/sec | 1.63 req/sec | 3.41 sec | 132.56 ms | 26.00 ms | 206.07 tokens/sec |
| asynchronous@2.94 req/sec | 2.84 req/sec | 4.29 sec | 137.60 ms | 33.06 ms | 357.63 tokens/sec |
| asynchronous@4.21 req/sec | 4.05 req/sec | 5.43 sec | 142.57 ms | 42.03 ms | 509.93 tokens/sec |
| asynchronous@5.49 req/sec | 5.20 req/sec | 6.70 sec | 146.38 ms | 52.11 ms | 654.92 tokens/sec |
| asynchronous@6.76 req/sec | 6.06 req/sec | 12.27 sec | 188.13 ms | 95.88 ms | 764.05 tokens/sec |
| asynchronous@8.03 req/sec | 6.53 req/sec | 21.28 sec | 237.06 ms | 166.83 ms | 823.78 tokens/sec |
| asynchronous@9.30 req/sec | 7.16 req/sec | 27.42 sec | 469.00 ms | 213.92 ms | 901.59  tokens/sec |
| asynchronous@11.85 req/sec | 7.99 req/sec | 28.25 sec | 7112.56 ms | 166.51 ms | 1012.46 tokens/sec |
| asynchronous@10.58 req/sec | 9.26 req/sec | 27.67 sec | 3097.94 ms |192.70 ms | 1170.20 tokens/sec |
| throughput | 11.85 req/sec | 19.86 sec | 7378.75 ms | 95.77 ms | 1500.41 tokens/sec |

- **Qwen2-72B-Instruct**, **8**张**L20 48GB**, SGLang, prompt_tokens=512, generated_tokens=128

| Benchmark | Requests per Second | Request Latency | Time to First Token | Inter Token Latency | Output Token Throughput |
| :---: | :---: | :---: | :---: | :---: | :---: |
| synchronous | 0.26 req/sec | 3.89 sec | 172.61 ms | 29.17 ms | 32.75 tokens/sec |
| asynchronous@1.20 req/sec | 1.16 req/sec | 4.34 sec | 54.81 ms | 33.58 ms | 148.29 tokens/sec |
| asynchronous@2.14 req/sec | 2.04 req/sec | 5.98 sec | 61.16 ms | 46.46 ms | 260.03 tokens/sec |
| asynchronous@3.08 req/sec | 2.90 req/sec | 7.52 sec | 67.03 ms | 58.29 ms | 369.44 tokens/sec |
| asynchronous@4.02 req/sec | 3.79 req/sec | 7.19 sec | 65.10 ms | 55.75 ms | 484.42 tokens/sec |
| asynchronous@4.96 req/sec | 4.64 req/sec | 8.10 sec | 68.00 ms | 62.91 ms | 591.39 tokens/sec |
| asynchronous@5.90 req/sec | 5.50 req/sec | 8.43 sec | 69.78 ms | 65.68 ms | 699.85 tokens/sec |
| asynchronous@6.85 req/sec | 6.34 req/sec | 9.09 sec | 69.10 ms | 70.80 ms | 807.47 tokens/sec |
| asynchronous@7.79 req/sec | 7.09 req/sec | 10.70 sec | 70.55 ms | 83.45 ms | 902.96 tokens/sec |
| asynchronous@8.73 req/sec | 7.68 req/sec | 12.53 sec | 79.25 ms | 97.56 ms | 979.95 tokens/sec |
| throughput | 8.73 req/sec | 17.46 sec | 3983.31 ms | 105.63 ms | 1113.39 tokens/sec |

- **Qwen2-72B-Instruct**, **8**张**L20 48GB**, **vLLM**, prompt_tokens=512, generated_tokens=128

| Benchmark | Requests per Second | Request Latency | Time to First Token | Inter Token Latency | Output Token Throughput |
| :---: | :---: | :---: | :---: | :---: | :---: |
| synchronous | 0.25 req/sec | 4.01 sec | 244.63 ms | 29.53 ms | 31.79 tokens/sec |
| asynchronous@0.58 req/sec | 0.57 req/sec | 4.65 sec | 259.10 ms | 34.70 ms | 71.93 tokens/sec |
| asynchronous@0.92 req/sec | 0.88 req/sec | 5.44 sec | 259.82 ms | 40.59 ms | 112.65 tokens/sec |
| asynchronous@1.25 req/sec | 1.20 req/sec | 6.17 sec | 259.94 ms | 46.52 ms | 152.90 tokens/sec |
| asynchronous@3.25 req/sec | 1.26 req/sec | 54.06 sec | 284.48 ms | 72.18 ms | 160.09 tokens/sec |
| asynchronous@1.58 req/sec | 1.46 req/sec | 9.62 sec | 265.39 ms | 98.31 ms | 186.95 tokens/sec |
| asynchronous@1.92 req/sec | 1.72 req/sec | 12.79 sec | 271.90 ms | 120.31 ms | 219.62 tokens/sec |
| asynchronous@2.25 req/sec | 1.96 req/sec | 15.73 sec | 271.93 ms | 232.41 ms | 250.68 tokens/sec |
| asynchronous@2.92 req/sec | 2.13 req/sec | 29.94 sec | 286.32 ms | 149.38 ms | 271.11 tokens/sec |
| asynchronous@2.58 req/sec | 2.16 req/sec | 19.32 sec | 273.15 ms | 191.72 ms | 275.22 tokens/sec |
| throughput | 3.25 req/sec | 43.96 sec | 19640.90 ms | 196.41 ms | 413.55 tokens/sec |

- **Qwen2-72B-Instruct**, **8**张**L20 48GB**, lmdeploy, prompt_tokens=512, generated_tokens=128
  
| Benchmark | Requests per Second | Request Latency | Time to First Token | Inter Token Latency | Output Token Throughput |
| :---: | :---: | :---: | :---: | :---: | :---: |
| synchronous | 0.26 req/sec | 3.85 sec | 243.20 ms | 28.34 ms | 33.29 tokens/sec |
| asynchronous@0.59 req/sec | 0.58 req/sec | 4.32 sec | 258.16 ms | 31.76 ms | 74.70 tokens/sec |
| asynchronous@0.93 req/sec | 0.90 req/sec | 4.76 sec | 259.42 ms | 35.36 ms | 115.06 tokens/sec |
| asynchronous@1.26 req/sec | 1.22 req/sec | 5.28 sec | 260.75 ms | 39.56 ms | 155.86 tokens/sec |
| asynchronous@1.59 req/sec | 1.52 req/sec | 6.12 sec | 264.07 ms | 45.86 ms | 195.58 tokens/sec |
| asynchronous@1.93 req/sec | 1.79 req/sec | 8.72 sec | 274.75 ms | 66.36 ms | 229.81 tokens/sec |
| asynchronous@2.26 req/sec | 2.08 req/sec | 10.28 sec | 281.24 ms | 78.35 ms | 266.82 tokens/sec |
| asynchronous@2.59 req/sec | 2.33 req/sec | 12.22 sec | 291.09 ms | 93.72 ms | 299.51 tokens/sec |
| asynchronous@2.93 req/sec | 2.59 req/sec | 14.61 sec | 311.31 ms | 111.98 ms | 332.61 tokens/sec |
| asynchronous@3.26 req/sec | 2.74 req/sec | 19.23 sec | 368.23 ms | 147.98 ms | 352.21 tokens/sec |
| throughput | 3.26 req/sec | 40.90 sec | 19009.19 ms | 171.70 ms | 418.47 tokens/sec |