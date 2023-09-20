## Overview for: `federation-v1/constant-vus-subgraphs-delay`


This scenario runs 4 subgraphs and a GraphQL gateway with Federation v1 spec, and runs a heavy query. It's being executed with a constant amount of VUs over a fixed amount of time. It measure things like memory usage, CPU usage, average RPS. It also includes a summary of the entire execution, and metrics information about HTTP execution times.


This scenario was running 300 VUs over 600s


### Comparison


**no-chart-available**


| Gateway             | RPS ⬇️ |         Requests         |          Duration          | Notes                                                                          |
| :------------------ | :----: | :----------------------: | :------------------------: | :----------------------------------------------------------------------------- |
| wundergraph         |  113   |  68069 total, 0 failed   |  avg: 2185ms, p95: 3371ms  | ✅                                                                              |
| cosmo               |   72   |  43473 total, 0 failed   |  avg: 3022ms, p95: 4561ms  | ✅                                                                              |
| apollo-router       |   71   |  43378 total, 0 failed   |  avg: 2665ms, p95: 4727ms  | ✅                                                                              |
| mesh                |   59   |  36055 total, 0 failed   |  avg: 4959ms, p95: 5736ms  | ✅                                                                              |
| mesh-supergraph     |   59   |  36144 total, 0 failed   |  avg: 4950ms, p95: 5608ms  | ✅                                                                              |
| mesh-supergraph-bun |   46   |  28090 total, 0 failed   |  avg: 5912ms, p95: 8536ms  | ✅                                                                              |
| apollo-server       |   43   | 26430 total, 1150 failed |  avg: 6786ms, p95: 6314ms  | ❌ 1150 failed requests, 1150 non-200 responses, 1150 unexpected GraphQL errors |
| mesh-bun            |   42   |  25453 total, 0 failed   |  avg: 6630ms, p95: 9864ms  | ✅                                                                              |
| mercurius           |   12   |   7657 total, 0 failed   | avg: 23951ms, p95: 24881ms | ✅                                                                              |



<details>
  <summary>Summary for: `wundergraph`</summary>

  **K6 Output**




```
     ✓ response code was 200
     ✓ no graphql errors
     ✓ valid response structure

     checks.........................: 100.00% ✓ 204207     ✗ 0    
     data_received..................: 6.0 GB  9.9 MB/s
     data_sent......................: 81 MB   134 kB/s
     http_req_blocked...............: avg=534.34µs min=1.09µs   med=3.2µs    max=1.72s p(90)=4.89µs p(95)=5.6µs  
     http_req_connecting............: avg=263.02µs min=0s       med=0s       max=1.26s p(90)=0s     p(95)=0s     
     http_req_duration..............: avg=2.18s    min=699.89ms med=2.16s    max=6.2s  p(90)=3s     p(95)=3.37s  
       { expected_response:true }...: avg=2.18s    min=699.89ms med=2.16s    max=6.2s  p(90)=3s     p(95)=3.37s  
     http_req_failed................: 0.00%   ✓ 0          ✗ 68069
     http_req_receiving.............: avg=299.14ms min=30.3µs   med=102.19µs max=4.29s p(90)=1.32s  p(95)=1.64s  
     http_req_sending...............: avg=32.28ms  min=5.4µs    med=17.89µs  max=4.77s p(90)=5.82ms p(95)=31.11ms
     http_req_tls_handshaking.......: avg=0s       min=0s       med=0s       max=0s    p(90)=0s     p(95)=0s     
     http_req_waiting...............: avg=1.85s    min=699.83ms med=1.89s    max=4.54s p(90)=2.43s  p(95)=2.58s  
     http_reqs......................: 68069   113.114287/s
     iteration_duration.............: avg=2.64s    min=742.99ms med=2.46s    max=9.63s p(90)=3.99s  p(95)=4.57s  
     iterations.....................: 68069   113.114287/s
     vus............................: 133     min=133      max=300
     vus_max........................: 300     min=300      max=300
```


**Performance Overview**


**no-image-available**


**Subgraphs Overview**


**no-image-available**


**HTTP Overview**


**no-image-available**


  </details>

<details>
  <summary>Summary for: `cosmo`</summary>

  **K6 Output**




