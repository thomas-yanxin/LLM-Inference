# LLM-Inference

## 提要
1. 对比**不同硬件**LLM的推理性能影响，如A100、L20等，便于推理显卡选型
2. 对比**不同推理引擎**对LLM的推理性能影响，如vLLM、lmdeploy、SGLang，便于推理引擎选型
3. 对比**不同参数**下的推理速度，如7B、14B、32B、57B、72B等，便于LLM参数选型
4. 对比**不同量化算法**对LLM推理速度的影响，如AWQ、GPTQ等

## 细节
- **Qwen2-7B-Instruct**, **1**张**L20 48GB**, **vLLM**, prompt_tokens=512,generated_tokens=128

| Benchmark | Requests per Second | Request Latency | Time to First Token | Inter Token Latency | Output Token Throughput |
| :---------: | :----------: | :--------: | :------------: | :----------: | :------------: |
| synchronous | 0.51 req/sec | 1.96 sec | 95.57 ms | 21.01 ms | 45.36 tokens/second |
| asynchronous@1.57 req/sec | 1.56 req/sec | 2.26 sec | 104.42 ms | 25.96 ms | 129.68 tokens/second |
| asynchronous@2.63 req/sec | 2.59 req/sec | 2.66 sec | 105.14 ms | 29.47 ms | 223.06 tokens/second |
| asynchronous@3.69 req/sec | 3.58 req/sec | 2.92 sec | 105.69 ms | 34.76 ms | 290.81 tokens/second |
| asynchronous@4.75 req/sec | 4.62 req/sec | 3.56 sec | 106.69 ms | 44.34 ms | 361.81 tokens/second |
| asynchronous@5.80 req/sec | 5.60 req/sec | 4.93 sec | 112.41 ms | 60.59 ms | 447.11 tokens/second |
| asynchronous@6.86 req/sec | 6.41 req/sec | 7.03 sec | 115.36 ms | 90.19 ms | 493.44 tokens/second |
| asynchronous@8.98 req/sec | 7.06 req/sec | 220.06 sec | 1090.02 sec | 299.34 ms | 497.25 tokens/second |
| asynchronous@7.92 req/sec | 7.15 req/sec | 11.19 sec | 127.62 ms | 155.64 ms | 510.62 tokens/second |
| asynchronous@10.04 req/sec | 7.20 req/sec | 26.01 sec | 4674.95 ms | 300.86 ms | 510.64 tokens/second |
| throughput | 10.04 req/sec |  22.65 sec | 11571.36 ms | 135.46 ms | 826.03 tokens/second |


- **Qwen2-7B-Instruct-GPTQ-Int4**, **1**张**L20 48GB**, **vLLM**, prompt_tokens=512,generated_tokens=128

| Benchmark | Requests per Second | Request Latency | Time to First Token | Inter Token Latency | Output Token Throughput |
| :---: | :---: | :---: | :---: | :---: | :---: |
| synchronous | 0.93 req/sec | 1.07 sec | 81.01 ms | 7.72 ms | 119.62 tokens/second |
| asynchronous@1.86 req/sec | 1.85 req/sec | 1.28 sec | 85.62 ms | 9.33 ms | 236.78 tokens/second |
| asynchronous@2.79 req/sec | 2.79 req/sec | 1.40 sec | 85.74 ms | 10.27 ms | 353.79 tokens/second |
| asynchronous@3.71 req/sec | 3.67 req/sec | 1.58 sec | 87.64 ms | 11.67 ms | 469.37 tokens/second |
| asynchronous@4.64 req/sec | 4.58 req/sec | 1.86 sec | 89.64 ms | 13.90 ms | 585.89 tokens/second |
| asynchronous@5.57 req/sec | 5.48 req/sec | 2.13 sec | 89.34 ms | 16.04 ms | 699.73 tokens/second |
| asynchronous@6.50 req/sec | 6.35 req/sec | 2.91 sec | 93.91 ms | 22.04 ms | 811.96 tokens/second |
| asynchronous@9.28 req/sec | 6.28 req/sec | 26.70 sec | 846.93 ms | 201.96 ms | 872.94 tokens/second |
| asynchronous@8.35 req/sec | 7.09 req/sec | 13.80 sec | 121.52 ms | 106.90 ms | 906.62 tokens/second |
| asynchronous@7.42 req/sec | 7.19 req/sec | 4.11 sec | 98.44 ms | 31.27 ms | 919.72 tokens/second |
| throughput | 9.28 req/sec | 38.53 sec | 22296.98 ms | 126.94 ms | 1,187.02 tokens/second |


