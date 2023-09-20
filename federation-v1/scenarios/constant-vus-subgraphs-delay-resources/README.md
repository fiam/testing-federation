## Overview for: `federation-v1/constant-vus-subgraphs-delay-resources`


This scenario runs 4 subgraphs and a GraphQL gateway with Federation v1 spec, and runs a heavy query. It's being executed with a constant amount of VUs over a fixed amount of time. It measure things like memory usage, CPU usage, average RPS. It also includes a summary of the entire execution, and metrics information about HTTP execution times.


This scenario was running 500 VUs over 600s


### Comparison


**no-chart-available**


| Gateway             | RPS ⬇️ |         Requests         |          Duration          | Notes                                                                          |
| :------------------ | :----: | :----------------------: | :------------------------: | :----------------------------------------------------------------------------- |
| wundergraph         |  112   |  68076 total, 0 failed   |  avg: 3443ms, p95: 5855ms  | ✅                                                                              |
| apollo-router       |   99   |  60073 total, 0 failed   |  avg: 3482ms, p95: 6500ms  | ✅                                                                              |
| cosmo               |   97   |  58840 total, 0 failed   |  avg: 3915ms, p95: 6338ms  | ✅                                                                              |
| mesh-bun            |   66   |  40476 total, 0 failed   |  avg: 6979ms, p95: 9803ms  | ✅                                                                              |
| mesh-supergraph-bun |   65   |  39415 total, 0 failed   | avg: 7190ms, p95: 10150ms  | ✅                                                                              |
| mesh-supergraph     |   60   |  36922 total, 0 failed   |  avg: 8100ms, p95: 9031ms  | ✅                                                                              |
| apollo-server       |   46   | 28186 total, 2560 failed | avg: 10625ms, p95: 59994ms | ❌ 2560 failed requests, 2560 non-200 responses, 2560 unexpected GraphQL errors |
| mesh                |   38   |  23694 total, 0 failed   | avg: 12676ms, p95: 14523ms | ✅                                                                              |
| mercurius           |   11   |   7491 total, 0 failed   | avg: 40730ms, p95: 44163ms | ✅                                                                              |



<details>
  <summary>Summary for: `wundergraph`</summary>

  **K6 Output**