```
     ✓ response code was 200
     ✓ no graphql errors
     ✓ valid response structure

     checks.........................: 100.00% ✓ 130419    ✗ 0    
     data_received..................: 3.8 GB  6.3 MB/s
     data_sent......................: 52 MB   86 kB/s
     http_req_blocked...............: avg=1.42ms   min=1.7µs    med=3.9µs    max=2.94s  p(90)=6.5µs   p(95)=10.4µs  
     http_req_connecting............: avg=745µs    min=0s       med=0s       max=2.88s  p(90)=0s      p(95)=0s      
     http_req_duration..............: avg=3.02s    min=843.97ms med=2.92s    max=8.75s  p(90)=4.12s   p(95)=4.56s   
       { expected_response:true }...: avg=3.02s    min=843.97ms med=2.92s    max=8.75s  p(90)=4.12s   p(95)=4.56s   
     http_req_failed................: 0.00%   ✓ 0         ✗ 43473
     http_req_receiving.............: avg=353.82ms min=46.1µs   med=138.29µs max=7.34s  p(90)=1.53s   p(95)=2.35s   
     http_req_sending...............: avg=49.25ms  min=9.19µs   med=21.8µs   max=5.24s  p(90)=14.39ms p(95)=265.41ms
     http_req_tls_handshaking.......: avg=0s       min=0s       med=0s       max=0s     p(90)=0s      p(95)=0s      
     http_req_waiting...............: avg=2.61s    min=843.84ms med=2.61s    max=5.89s  p(90)=3.44s   p(95)=3.63s   
     http_reqs......................: 43473   72.166992/s
     iteration_duration.............: avg=4.14s    min=909.63ms med=4.03s    max=14.62s p(90)=6.11s   p(95)=6.78s   
     iterations.....................: 43473   72.166992/s
     vus............................: 103     min=103     max=300
     vus_max........................: 300     min=300     max=300
```


**Performance Overview**


**no-image-available**


**Subgraphs Overview**


**no-image-available**


**HTTP Overview**


**no-image-available**


  </details>

<details>
  <summary>Summary for: `apollo-router`</summary>

  **K6 Output**




```
     ✓ response code was 200
     ✓ no graphql errors
     ✓ valid response structure

     checks.........................: 100.00% ✓ 130134    ✗ 0    
     data_received..................: 3.8 GB  6.3 MB/s
     data_sent......................: 52 MB   85 kB/s
     http_req_blocked...............: avg=7.18ms  min=1.89µs   med=3.7µs    max=5.05s  p(90)=6.2µs  p(95)=9.9µs  
     http_req_connecting............: avg=5.85ms  min=0s       med=0s       max=4.6s   p(90)=0s     p(95)=0s     
     http_req_duration..............: avg=2.66s   min=338.32ms med=2.53s    max=10.54s p(90)=4.09s  p(95)=4.72s  
       { expected_response:true }...: avg=2.66s   min=338.32ms med=2.53s    max=10.54s p(90)=4.09s  p(95)=4.72s  
     http_req_failed................: 0.00%   ✓ 0         ✗ 43378
     http_req_receiving.............: avg=493.8ms min=44.59µs  med=118.99µs max=9.56s  p(90)=2.22s  p(95)=2.98s  
     http_req_sending...............: avg=52.79ms min=9.5µs    med=18µs     max=6.44s  p(90)=2.93ms p(95)=59.11ms
     http_req_tls_handshaking.......: avg=0s      min=0s       med=0s       max=0s     p(90)=0s     p(95)=0s     
     http_req_waiting...............: avg=2.11s   min=336.82ms med=2.13s    max=6.04s  p(90)=2.96s  p(95)=3.18s  
     http_reqs......................: 43378   71.982429/s
     iteration_duration.............: avg=4.15s   min=366.76ms med=4.01s    max=17.92s p(90)=6.71s  p(95)=7.81s  
     iterations.....................: 43378   71.982429/s
     vus............................: 136     min=136     max=300
     vus_max........................: 300     min=300     max=300
```


**Performance Overview**


**no-image-available**


**Subgraphs Overview**


**no-image-available**


**HTTP Overview**


**no-image-available**


  </details>

<details>
  <summary>Summary for: `mesh`</summary>

  **K6 Output**