- **Qwen2-7B-Instruct**, **2**张**L20 48GB**, **vLLM**, prompt_tokens=512,generated_tokens=128

| Benchmark | Requests per Second | Request Latency | Time to First Token | Inter Token Latency | Output Token Throughput |
| :---: | :---: | :---: | :---: | :---: | :---: |
| synchronous | 0.85 req/sec | 1.18 sec | 18.22 ms | 13.28 ms | 73.72 tokens/second |
| asynchronous@2.02 req/sec | 2.01 req/sec | 1.37 sec | 65.28 ms | 14.65 ms | 178.86 tokens/second |
| asynchronous@3.19 req/sec | 3.17 req/sec | 1.56 sec | 70.41 ms | 16.23 ms | 291.56 tokens/second |
| asynchronous@4.73 req/sec | 4.30 req/sec | 1.70 sec | 71.90 ms | 18.08 ms | 387.99 tokens/second |
| asynchronous@5.54 req/sec | 5.48 req/sec | 1.91 sec | 73.71 ms | 20.04 ms | 501.26 tokens/second |
| asynchronous@6.71 req/sec | 6.60 req/sec | 2.08 sec | 76.08 ms | 22.45 ms | 588.40 tokens/second |
| asynchronous@7.89 req/sec | 7.80 req/sec | 2.38 sec | 79.62 ms | 26.33 ms | 681.36 tokens/second |
| asynchronous@9.06 req/sec | 8.87 req/sec | 2.79 sec | 85.73 ms | 30.81 ms | 779.04 tokens/second |
| asynchronous@10.23 req/sec | 9.94 req/sec | 3.29 sec | 94.18 ms | 37.74 ms | 842.25 tokens/second |
| asynchronous@11.41 req/sec | 10.95 req/sec | 4.65 sec | 125.47 ms | 51.12 ms | 969.20 tokens/second |
| throughput | 11.41 req/sec | 22.08 sec | 16322.32 ms | 66.36 ms | 990.34 tokens/second |

- **Qwen2-7B-Instruct**, **2**张**L20 48GB**, SGLang, prompt_tokens=512,generated_tokens=128

| Benchmark | Requests per Second | Request Latency | Time to First Token | Inter Token Latency | Output Token Throughput |
|---|---|---|---|---|---|
| synchronous | 0.74 req/sec | 1.34 sec | 35.26 ms | 10.30 ms | 94.50 tokens/second |
| asynchronous@3.79 req/sec | 3.75 req/sec | 1.50 sec | 26.39 ms | 11.53 ms | 479.23 tokens/second |
| asynchronous@6.84 req/sec | 6.76 req/sec | 1.64 sec | 28.07 ms | 12.56 ms | 860.99 tokens/second |
| asynchronous@9.89 req/sec | 9.74 req/sec | 1.88 sec | 28.79 ms | 14.52 ms | 1243.22 tokens/second |
| asynchronous@12.94 req/sec | 12.73 req/sec | 2.05 sec | 33.27 ms | 15.78 ms | 1620.30 tokens/second |
| asynchronous@15.99 req/sec | 15.68 req/sec | 2.38 sec | 39.97 ms | 18.39 ms | 1996.72 tokens/second |
| asynchronous@19.04 req/sec | 18.62 req/sec | 2.66 sec | 57.56 ms | 20.47 ms | 2370.17 tokens/second |
| asynchronous@22.09 req/sec | 21.58 req/sec | 2.86 sec | 91.01 ms | 21.77 ms | 2744.02 tokens/second |
| asynchronous@28.19 req/sec | 24.50 req/sec | 4.97 sec | 300.49 ms | 37.36 ms | 3063.57 tokens/second |
| asynchronous@25.14 req/sec | 24.54 req/sec | 3.08 sec | 183.85 ms | 23.01 ms | 3092.86 tokens/second |
| throughput | 28.19 req/sec | 3.64 sec | 212.52 ms | 27.55 ms |3509.59 tokens/second |