```
     ✓ response code was 200
     ✓ no graphql errors
     ✓ valid response structure

     checks.........................: 100.00% ✓ 204228     ✗ 0    
     data_received..................: 6.0 GB  9.9 MB/s
     data_sent......................: 81 MB   134 kB/s
     http_req_blocked...............: avg=2.89ms   min=1.1µs    med=3.1µs   max=4.92s  p(90)=4.8µs  p(95)=5.7µs  
     http_req_connecting............: avg=2.08ms   min=0s       med=0s      max=4.19s  p(90)=0s     p(95)=0s     
     http_req_duration..............: avg=3.44s    min=618.35ms med=3.41s   max=11.87s p(90)=5.03s  p(95)=5.85s  
       { expected_response:true }...: avg=3.44s    min=618.35ms med=3.41s   max=11.87s p(90)=5.03s  p(95)=5.85s  
     http_req_failed................: 0.00%   ✓ 0          ✗ 68076
     http_req_receiving.............: avg=638.84ms min=31.5µs   med=99.8µs  max=9.82s  p(90)=2.65s  p(95)=3.65s  
     http_req_sending...............: avg=49.88ms  min=5.8µs    med=16.59µs max=6.84s  p(90)=5.92ms p(95)=44.18ms
     http_req_tls_handshaking.......: avg=0s       min=0s       med=0s      max=0s     p(90)=0s     p(95)=0s     
     http_req_waiting...............: avg=2.75s    min=616.66ms med=2.87s   max=7.57s  p(90)=3.88s  p(95)=4.07s  
     http_reqs......................: 68076   112.964593/s
     iteration_duration.............: avg=4.41s    min=625.44ms med=3.96s   max=18.26s p(90)=7.14s  p(95)=8.22s  
     iterations.....................: 68076   112.964593/s
     vus............................: 211     min=211      max=500
     vus_max........................: 500     min=500      max=500
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

     checks.........................: 100.00% ✓ 180219   ✗ 0    
     data_received..................: 5.3 GB  8.7 MB/s
     data_sent......................: 71 MB   118 kB/s
     http_req_blocked...............: avg=6.65ms   min=1.3µs    med=3.3µs  max=7.25s  p(90)=5.2µs   p(95)=6.3µs   
     http_req_connecting............: avg=5.51ms   min=0s       med=0s     max=7.25s  p(90)=0s      p(95)=0s      
     http_req_duration..............: avg=3.48s    min=287.55ms med=3.39s  max=13.7s  p(90)=5.41s   p(95)=6.5s    
       { expected_response:true }...: avg=3.48s    min=287.55ms med=3.39s  max=13.7s  p(90)=5.41s   p(95)=6.5s    
     http_req_failed................: 0.00%   ✓ 0        ✗ 60073
     http_req_receiving.............: avg=770.62ms min=27.6µs   med=94.6µs max=12.12s p(90)=3.19s   p(95)=4.47s   
     http_req_sending...............: avg=79.12ms  min=5.9µs    med=16.7µs max=8.82s  p(90)=15.91ms p(95)=496.84ms
     http_req_tls_handshaking.......: avg=0s       min=0s       med=0s     max=0s     p(90)=0s      p(95)=0s      
     http_req_waiting...............: avg=2.63s    min=276.97ms med=2.76s  max=9.18s  p(90)=3.93s   p(95)=4.18s   
     http_reqs......................: 60073   99.71528/s
     iteration_duration.............: avg=4.99s    min=301.91ms med=4.45s  max=24.33s p(90)=8.51s   p(95)=9.77s   
     iterations.....................: 60073   99.71528/s
     vus............................: 217     min=217    max=500
     vus_max........................: 500     min=500    max=500
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

     checks.........................: 100.00% ✓ 176520    ✗ 0    
     data_received..................: 5.2 GB  8.6 MB/s
     data_sent......................: 70 MB   116 kB/s
     http_req_blocked...............: avg=1.95ms   min=1.1µs    med=3.1µs  max=3.99s  p(90)=4.8µs   p(95)=5.6µs   
     http_req_connecting............: avg=917.92µs min=0s       med=0s     max=3.99s  p(90)=0s      p(95)=0s      
     http_req_duration..............: avg=3.91s    min=982.04ms med=3.84s  max=12.19s p(90)=5.69s   p(95)=6.33s   
       { expected_response:true }...: avg=3.91s    min=982.04ms med=3.84s  max=12.19s p(90)=5.69s   p(95)=6.33s   
     http_req_failed................: 0.00%   ✓ 0         ✗ 58840
     http_req_receiving.............: avg=730.52ms min=29.8µs   med=97.5µs max=9.86s  p(90)=2.93s   p(95)=3.52s   
     http_req_sending...............: avg=70.31ms  min=5.7µs    med=17.2µs max=7.8s   p(90)=14.93ms p(95)=343.05ms
     http_req_tls_handshaking.......: avg=0s       min=0s       med=0s     max=0s     p(90)=0s      p(95)=0s      
     http_req_waiting...............: avg=3.11s    min=969.2ms  med=3.14s  max=7.82s  p(90)=4.24s   p(95)=4.47s   
     http_reqs......................: 58840   97.611198/s
     iteration_duration.............: avg=5.1s     min=989.73ms med=4.7s   max=24.46s p(90)=8.05s   p(95)=9.21s   
     iterations.....................: 58840   97.611198/s
     vus............................: 229     min=229     max=500
     vus_max........................: 500     min=500     max=500
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

     checks.........................: 100.00% ✓ 121428    ✗ 0    
     data_received..................: 3.6 GB  5.9 MB/s
     data_sent......................: 48 MB   79 kB/s
     http_req_blocked...............: avg=688.06µs min=1.1µs  med=3.1µs  max=2.45s   p(90)=4.7µs    p(95)=5.8µs  
     http_req_connecting............: avg=454.39µs min=0s     med=0s     max=66.66ms p(90)=0s       p(95)=0s     
     http_req_duration..............: avg=6.97s    min=2.67s  med=7.63s  max=12.98s  p(90)=9.45s    p(95)=9.8s   
       { expected_response:true }...: avg=6.97s    min=2.67s  med=7.63s  max=12.98s  p(90)=9.45s    p(95)=9.8s   
     http_req_failed................: 0.00%   ✓ 0         ✗ 40476
     http_req_receiving.............: avg=173.05ms min=36.1µs med=79.1µs max=5.52s   p(90)=622.95ms p(95)=1.27s  
     http_req_sending...............: avg=11.82ms  min=5.7µs  med=15.9µs max=2.16s   p(90)=172.09µs p(95)=16.83ms
     http_req_tls_handshaking.......: avg=0s       min=0s     med=0s     max=0s      p(90)=0s       p(95)=0s     
     http_req_waiting...............: avg=6.79s    min=2.54s  med=7.4s   max=11.14s  p(90)=9.13s    p(95)=9.48s  
     http_reqs......................: 40476   66.888054/s
     iteration_duration.............: avg=7.44s    min=2.69s  med=8s     max=17.08s  p(90)=10.1s    p(95)=10.54s 
     iterations.....................: 40476   66.888054/s
     vus............................: 63      min=63      max=500
     vus_max........................: 500     min=500     max=500
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

     checks.........................: 100.00% ✓ 118245    ✗ 0    
     data_received..................: 3.5 GB  5.7 MB/s
     data_sent......................: 47 MB   77 kB/s
     http_req_blocked...............: avg=756.99µs min=1.4µs   med=3.6µs   max=2.06s   p(90)=5.5µs    p(95)=6.6µs  
     http_req_connecting............: avg=387.99µs min=0s      med=0s      max=56.71ms p(90)=0s       p(95)=0s     
     http_req_duration..............: avg=7.18s    min=1.14s   med=7.58s   max=13.73s  p(90)=9.79s    p(95)=10.15s 
       { expected_response:true }...: avg=7.18s    min=1.14s   med=7.58s   max=13.73s  p(90)=9.79s    p(95)=10.15s 
     http_req_failed................: 0.00%   ✓ 0         ✗ 39415
     http_req_receiving.............: avg=173.97ms min=41.09µs med=94.9µs  max=4.62s   p(90)=727.71ms p(95)=1.12s  
     http_req_sending...............: avg=13.28ms  min=6.3µs   med=17.39µs max=2.47s   p(90)=501.7µs  p(95)=18.08ms
     http_req_tls_handshaking.......: avg=0s       min=0s      med=0s      max=0s      p(90)=0s       p(95)=0s     
     http_req_waiting...............: avg=7s       min=1.14s   med=7.4s    max=12.02s  p(90)=9.47s    p(95)=9.82s  
     http_reqs......................: 39415   65.118955/s
     iteration_duration.............: avg=7.64s    min=1.2s    med=8.01s   max=14.64s  p(90)=10.42s   p(95)=10.87s 
     iterations.....................: 39415   65.118955/s
     vus............................: 112     min=112     max=500
     vus_max........................: 500     min=500     max=500
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

     checks.........................: 100.00% ✓ 110766    ✗ 0    
     data_received..................: 3.2 GB  5.3 MB/s
     data_sent......................: 44 MB   72 kB/s
     http_req_blocked...............: avg=551.66µs min=1.2µs  med=3.3µs   max=529.52ms p(90)=4.8µs    p(95)=5.7µs  
     http_req_connecting............: avg=493.78µs min=0s     med=0s      max=78.78ms  p(90)=0s       p(95)=0s     
     http_req_duration..............: avg=8.1s     min=5.3s   med=8.07s   max=12.94s   p(90)=8.76s    p(95)=9.03s  
       { expected_response:true }...: avg=8.1s     min=5.3s   med=8.07s   max=12.94s   p(90)=8.76s    p(95)=9.03s  
     http_req_failed................: 0.00%   ✓ 0         ✗ 36922
     http_req_receiving.............: avg=7.55ms   min=34.4µs med=87.19µs max=1.72s    p(90)=1.1ms    p(95)=8.6ms  
     http_req_sending...............: avg=3.47ms   min=6.6µs  med=18.39µs max=1.11s    p(90)=109.38µs p(95)=13.27ms
     http_req_tls_handshaking.......: avg=0s       min=0s     med=0s      max=0s       p(90)=0s       p(95)=0s     
     http_req_waiting...............: avg=8.08s    min=5.3s   med=8.06s   max=12.93s   p(90)=8.75s    p(95)=9s     
     http_reqs......................: 36922   60.947747/s
     iteration_duration.............: avg=8.17s    min=5.48s  med=8.12s   max=13.02s   p(90)=8.87s    p(95)=9.18s  
     iterations.....................: 36922   60.947747/s
     vus............................: 122     min=122     max=500
     vus_max........................: 500     min=500     max=500
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
      ↳  90% — ✓ 25626 / ✗ 2560
     ✗ no graphql errors
      ↳  90% — ✓ 25626 / ✗ 2560
     ✓ valid response structure

     checks.........................: 93.75% ✓ 76878     ✗ 5120 
     data_received..................: 2.3 GB 3.7 MB/s
     data_sent......................: 34 MB  55 kB/s
     http_req_blocked...............: avg=7.65ms min=1.3µs med=3.3µs  max=1.18s    p(90)=108.1µs p(95)=28.28ms
     http_req_connecting............: avg=7.48ms min=0s    med=0s     max=1.18s    p(90)=0s      p(95)=27.78ms
     http_req_duration..............: avg=10.62s min=2.53s med=5.74s  max=1m1s     p(90)=7.95s   p(95)=59.99s 
       { expected_response:true }...: avg=5.69s  min=2.53s med=5.58s  max=59.62s   p(90)=6.9s    p(95)=7.24s  
     http_req_failed................: 9.08%  ✓ 2560      ✗ 25626
     http_req_receiving.............: avg=3.13ms min=0s    med=85.3µs max=549.52ms p(90)=357.3µs p(95)=1.12ms 
     http_req_sending...............: avg=3.98ms min=6.7µs med=19.3µs max=790.57ms p(90)=1.46ms  p(95)=15.02ms
     http_req_tls_handshaking.......: avg=0s     min=0s    med=0s     max=0s       p(90)=0s      p(95)=0s     
     http_req_waiting...............: avg=10.61s min=2.53s med=5.73s  max=1m1s     p(90)=7.95s   p(95)=59.99s 
     http_reqs......................: 28186  46.593408/s
     iteration_duration.............: avg=10.68s min=2.55s med=5.78s  max=1m1s     p(90)=8.08s   p(95)=1m0s   
     iterations.....................: 28186  46.593408/s
     vus............................: 28     min=28      max=500
     vus_max........................: 500    min=500     max=500
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

     checks.........................: 100.00% ✓ 71082     ✗ 0    
     data_received..................: 2.1 GB  3.4 MB/s
     data_sent......................: 28 MB   46 kB/s
     http_req_blocked...............: avg=1.51ms min=1.8µs  med=4.59µs  max=335.62ms p(90)=7.1µs   p(95)=13.73µs
     http_req_connecting............: avg=1.46ms min=0s     med=0s      max=140.87ms p(90)=0s      p(95)=0s     
     http_req_duration..............: avg=12.67s min=8.38s  med=12.65s  max=17.93s   p(90)=14.19s  p(95)=14.52s 
       { expected_response:true }...: avg=12.67s min=8.38s  med=12.65s  max=17.93s   p(90)=14.19s  p(95)=14.52s 
     http_req_failed................: 0.00%   ✓ 0         ✗ 23694
     http_req_receiving.............: avg=8.09ms min=50.1µs med=136.2µs max=1.8s     p(90)=2.28ms  p(95)=9.84ms 
     http_req_sending...............: avg=3.23ms min=9.7µs  med=26.9µs  max=869ms    p(90)=171.6µs p(95)=15.66ms
     http_req_tls_handshaking.......: avg=0s     min=0s     med=0s      max=0s       p(90)=0s      p(95)=0s     
     http_req_waiting...............: avg=12.66s min=8.38s  med=12.64s  max=17.74s   p(90)=14.19s  p(95)=14.5s  
     http_reqs......................: 23694   38.902248/s
     iteration_duration.............: avg=12.77s min=8.71s  med=12.76s  max=18.14s   p(90)=14.32s  p(95)=14.68s 
     iterations.....................: 23694   38.902248/s
     vus............................: 90      min=90      max=500
     vus_max........................: 500     min=500     max=500
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

     checks.........................: 100.00% ✓ 22473     ✗ 0    
     data_received..................: 658 MB  1.0 MB/s
     data_sent......................: 9.0 MB  14 kB/s
     http_req_blocked...............: avg=3.49ms   min=1.8µs  med=4.4µs   max=114.76ms p(90)=5.9µs   p(95)=30.94ms
     http_req_connecting............: avg=3.43ms   min=0s     med=0s      max=114.73ms p(90)=0s      p(95)=30.25ms
     http_req_duration..............: avg=40.72s   min=13.43s med=41.82s  max=47.1s    p(90)=43.06s  p(95)=44.16s 
       { expected_response:true }...: avg=40.72s   min=13.43s med=41.82s  max=47.1s    p(90)=43.06s  p(95)=44.16s 
     http_req_failed................: 0.00%   ✓ 0         ✗ 7491 
     http_req_receiving.............: avg=249.43µs min=55µs   med=116.2µs max=21.24ms  p(90)=309.8µs p(95)=401.3µs
     http_req_sending...............: avg=638.12µs min=10.2µs med=27.3µs  max=31.3ms   p(90)=45.2µs  p(95)=5.18ms 
     http_req_tls_handshaking.......: avg=0s       min=0s     med=0s      max=0s       p(90)=0s      p(95)=0s     
     http_req_waiting...............: avg=40.72s   min=13.43s med=41.82s  max=47.1s    p(90)=43.06s  p(95)=44.16s 
     http_reqs......................: 7491    11.890301/s
     iteration_duration.............: avg=40.74s   min=13.44s med=41.82s  max=47.11s   p(90)=43.07s  p(95)=44.17s 
     iterations.....................: 7491    11.890301/s
     vus............................: 120     min=120     max=500
     vus_max........................: 500     min=500     max=500
```


**Performance Overview**


**no-image-available**


**Subgraphs Overview**


**no-image-available**


**HTTP Overview**


**no-image-available**


  </details>