```
     ✓ response code was 200
     ✓ no graphql errors
     ✓ valid response structure

     checks.........................: 100.00% ✓ 108165    ✗ 0    
     data_received..................: 3.2 GB  5.2 MB/s
     data_sent......................: 43 MB   71 kB/s
     http_req_blocked...............: avg=84.39µs min=1.29µs  med=3.1µs   max=112.03ms p(90)=4.4µs   p(95)=5.1µs  
     http_req_connecting............: avg=69.19µs min=0s      med=0s      max=19.59ms  p(90)=0s      p(95)=0s     
     http_req_duration..............: avg=4.95s   min=3.17s   med=4.94s   max=8.97s    p(90)=5.56s   p(95)=5.73s  
       { expected_response:true }...: avg=4.95s   min=3.17s   med=4.94s   max=8.97s    p(90)=5.56s   p(95)=5.73s  
     http_req_failed................: 0.00%   ✓ 0         ✗ 36055
     http_req_receiving.............: avg=8.34ms  min=36.59µs med=82.49µs max=2.28s    p(90)=1.18ms  p(95)=11.63ms
     http_req_sending...............: avg=2.61ms  min=6.6µs   med=17µs    max=1.75s    p(90)=57.47µs p(95)=11.96ms
     http_req_tls_handshaking.......: avg=0s      min=0s      med=0s      max=0s       p(90)=0s      p(95)=0s     
     http_req_waiting...............: avg=4.94s   min=3.16s   med=4.93s   max=8.33s    p(90)=5.55s   p(95)=5.71s  
     http_reqs......................: 36055   59.727065/s
     iteration_duration.............: avg=5s      min=3.18s   med=4.99s   max=9.05s    p(90)=5.63s   p(95)=5.82s  
     iterations.....................: 36055   59.727065/s
     vus............................: 84      min=84      max=300
     vus_max........................: 300     min=300     max=300
```


**Performance Overview**


**no-image-available**


**Subgraphs Overview**


**no-image-available**


**HTTP Overview**


**no-image-available**


  </details>

<details>
  <summary>Summary for: `mesh-supergraph`</summary>

  **K6 Output**




```
     ✓ response code was 200
     ✓ no graphql errors
     ✓ valid response structure

     checks.........................: 100.00% ✓ 108432    ✗ 0    
     data_received..................: 3.2 GB  5.3 MB/s
     data_sent......................: 43 MB   71 kB/s
     http_req_blocked...............: avg=553.4µs  min=1.1µs  med=3.8µs  max=442.68ms p(90)=5.1µs    p(95)=5.8µs  
     http_req_connecting............: avg=508.02µs min=0s     med=0s     max=135.53ms p(90)=0s       p(95)=0s     
     http_req_duration..............: avg=4.95s    min=3.16s  med=4.94s  max=7.98s    p(90)=5.45s    p(95)=5.6s   
       { expected_response:true }...: avg=4.95s    min=3.16s  med=4.94s  max=7.98s    p(90)=5.45s    p(95)=5.6s   
     http_req_failed................: 0.00%   ✓ 0         ✗ 36144
     http_req_receiving.............: avg=5.66ms   min=40.2µs med=95.4µs max=1.14s    p(90)=1.36ms   p(95)=9.9ms  
     http_req_sending...............: avg=2.39ms   min=5.6µs  med=21.3µs max=616.42ms p(90)=106.89µs p(95)=11.61ms
     http_req_tls_handshaking.......: avg=0s       min=0s     med=0s     max=0s       p(90)=0s       p(95)=0s     
     http_req_waiting...............: avg=4.94s    min=3.16s  med=4.93s  max=7.42s    p(90)=5.44s    p(95)=5.59s  
     http_reqs......................: 36144   59.856553/s
     iteration_duration.............: avg=4.99s    min=3.19s  med=4.98s  max=8.06s    p(90)=5.51s    p(95)=5.69s  
     iterations.....................: 36144   59.856553/s
     vus............................: 96      min=96      max=300
     vus_max........................: 300     min=300     max=300
```


**Performance Overview**


**no-image-available**


**Subgraphs Overview**


**no-image-available**


**HTTP Overview**


**no-image-available**


  </details>

<details>
  <summary>Summary for: `mesh-supergraph-bun`</summary>

  **K6 Output**