- **Qwen2-7B-Instruct**, **2**张**L20 48GB**, **lmdeploy**, prompt_tokens=512,generated_tokens=128
  
| Benchmark | Requests per Second | Request Latency | Time to First Token | Inter Token Latency | Output Token Throughput |
| :---: | :---: | :---: | :---: | :---: | :---: |
| synchronous | 0.74 req/sec | 1.35 sec | 69.60 ms | 10.06 ms | 94.99 tokens/second |
| asynchronous@2.34 req/sec | 2.30 req/sec | 1.57 sec | 77.25 ms | 11.69 ms | 298.34 tokens/second |
| asynchronous@3.94 req/sec | 3.89 req/sec | 1.75 sec | 80.25 ms | 13.12 ms | 499.34 tokens/second |
| asynchronous@5.53 req/sec | 5.45 req/sec | 2.01 sec | 82.67 ms | 15.12 ms | 700.77 tokens/second |
| asynchronous@7.13 req/sec | 6.99 req/sec | 2.53 sec | 88.20 ms | 19.19 ms | 896.15 tokens/second |
| asynchronous@8.73 req/sec | 8.51 req/sec | 3.01 sec | 95.18 ms | 22.94 ms | 1099.13 tokens/second |
| asynchronous@10.32 req/sec | 10.00 req/sec | 3.95 sec | 109.94 ms | 30.18 ms | 1282.70 tokens/second |
| asynchronous@11.92 req/sec | 11.45 req/sec | 4.97 sec | 130.29 ms | 38.04 ms | 1468.02 tokens/second |
| asynchronous@13.52 req/sec | 12.82 req/sec | 6.75 sec | 184.79 ms | 51.72 ms | 1641.09 tokens/second |
| asynchronous@15.11 req/sec | 13.96 req/sec | 9.76 sec | 1585.32 ms | 66.55 ms | 1729.01 tokens/second |
| throughput | 15.11 req/sec | 16.58 sec | 10868.75 ms | 45.38 | 1915.20 tokens/second |


- **Qwen2-7B-Instruct**, **1**张**A100 80GB**, **vLLM**, prompt_tokens=512,generated_tokens=128
  

| Benchmark | Requests per Second | Request Latency | Time to First Token | Inter Token Latency | Output Token Throughput |
| :---: | :---: | :---: | :---: | :---: | :---: |
| synchronous | 0.75 req/sec | 1.34 sec | 59.82 ms | 11.55 ms | 82.66 tokens/second |
| asynchronous@2.65 req/sec | 2.63 req/sec | 1.62 sec | 69.16 ms | 13.61 ms | 298.87 tokens/second |
| asynchronous@4.55 req/sec | 4.49 req/sec | 1.91 sec | 75.56 ms | 16.13 ms | 510.32 tokens/second |
| asynchronous@6.46 req/sec | 6.38 req/sec | 2.17 sec | 78.72 ms | 18.75 ms | 714.21 tokens/second |
| asynchronous@8.36 req/sec | 8.20 req/sec | 2.60 sec | 88.49 ms | 22.36 ms | 921.63 tokens/second |
| asynchronous@10.27 req/sec | 10.01 req/sec | 3.33 sec | 100.43 ms | 28.68 ms | 1127.71 tokens/second |
| asynchronous@12.17 req/sec | 11.66 req/sec | 4.43 sec | 128.75 ms | 37.81 ms | 1327.32 tokens/second |
| asynchronous@14.08 req/sec | 13.13 req/sec | 6.36 sec | 309.98 ms | 53.77 ms | 1477.22 tokens/second |
| asynchronous@17.88 req/sec | 14.45 req/sec | 16.05 sec | 2246.04 ms | 122.78 ms | 1626.13 tokens/second |
| asynchronous@15.98 req/sec | 14.62 req/sec | 9.55 sec | 751.47 ms | 78.69 ms | 1639.94 tokens/second |
| throughput | 17.88 req/sec | 16.29 sec | 6509.10 ms | 87.06 ms | 2023.10 tokens/second |