```
     ✓ response code was 200
     ✓ no graphql errors
     ✓ valid response structure

     checks.........................: 100.00% ✓ 84270     ✗ 0    
     data_received..................: 2.5 GB  4.1 MB/s
     data_sent......................: 33 MB   55 kB/s
     http_req_blocked...............: avg=1.74ms  min=1.8µs  med=3.7µs   max=747.61ms p(90)=6µs      p(95)=10.4µs  
     http_req_connecting............: avg=1.57ms  min=0s     med=0s      max=256.47ms p(90)=0s       p(95)=0s      
     http_req_duration..............: avg=5.91s   min=1.22s  med=6.05s   max=11.25s   p(90)=8.07s    p(95)=8.53s   
       { expected_response:true }...: avg=5.91s   min=1.22s  med=6.05s   max=11.25s   p(90)=8.07s    p(95)=8.53s   
     http_req_failed................: 0.00%   ✓ 0         ✗ 28090
     http_req_receiving.............: avg=99.21ms min=54.5µs med=109.6µs max=4.2s     p(90)=308.94ms p(95)=746.43ms
     http_req_sending...............: avg=12.61ms min=10.8µs med=18.39µs max=3.49s    p(90)=5.79ms   p(95)=31.42ms 
     http_req_tls_handshaking.......: avg=0s      min=0s     med=0s      max=0s       p(90)=0s       p(95)=0s      
     http_req_waiting...............: avg=5.8s    min=1.22s  med=5.92s   max=10.64s   p(90)=7.91s    p(95)=8.36s   
     http_reqs......................: 28090   46.389351/s
     iteration_duration.............: avg=6.44s   min=1.4s   med=6.54s   max=17.93s   p(90)=8.86s    p(95)=9.41s   
     iterations.....................: 28090   46.389351/s
     vus............................: 68      min=68      max=300
     vus_max........................: 300     min=300     max=300
```


**Performance Overview**


**no-image-available**


**Subgraphs Overview**


**no-image-available**


**HTTP Overview**


**no-image-available**


  </details>

<details>
  <summary>Summary for: `apollo-server`</summary>

  **K6 Output**




```
     ✗ response code was 200
      ↳  95% — ✓ 25280 / ✗ 1150
     ✗ no graphql errors
      ↳  95% — ✓ 25280 / ✗ 1150
     ✓ valid response structure

     checks.........................: 97.05% ✓ 75840     ✗ 2300 
     data_received..................: 2.2 GB 3.7 MB/s
     data_sent......................: 31 MB  52 kB/s
     http_req_blocked...............: avg=1.98ms min=1.3µs    med=3.6µs   max=447.59ms p(90)=5.2µs    p(95)=113.26µs
     http_req_connecting............: avg=1.9ms  min=0s       med=0s      max=412.77ms p(90)=0s       p(95)=57.9µs  
     http_req_duration..............: avg=6.78s  min=971.73ms med=4.39s   max=1m0s     p(90)=5.39s    p(95)=6.31s   
       { expected_response:true }...: avg=4.36s  min=971.73ms med=4.33s   max=59.23s   p(90)=5.22s    p(95)=5.44s   
     http_req_failed................: 4.35%  ✓ 1150      ✗ 25280
     http_req_receiving.............: avg=2.77ms min=0s       med=94.89µs max=502.69ms p(90)=382.95µs p(95)=1.25ms  
     http_req_sending...............: avg=2.14ms min=7.2µs    med=20.8µs  max=586.95ms p(90)=131.7µs  p(95)=7.23ms  
     http_req_tls_handshaking.......: avg=0s     min=0s       med=0s      max=0s       p(90)=0s       p(95)=0s      
     http_req_waiting...............: avg=6.78s  min=970.85ms med=4.38s   max=1m0s     p(90)=5.38s    p(95)=6.31s   
     http_reqs......................: 26430  43.834158/s
     iteration_duration.............: avg=6.82s  min=995.42ms med=4.42s   max=1m0s     p(90)=5.46s    p(95)=6.42s   
     iterations.....................: 26430  43.834158/s
     vus............................: 9      min=9       max=300
     vus_max........................: 300    min=300     max=300
```


**Performance Overview**


**no-image-available**


**Subgraphs Overview**


**no-image-available**


**HTTP Overview**


**no-image-available**


  </details>