- **Qwen2-7B-Instruct-AWQ**, **1**张**L20 48GB**, **vLLM**, prompt_tokens=512,generated_tokens=128

| Benchmark | Requests per Second | Request Latency | Time to First Taken | Inter Token Latency | Output Token Throughput |
| :---: | :---: | :---: | :---: | :---: | :---: |
| synchronous | 0.83 req/sec | 1.20 sec | 137.05 ms | 8.55 ms | 103.52 tokens/sec |
| asynchronous@1.71 req/sec | 1.69 req/sec | 1.54 sec | 142.75 ms | 11.08 ms | 213.42 tokens/sec |
| asynchronous@2.58 req/sec | 2.57 req/sec | 1.81 sec | 143.32 ms | 13.30 ms | 322.02 tokens/sec |
| asynchronous@3.45 req/sec | 3.41 req/sec | 2.19 sec | 144.91 ms | 16.48 ms | 423.82 tokens/sec |
| asynchronous@4.33 req/sec | 4.23 req/sec | 2.92 sec | 150.66 ms | 22.20 ms | 529.97 tokens/sec |
| asynchronous@6.95 req/sec | 4.80 req/sec | 37.01 sec | 1110.06 ms | 286.57 ms | 599.75 tokens/sec |
| asynchronous@6.07 req/sec | 4.98 req/sec | 19.37 sec | 218.08 ms | 154.17 ms | 617.82 tokens/sec |
| asynchronous@5.20 req/sec | 5.02 req/sec | 4.67 sec | 157.80 ms | 36.41 ms | 621.91 tokens/sec |
| asynchronous@7.82 req/sec | 5.60 req/sec | 37.15 sec | 3553.69 ms | 269.73 ms | 689.06 tokens/sec |
| asynchronous@8.69 req/sec | 7.61 req/sec | 32.74 sec | 7479.98 ms | 204.23 ms | 943.87 tokens/sec |
| throughput | 8.69 req/sec | 42.64 sec | 24549.94 ms | 145.07 ms | 1086.64 tokens/sec |


- **Qwen2-7B-Instruct-AWQ**, **1**张**A100 80GB**, **vLLM**, prompt_tokens=512,generated_tokens=128

| Benchmark | Requests per Second | Request Latency | Time to First Token | Inter Token Latency | Output Token Throughput |
| :---: | :---: | :---: | :---: | :---: | :---: |
| synchronous | 0.84 req/sec | 1.19 sec | 96.46 ms | 9.55 ms | 96.19 tokens/sec |
| asynchronous@2.24 req/sec | 2.22 req/sec | 1.50 sec | 104.14 ms | 12.01 ms | 258.43 tokens/sec |
| asynchronous@3.65 req/sec | 3.60 req/sec | 1.95 sec | 107.59 ms | 15.41 ms | 430.04 tokens/sec |
| asynchronous@5.65 req/sec | 4.98 req/sec | 2.53 sec | 112.90 ms | 20.48 ms | 588.42 tokens/sec |
| asynchronous@6.45 req/sec | 6.29 req/sec | 3.88 sec | 127.94 ms | 224.10 ms | 741.79 tokens/sec |
| asynchronous@9.26 req/sec | 7.15 req/sec | 26.25 sec | 262.79 ms | 224.10 ms | 829.62 tokens/sec |
| asynchronous@7.86 req/sec | 7.28 req/sec | 9.03 sec | 168.94 ms | 74.84 ms | 861.98 tokens/sec |
| asynchronous@10.66 req/sec | 8.75 req/sec | 24.36 sec | 866.62 ms | 201.19 ms | 1021.06 tokens/sec |
| asynchronous@13.47 req/sec | 9.56 req/sec | 29.18 sec | 9072.17 ms | 170.34 ms | 1124.06 tokens/sec |
| asynchronous@12.07 req/sec | 9.58 req/sec | 25.66 sec | 3779.77 ms | 186.17 ms | 1121.71 tokens/sec |
| throughput | 13.47 req/sec | 26.21 sec | 11036.84 ms | 127.38 ms | 1610.04 tokens/sec |