<details>
  <summary>Summary for: `mesh-bun`</summary>

  **K6 Output**




```
     ✓ response code was 200
     ✓ no graphql errors
     ✓ valid response structure

     checks.........................: 100.00% ✓ 76359     ✗ 0    
     data_received..................: 2.2 GB  3.7 MB/s
     data_sent......................: 30 MB   50 kB/s
     http_req_blocked...............: avg=508.26µs min=2.1µs  med=4.5µs   max=963.66ms p(90)=7.2µs    p(95)=12.7µs  
     http_req_connecting............: avg=236.78µs min=0s     med=0s      max=33.88ms  p(90)=0s       p(95)=0s      
     http_req_duration..............: avg=6.63s    min=2.43s  med=6.3s    max=16.52s   p(90)=9.46s    p(95)=9.86s   
       { expected_response:true }...: avg=6.63s    min=2.43s  med=6.3s    max=16.52s   p(90)=9.46s    p(95)=9.86s   
     http_req_failed................: 0.00%   ✓ 0         ✗ 25453
     http_req_receiving.............: avg=102.47ms min=53.3µs med=125.4µs max=4.04s    p(90)=336.79ms p(95)=801.85ms
     http_req_sending...............: avg=11.18ms  min=10.1µs med=24.29µs max=1.79s    p(90)=2.62ms   p(95)=25.51ms 
     http_req_tls_handshaking.......: avg=0s       min=0s     med=0s      max=0s       p(90)=0s       p(95)=0s      
     http_req_waiting...............: avg=6.51s    min=2.43s  med=6.09s   max=16.31s   p(90)=9.27s    p(95)=9.69s   
     http_reqs......................: 25453   42.040584/s
     iteration_duration.............: avg=7.1s     min=2.66s  med=6.92s   max=16.59s   p(90)=10.09s   p(95)=10.53s  
     iterations.....................: 25453   42.040584/s
     vus............................: 86      min=86      max=300
     vus_max........................: 300     min=300     max=300
```


**Performance Overview**


**no-image-available**


**Subgraphs Overview**


**no-image-available**


**HTTP Overview**


**no-image-available**


  </details>

<details>
  <summary>Summary for: `mercurius`</summary>

  **K6 Output**




```
     ✓ response code was 200
     ✓ no graphql errors
     ✓ valid response structure

     checks.........................: 100.00% ✓ 22971     ✗ 0    
     data_received..................: 672 MB  1.1 MB/s
     data_sent......................: 9.1 MB  15 kB/s
     http_req_blocked...............: avg=1.71ms   min=2.1µs  med=3.9µs   max=82.5ms  p(90)=5.3µs   p(95)=6.9µs   
     http_req_connecting............: avg=1.68ms   min=0s     med=0s      max=76.59ms p(90)=0s      p(95)=0s      
     http_req_duration..............: avg=23.95s   min=7.77s  med=24.38s  max=26.94s  p(90)=24.71s  p(95)=24.88s  
       { expected_response:true }...: avg=23.95s   min=7.77s  med=24.38s  max=26.94s  p(90)=24.71s  p(95)=24.88s  
     http_req_failed................: 0.00%   ✓ 0         ✗ 7657 
     http_req_receiving.............: avg=221.11µs min=48.8µs med=113.5µs max=49.15ms p(90)=290.9µs p(95)=396.44µs
     http_req_sending...............: avg=562.8µs  min=9.29µs med=24.7µs  max=53.96ms p(90)=33.1µs  p(95)=699.82µs
     http_req_tls_handshaking.......: avg=0s       min=0s     med=0s      max=0s      p(90)=0s      p(95)=0s      
     http_req_waiting...............: avg=23.95s   min=7.77s  med=24.38s  max=26.94s  p(90)=24.71s  p(95)=24.88s  
     http_reqs......................: 7657    12.289661/s
     iteration_duration.............: avg=23.96s   min=7.78s  med=24.39s  max=26.94s  p(90)=24.72s  p(95)=24.89s  
     iterations.....................: 7657    12.289661/s
     vus............................: 4       min=4       max=300
     vus_max........................: 300     min=300     max=300
```


**Performance Overview**


**no-image-available**


**Subgraphs Overview**


**no-image-available**


**HTTP Overview**


**no-image-available**


  </details>