- **Qwen2-7B-Instruct-GPTQ-Int4**, **1**张**A100 80GB**, **vLLM**, prompt_tokens=512,generated_tokens=128

| Benchmark | Requests per Second | Request Latency | Time to First Token | Inter Token Latency | Output Token Throughput |
| :---: | :---: | :---: | :---: | :---: | :---: |
| synchronous | 1.31 req/sec | 0.76 sec | 58.71 ms | 6.19 ms | 148.91 tokens/sec |
| asynchronous@3.01 req/sec | 3.00 req/sec | 0.88 sec | 65.40 ms | 7.32 ms | 335.07 tokens/sec |
| asynchronous@4.71 req/sec | 4.67 req/sec | 1.08 sec | 70.76 ms | 8.81 ms | 535.72 tokens/sec |
| asynchronous@6.41 req/sec | 6.39 req/sec | 1.22 sec | 73.55 ms | 10.23 ms | 714.67 tokens/sec |
| asynchronous@8.12 req/sec | 8.07 req/sec | 1.44 sec | 78.66 ms | 12.13 ms | 908.74 tokens/sec |
| asynchronous@9.82 req/sec | 9.66 req/sec | 2.00 sec | 93.99 ms | 16.82 ms | 1093.66 tokens/sec |
| asynchronous@11.52 req/sec | 11.36 req/sec | 2.80 sec | 124.99 ms | 23.39 ms | 1300.61 tokens/sec |
| asynchronous@13.22 req/sec | 12.49 req/sec | 6.56 sec | 321.97 ms | 54.38 ms | 1434.04 tokens/sec |
| asynchronous@16.33 req/sec | 12.95 req/sec | 18.12 sec | 2907.50 ms | 134.57 ms | 1464.07 tokens/sec |
| asynchronous@14.92 req/sec | 13.85 req/sec | 11.42 sec | 1146.18 ms | 90.41 ms | 1576.69 tokens/sec |
| throughput | 16.63 req/sec | 24.89 sec | 13360.29 ms | 101.44 ms | 1894.73 tokens/sec |

- **Qwen2-7B-Instruct-GPTQ-Int8**, **1**张**A100 80GB**, **vLLM**, prompt_tokens=512,generated_tokens=128

| Benchmark | Requests per Second | Request Latency | Time to First Token | Inter Token Latency | Output Token Throughput |
|---|---|---|---|---|---|
| synchronous | 1.04 req/sec | 0.96 sec | 66.87 ms | 7.86 ms | 118.41 tokens/sec |
| asynchronous@2.55 req/sec | 2.54 req/sec | 1.17 sec | 78.89 ms | 9.50 ms | 291.54 tokens/sec |
| asynchronous@4.87 req/sec | 4.04 req/sec | 1.31 sec | 79.79 ms | 10.92 ms | 455.36 tokens/sec |
| asynchronous@5.58 req/sec | 5.52 req/sec | 1.53 sec | 85.05 ms | 12.88 ms | 619.24 tokens/sec |
| asynchronous@7.10 req/sec | 7.00 req/sec | 1.83 sec | 89.12 ms | 15.35 ms | 792.95 tokens/sec |
| asynchronous@8.61 req/sec | 8.51 req/sec | 2.40 sec | 98.71 ms | 20.54 ms | 954.91 tokens/sec |
| asynchronous@10.12 req/sec | 9.90 req/sec | 3.34 sec | 128.87 ms | 28.37 ms | 1122.10 tokens/sec |
| asynchronous@11.46 req/sec | 10.65 req/sec | 7.89 sec | 225.46 ms | 67.87 ms | 1203.02 tokens/sec |
| asynchronous@13.15 req/sec | 11.77 req/sec | 13.37 sec | 815.44 ms | 111.64 ms | 1325.43 tokens/sec |
| asynchronous@14.67 req/sec | 12.34 req/sec | 20.47 sec | 2765.22 ms | 157.76 ms | 1384.63 tokens/sec |
| throughput | 14.67 req/sec | 25.93 sec | 3618.86 ms | 109.47 ms | 1655.82 tokens/sec |

- **Qwen2-14B-Instruct**, **1**张**L20 48GB**, **vLLM**, prompt_tokens=512,generated_tokens=128

| Benchmark | Requests per Second | Request Latency | Time to First Token | Inter Token Latency | Output Token Throughput |
| :---: | :---: | :---: | :---: | :---: | :---: |
| synchronous | 0.21 req/sec | 4.84 sec | 178.08 ms | 36.43 ms | 26.43 tokens/sec |
| asynchronous@0.57 req/sec | 0.55 req/sec | 5.53 sec | 195.90 ms | 41.68 ms | 71.00 tokens/sec |
| asynchronous@0.94 req/sec | 0.90 req/sec | 5.92 sec | 198.16 ms | 44.90 ms | 115.00 tokens/sec |
| asynchronous@1.31 req/sec | 1.24 req/sec | 6.53 sec | 198.82 ms | 49.61 ms | 158.72 tokens/sec |
| asynchronous@1.67 req/sec | 1.58 req/sec | 7.44 sec | 199.12 ms | 56.60 ms | 201.53 tokens/sec |
| asynchronous@2.04 req/sec | 1.88 req/sec | 9.52 sec | 202.99 ms | 73.18 ms | 240.06 tokens/sec |
| asynchronous@2.40 req/sec | 2.19 req/sec | 11.08 sec | 203.57 ms | 85.24 ms | 279.84 tokens/sec |
| asynchronous@2.77 req/sec | 2.49 req/sec | 12.53 sec | 205.20 ms | 96.86 ms | 318.46 tokens/sec |
| asynchronous@3.14 req/sec | 2.75 req/sec | 15.09 sec | 207.36 ms | 116.08 ms | 350.78 tokens/sec |
| asynchronous@3.50 req/sec | 2.92 req/sec | 15.9 sec | 207.36 ms | 116.08 ms | 371.90 tokens/sec |
| throughput | 3.50 req/sec | 25.43 sec | 213.43 ms | 105.60 ms | 448.10 tokens/sec |

- **Qwen2-14B-Instruct**, **4**张**L20 48GB**, **vLLM**, prompt_tokens=512,generated_tokens=128

| Benchmark | Requests per Second | Request Latency | Time to First Token | Inter Token Latency | Output Token Throughput |
| :---: | :---: | :---: | :---: | :---: | :---: |
| synchronous | 0.58 req/sec | 1.73 sec | 102.73 ms | 12.72 ms | 73.90 tokens/sec |
| asynchronous@1.46 req/sec | 1.45 req/sec | 2.18 sec | 108.14 ms | 16.09 ms | 184.75 tokens/sec |
| asynchronous@2.35 req/sec | 2.31 req/sec | 2.65 sec | 108.59 ms | 19.36 ms | 294.73 tokens/sec |
| asynchronous@3.24 req/sec | 3.15 req/sec | 3.71 sec | 114.42 ms | 28.19 ms | 402.45 tokens/sec |
| asynchronous@4.12 req/sec | 3.97 req/sec | 4.52 sec | 114.82 ms | 34.53 ms | 507.85 tokens/sec |
| asynchronous@5.01 req/sec | 4.78 req/sec | 5.75 sec | 118.33 ms | 43.94 ms | 610.24 tokens/sec |
| asynchronous@5.89 req/sec | 5.39 req/sec | 8.88 sec | 122.17 ms | 68.52 ms | 681.90 tokens/sec |
| asynchronous@7.66 req/sec | 5.51 req/sec | 31.94 sec | 415.83 ms | 246.32 ms | 704.34 tokens/sec |
| asynchronous@8.55 req/sec | 5.75 req/sec | 35.53 sec | 2904.71 ms | 255.38 ms | 733.39 tokens/sec |
| asynchronous@6.78 req/sec | 5.80 req/sec | 15.92 sec | 136.00 ms | 123.56 ms | 740.97 tokens/sec |
| throughput | 8.55 req/sec | 31.91 sec | 15748.22 ms | 126.71 ms | 1091.59 tokens/sec |

- **Qwen2-MoE-57B-A14B-Instruct**, **2**张**A100 80GB**, **vLLM**, prompt_tokens=512,generated_tokens=128

| Benchmark | Requests per Second | Request Latency | Time to First Token | Inter Token Latency | Output Token Throughput |
|---|---|---|---|---|---|
| asynchronous@1.27 req/sec | 0.00 req/sec | 0.00 sec | 0.00 ms | 0.00 ms | 0.00 tokens/sec |
| synchronous | 0.60 req/sec | 1.67 sec | 108.93 ms | 13.15 ms | 71.04 tokens/sec |
| asynchronous@2.60 req/sec | 2.44 req/sec | 5.73 sec | 954.26 ms | 42.14 ms | 298.70 tokens/sec |
| asynchronous@1.94 req/sec | 2.82 req/sec | 20.61 sec | 14455.79 ms | 52.86 ms | 329.48 tokens/sec |
| asynchronous@3.27 req/sec | 3.15 req/sec | 5.57 sec | 133.07 ms | 46.03 ms | 372.05 tokens/sec |
| asynchronous@3.94 req/sec | 3.72 req/sec | 6.10 sec | 134.91 ms | 51.34 ms | 432.50 tokens/sec |
| asynchronous@4.61 req/sec | 4.37 req/sec | 6.74 sec | 135.41 ms | 56.41 ms | 511.91 tokens/sec |
| asynchronous@5.28 req/sec | 4.99 req/sec | 7.68 sec | 168.68 ms | 64.06 ms | 585.06 tokens/sec |
| asynchronous@5.95 req/sec | 5.56 req/sec | 8.06 sec | 151.98 ms | 67.87 ms | 648.10 tokens/sec |
| asynchronous@6.61 req/sec | 6.21 req/sec | 8.89 sec | 224.21 ms | 73.20 ms | 735.18 tokens/sec |
| throughput | 6.61 req/sec | 12.94 sec | 7201.07 ms | 50.12 ms | 762.60 tokens/sec |

- **Qwen2-32B-Instruct**, **4**张**L20 48GB**, **vLLM**, prompt_tokens=512,generated_tokens=128

| Benchmark                 | Requests per Second | Request Latency | Time to First Token | Inter Token Latency | Output Token Throughput |
|---------------------------|---------------------|-----------------|---------------------|---------------------|-------------------------|
| synchronous               | 0.30 req/sec        | 3.29 sec        | 190.24 ms           | 24.25 ms            | 38.85 tokens/sec        |
| asynchronous@0.86 req/sec | 0.84 req/sec        | 3.90 sec        | 207.12 ms           | 29.77 ms            | 104.85 tokens/sec       |
| asynchronous@1.43 req/sec | 1.38 req/sec        | 4.70 sec        | 207.47 ms           | 35.32 ms            | 175.52 tokens/sec       |
| asynchronous@1.99 req/sec | 1.91 req/sec        | 6.22 sec        | 219.91 ms           | 48.09 ms            | 238.54 tokens/sec       |
| asynchronous@2.55 req/sec | 2.39 req/sec        | 7.94 sec        | 221.79 ms           | 61.28 ms            | 300.81 tokens/sec       |
| asynchronous@4.79 req/sec | 2.79 req/sec        | 42.14 sec       | 281.45 ms           | 337.31 ms           | 345.85 tokens/sec       |
| asynchronous@3.11 req/sec | 2.88 req/sec        | 9.11 sec        | 224.99 ms           | 70.44 ms            | 362.86 tokens/sec       |
| asynchronous@5.35 req/sec | 3.02 req/sec        | 50.71 sec       | 910.93 ms           | 399.45 ms           | 375.76 tokens/sec       |
| asynchronous@3.67 req/sec | 3.24 req/sec        | 13.15 sec       | 234.41 ms           | 103.08 ms           | 405.71 tokens/sec       |
| asynchronous@4.23 req/sec | 3.61 req/sec        | 18.50 sec       | 240.61 ms           | 146.15 ms           | 450.81 tokens/sec       |
| throughput                | 5.35 req/sec        | 33.59 sec       | 17327.73 ms         | 129.30 ms           | 674.89 tokens/sec       |

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
