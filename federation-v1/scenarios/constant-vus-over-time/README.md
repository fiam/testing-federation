## Overview for: `federation-v1/constant-vus-over-time`


This scenario runs 4 subgraphs and a GraphQL gateway with Federation v1 spec, and runs a heavy query. It's being executed with a constant amount of VUs over a fixed amount of time. It measure things like memory usage, CPU usage, average RPS. It also includes a summary of the entire execution, and metrics information about HTTP execution times.


This scenario was running 300 VUs over 600s


### Comparison


**no-chart-available**


| Gateway              | RPS ⬇️ |         Requests         |         Duration          | Notes                                                                          |
| :------------------- | :----: | :----------------------: | :-----------------------: | :----------------------------------------------------------------------------- |
| apollo-router        |   97   |  58611 total, 0 failed   | avg: 2063ms, p95: 4359ms  | ✅                                                                              |
| wundergraph          |   86   |  51939 total, 0 failed   | avg: 2165ms, p95: 4317ms  | ✅                                                                              |
| cosmo                |   73   |  44402 total, 0 failed   | avg: 2504ms, p95: 4840ms  | ✅                                                                              |
| mesh-supergraph-bun  |   72   |  43669 total, 0 failed   | avg: 3812ms, p95: 5379ms  | ✅                                                                              |
| mesh-bun             |   46   |  27842 total, 0 failed   | avg: 5995ms, p95: 8483ms  | ✅                                                                              |
| mesh-supergraph      |   44   |  27136 total, 0 failed   | avg: 6563ms, p95: 8099ms  | ✅                                                                              |
| apollo-server        |   43   | 26171 total, 1490 failed | avg: 6854ms, p95: 59940ms | ❌ 1490 failed requests, 1490 non-200 responses, 1490 unexpected GraphQL errors |
| mesh                 |   41   |  25085 total, 0 failed   | avg: 7109ms, p95: 8505ms  | ✅                                                                              |
| apollo-server-node16 |   33   |  20527 total, 0 failed   | avg: 8739ms, p95: 12552ms | ✅                                                                              |
| mercurius            |   30   |  18539 total, 0 failed   | avg: 9721ms, p95: 10217ms | ✅                                                                              |



<details>
  <summary>Summary for: `apollo-router`</summary>

  **K6 Output**




```
     ✓ response code was 200
     ✓ no graphql errors
     ✓ valid response structure

     checks.........................: 100.00% ✓ 175833    ✗ 0    
     data_received..................: 5.1 GB  8.5 MB/s
     data_sent......................: 70 MB   116 kB/s
     http_req_blocked...............: avg=5.49ms   min=1µs     med=3.6µs   max=5.32s  p(90)=5.2µs   p(95)=6µs     
     http_req_connecting............: avg=4.59ms   min=0s      med=0s      max=3.98s  p(90)=0s      p(95)=0s      
     http_req_duration..............: avg=2.06s    min=18.57ms med=1.9s    max=10.35s p(90)=3.75s   p(95)=4.35s   
       { expected_response:true }...: avg=2.06s    min=18.57ms med=1.9s    max=10.35s p(90)=3.75s   p(95)=4.35s   
     http_req_failed................: 0.00%   ✓ 0         ✗ 58611
     http_req_receiving.............: avg=645.71ms min=27.7µs  med=91.8µs  max=9.71s  p(90)=2.46s   p(95)=3.32s   
     http_req_sending...............: avg=62.46ms  min=5.5µs   med=19.09µs max=5.25s  p(90)=15.42ms p(95)=307.91ms
     http_req_tls_handshaking.......: avg=0s       min=0s      med=0s      max=0s     p(90)=0s      p(95)=0s      
     http_req_waiting...............: avg=1.35s    min=14.44ms med=1.3s    max=4.61s  p(90)=2.28s   p(95)=2.5s    
     http_reqs......................: 58611   97.447194/s
     iteration_duration.............: avg=3.06s    min=26.53ms med=2.72s   max=15.62s p(90)=5.71s   p(95)=6.7s    
     iterations.....................: 58611   97.447194/s
     vus............................: 130     min=130     max=300
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
  <summary>Summary for: `wundergraph`</summary>

  **K6 Output**




```
     ✓ response code was 200
     ✓ no graphql errors
     ✓ valid response structure

     checks.........................: 100.00% ✓ 155817    ✗ 0    
     data_received..................: 4.6 GB  7.6 MB/s
     data_sent......................: 62 MB   103 kB/s
     http_req_blocked...............: avg=6.47ms   min=1.2µs   med=4.7µs   max=5.43s  p(90)=7µs    p(95)=8.4µs  
     http_req_connecting............: avg=5.08ms   min=0s      med=0s      max=4.62s  p(90)=0s     p(95)=0s     
     http_req_duration..............: avg=2.16s    min=16.3ms  med=2.04s   max=11.62s p(90)=3.69s  p(95)=4.31s  
       { expected_response:true }...: avg=2.16s    min=16.3ms  med=2.04s   max=11.62s p(90)=3.69s  p(95)=4.31s  
     http_req_failed................: 0.00%   ✓ 0         ✗ 51939
     http_req_receiving.............: avg=567.53ms min=36.4µs  med=121.7µs max=8.17s  p(90)=2.31s  p(95)=3.06s  
     http_req_sending...............: avg=51.27ms  min=5.9µs   med=23.8µs  max=7.99s  p(90)=9.33ms p(95)=53.94ms
     http_req_tls_handshaking.......: avg=0s       min=0s      med=0s      max=0s     p(90)=0s     p(95)=0s     
     http_req_waiting...............: avg=1.54s    min=16.1ms  med=1.54s   max=6.01s  p(90)=2.51s  p(95)=2.77s  
     http_reqs......................: 51939   86.354047/s
     iteration_duration.............: avg=3.45s    min=24.98ms med=3.17s   max=15.56s p(90)=6.16s  p(95)=7.19s  
     iterations.....................: 51939   86.354047/s
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
  <summary>Summary for: `cosmo`</summary>

  **K6 Output**




```
     ✓ response code was 200
     ✓ no graphql errors
     ✓ valid response structure

     checks.........................: 100.00% ✓ 133206    ✗ 0    
     data_received..................: 3.9 GB  6.5 MB/s
     data_sent......................: 53 MB   88 kB/s
     http_req_blocked...............: avg=6.1ms   min=1.6µs   med=3.7µs  max=5.21s  p(90)=5.8µs  p(95)=7.1µs  
     http_req_connecting............: avg=5.36ms  min=0s      med=0s     max=5.21s  p(90)=0s     p(95)=0s     
     http_req_duration..............: avg=2.5s    min=28.07ms med=2.3s   max=10.61s p(90)=4.26s  p(95)=4.84s  
       { expected_response:true }...: avg=2.5s    min=28.07ms med=2.3s   max=10.61s p(90)=4.26s  p(95)=4.84s  
     http_req_failed................: 0.00%   ✓ 0         ✗ 44402
     http_req_receiving.............: avg=747ms   min=35µs    med=114µs  max=7.48s  p(90)=2.81s  p(95)=3.48s  
     http_req_sending...............: avg=44.37ms min=6.8µs   med=19.5µs max=6.35s  p(90)=3.55ms p(95)=36.45ms
     http_req_tls_handshaking.......: avg=0s      min=0s      med=0s     max=0s     p(90)=0s     p(95)=0s     
     http_req_waiting...............: avg=1.71s   min=24.18ms med=1.69s  max=6.13s  p(90)=2.65s  p(95)=2.98s  
     http_reqs......................: 44402   73.791046/s
     iteration_duration.............: avg=4.05s   min=44.13ms med=3.87s  max=18.26s p(90)=6.99s  p(95)=8.1s   
     iterations.....................: 44402   73.791046/s
     vus............................: 25      min=25      max=300
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

     checks.........................: 100.00% ✓ 131007    ✗ 0    
     data_received..................: 3.8 GB  6.4 MB/s
     data_sent......................: 52 MB   86 kB/s
     http_req_blocked...............: avg=464.43µs min=1.4µs    med=3.4µs  max=1.39s   p(90)=5.2µs    p(95)=6.2µs   
     http_req_connecting............: avg=191.06µs min=0s       med=0s     max=41.15ms p(90)=0s       p(95)=0s      
     http_req_duration..............: avg=3.81s    min=720.27ms med=4.03s  max=8.13s   p(90)=5.1s     p(95)=5.37s   
       { expected_response:true }...: avg=3.81s    min=720.27ms med=4.03s  max=8.13s   p(90)=5.1s     p(95)=5.37s   
     http_req_failed................: 0.00%   ✓ 0         ✗ 43669
     http_req_receiving.............: avg=124.19ms min=42.1µs   med=94.9µs max=3.35s   p(90)=518.56ms p(95)=796.74ms
     http_req_sending...............: avg=15.91ms  min=7.3µs    med=18.5µs max=2.53s   p(90)=6.28ms   p(95)=53.54ms 
     http_req_tls_handshaking.......: avg=0s       min=0s       med=0s     max=0s      p(90)=0s       p(95)=0s      
     http_req_waiting...............: avg=3.67s    min=720.2ms  med=3.89s  max=6.77s   p(90)=4.86s    p(95)=5.05s   
     http_reqs......................: 43669   72.419892/s
     iteration_duration.............: avg=4.13s    min=773.05ms med=4.33s  max=11.39s  p(90)=5.53s    p(95)=5.87s   
     iterations.....................: 43669   72.419892/s
     vus............................: 18      min=18      max=300
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
  <summary>Summary for: `mesh-bun`</summary>

  **K6 Output**




```
     ✓ response code was 200
     ✓ no graphql errors
     ✓ valid response structure

     checks.........................: 100.00% ✓ 83526     ✗ 0    
     data_received..................: 2.4 GB  4.0 MB/s
     data_sent......................: 33 MB   55 kB/s
     http_req_blocked...............: avg=677.66µs min=1.7µs   med=3.7µs    max=890.84ms p(90)=6.5µs    p(95)=11.6µs  
     http_req_connecting............: avg=494.02µs min=0s      med=0s       max=87.01ms  p(90)=0s       p(95)=0s      
     http_req_duration..............: avg=5.99s    min=2.48s   med=6.68s    max=12.38s   p(90)=8.01s    p(95)=8.48s   
       { expected_response:true }...: avg=5.99s    min=2.48s   med=6.68s    max=12.38s   p(90)=8.01s    p(95)=8.48s   
     http_req_failed................: 0.00%   ✓ 0         ✗ 27842
     http_req_receiving.............: avg=110.78ms min=51.69µs med=118.29µs max=3.43s    p(90)=435.02ms p(95)=851.24ms
     http_req_sending...............: avg=12.12ms  min=8.5µs   med=19.3µs   max=2.53s    p(90)=1.57ms   p(95)=26.38ms 
     http_req_tls_handshaking.......: avg=0s       min=0s      med=0s       max=0s       p(90)=0s       p(95)=0s      
     http_req_waiting...............: avg=5.87s    min=2.48s   med=6.51s    max=11.86s   p(90)=7.8s     p(95)=8.28s   
     http_reqs......................: 27842   46.055081/s
     iteration_duration.............: avg=6.48s    min=2.5s    med=7.1s     max=12.66s   p(90)=8.78s    p(95)=9.18s   
     iterations.....................: 27842   46.055081/s
     vus............................: 52      min=52      max=300
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

     checks.........................: 100.00% ✓ 81408     ✗ 0    
     data_received..................: 2.4 GB  3.9 MB/s
     data_sent......................: 32 MB   53 kB/s
     http_req_blocked...............: avg=360.64µs min=1.3µs  med=3.4µs   max=214.99ms p(90)=6.1µs   p(95)=10.6µs 
     http_req_connecting............: avg=326.89µs min=0s     med=0s      max=47.9ms   p(90)=0s      p(95)=0s     
     http_req_duration..............: avg=6.56s    min=3.38s  med=6.51s   max=11.33s   p(90)=7.78s   p(95)=8.09s  
       { expected_response:true }...: avg=6.56s    min=3.38s  med=6.51s   max=11.33s   p(90)=7.78s   p(95)=8.09s  
     http_req_failed................: 0.00%   ✓ 0         ✗ 27136
     http_req_receiving.............: avg=10.71ms  min=48.3µs med=113.9µs max=2.11s    p(90)=3.31ms  p(95)=20.68ms
     http_req_sending...............: avg=3.45ms   min=9µs    med=19.59µs max=1.31s    p(90)=151.2µs p(95)=13.56ms
     http_req_tls_handshaking.......: avg=0s       min=0s     med=0s      max=0s       p(90)=0s      p(95)=0s     
     http_req_waiting...............: avg=6.54s    min=3.38s  med=6.5s    max=11.32s   p(90)=7.76s   p(95)=8.07s  
     http_reqs......................: 27136   44.901312/s
     iteration_duration.............: avg=6.65s    min=3.53s  med=6.59s   max=11.36s   p(90)=7.89s   p(95)=8.26s  
     iterations.....................: 27136   44.901312/s
     vus............................: 26      min=26      max=300
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
      ↳  94% — ✓ 24681 / ✗ 1490
     ✗ no graphql errors
      ↳  94% — ✓ 24681 / ✗ 1490
     ✓ valid response structure

     checks.........................: 96.13% ✓ 74043     ✗ 2980 
     data_received..................: 2.2 GB 3.6 MB/s
     data_sent......................: 31 MB  52 kB/s
     http_req_blocked...............: avg=2.1ms    min=1.3µs    med=3.1µs  max=433.91ms p(90)=8.3µs    p(95)=1.38ms  
     http_req_connecting............: avg=1.98ms   min=0s       med=0s     max=392.58ms p(90)=0s       p(95)=883.44µs
     http_req_duration..............: avg=6.85s    min=577.98ms med=3.54s  max=1m0s     p(90)=4.41s    p(95)=59.93s  
       { expected_response:true }...: avg=3.64s    min=577.98ms med=3.49s  max=58.95s   p(90)=4.14s    p(95)=4.38s   
     http_req_failed................: 5.69%  ✓ 1490      ✗ 24681
     http_req_receiving.............: avg=853.15µs min=0s       med=85.9µs max=241.43ms p(90)=329.61µs p(95)=741.98µs
     http_req_sending...............: avg=1.8ms    min=6.8µs    med=19.3µs max=271.89ms p(90)=186.3µs  p(95)=8.79ms  
     http_req_tls_handshaking.......: avg=0s       min=0s       med=0s     max=0s       p(90)=0s       p(95)=0s      
     http_req_waiting...............: avg=6.85s    min=577.85ms med=3.53s  max=1m0s     p(90)=4.41s    p(95)=59.92s  
     http_reqs......................: 26171  43.417545/s
     iteration_duration.............: avg=6.89s    min=585.39ms med=3.58s  max=1m0s     p(90)=4.46s    p(95)=1m0s    
     iterations.....................: 26171  43.417545/s
     vus............................: 72     min=72      max=300
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
  <summary>Summary for: `mesh`</summary>

  **K6 Output**




```
     ✓ response code was 200
     ✓ no graphql errors
     ✓ valid response structure

     checks.........................: 100.00% ✓ 75255     ✗ 0    
     data_received..................: 2.2 GB  3.6 MB/s
     data_sent......................: 30 MB   49 kB/s
     http_req_blocked...............: avg=211.48µs min=1.8µs  med=4.3µs   max=309.38ms p(90)=6.8µs    p(95)=12.07µs
     http_req_connecting............: avg=163.46µs min=0s     med=0s      max=27.95ms  p(90)=0s       p(95)=0s     
     http_req_duration..............: avg=7.1s     min=3.9s   med=7.09s   max=12.19s   p(90)=8.18s    p(95)=8.5s   
       { expected_response:true }...: avg=7.1s     min=3.9s   med=7.09s   max=12.19s   p(90)=8.18s    p(95)=8.5s   
     http_req_failed................: 0.00%   ✓ 0         ✗ 25085
     http_req_receiving.............: avg=10.76ms  min=53.7µs med=129.5µs max=2.17s    p(90)=3.32ms   p(95)=21.41ms
     http_req_sending...............: avg=3.92ms   min=9.79µs med=25.2µs  max=1.03s    p(90)=218.01µs p(95)=17.33ms
     http_req_tls_handshaking.......: avg=0s       min=0s     med=0s      max=0s       p(90)=0s       p(95)=0s     
     http_req_waiting...............: avg=7.09s    min=3.9s   med=7.07s   max=12.02s   p(90)=8.17s    p(95)=8.48s  
     http_reqs......................: 25085   41.451099/s
     iteration_duration.............: avg=7.21s    min=3.97s  med=7.19s   max=12.23s   p(90)=8.31s    p(95)=8.66s  
     iterations.....................: 25085   41.451099/s
     vus............................: 88      min=88      max=300
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
  <summary>Summary for: `apollo-server-node16`</summary>

  **K6 Output**




```
     ✓ response code was 200
     ✓ no graphql errors
     ✓ valid response structure

     checks.........................: 100.00% ✓ 61581     ✗ 0    
     data_received..................: 1.8 GB  3.0 MB/s
     data_sent......................: 24 MB   40 kB/s
     http_req_blocked...............: avg=1ms      min=1.7µs    med=4.4µs   max=148.3ms  p(90)=6.3µs    p(95)=7.6µs  
     http_req_connecting............: avg=946.42µs min=0s       med=0s      max=119.23ms p(90)=0s       p(95)=0s     
     http_req_duration..............: avg=8.73s    min=478.69ms med=8.27s   max=19.23s   p(90)=11.55s   p(95)=12.55s 
       { expected_response:true }...: avg=8.73s    min=478.69ms med=8.27s   max=19.23s   p(90)=11.55s   p(95)=12.55s 
     http_req_failed................: 0.00%   ✓ 0         ✗ 20527
     http_req_receiving.............: avg=10.24ms  min=51.8µs   med=107.2µs max=1.9s     p(90)=622.9µs  p(95)=6.12ms 
     http_req_sending...............: avg=2.95ms   min=8.4µs    med=23.4µs  max=798.68ms p(90)=145.34µs p(95)=12.67ms
     http_req_tls_handshaking.......: avg=0s       min=0s       med=0s      max=0s       p(90)=0s       p(95)=0s     
     http_req_waiting...............: avg=8.72s    min=478.58ms med=8.26s   max=19.23s   p(90)=11.51s   p(95)=12.47s 
     http_reqs......................: 20527   33.875328/s
     iteration_duration.............: avg=8.81s    min=490.96ms med=8.33s   max=19.47s   p(90)=11.73s   p(95)=12.68s 
     iterations.....................: 20527   33.875328/s
     vus............................: 15      min=15      max=300
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

     checks.........................: 100.00% ✓ 55617    ✗ 0    
     data_received..................: 1.6 GB  2.7 MB/s
     data_sent......................: 22 MB   37 kB/s
     http_req_blocked...............: avg=620.7µs  min=1.5µs  med=4µs     max=66.49ms  p(90)=5.4µs    p(95)=6.2µs   
     http_req_connecting............: avg=603.52µs min=0s     med=0s      max=66.47ms  p(90)=0s       p(95)=0s      
     http_req_duration..............: avg=9.72s    min=1.22s  med=9.8s    max=20.1s    p(90)=10.08s   p(95)=10.21s  
       { expected_response:true }...: avg=9.72s    min=1.22s  med=9.8s    max=20.1s    p(90)=10.08s   p(95)=10.21s  
     http_req_failed................: 0.00%   ✓ 0        ✗ 18539
     http_req_receiving.............: avg=1.1ms    min=48.4µs med=113.8µs max=597.75ms p(90)=369.84µs p(95)=503.21µs
     http_req_sending...............: avg=386.73µs min=8µs    med=21.9µs  max=91.35ms  p(90)=34.2µs   p(95)=122.09µs
     http_req_tls_handshaking.......: avg=0s       min=0s     med=0s      max=0s       p(90)=0s       p(95)=0s      
     http_req_waiting...............: avg=9.71s    min=1.22s  med=9.8s    max=20.1s    p(90)=10.07s   p(95)=10.21s  
     http_reqs......................: 18539   30.74339/s
     iteration_duration.............: avg=9.73s    min=1.24s  med=9.82s   max=20.15s   p(90)=10.09s   p(95)=10.23s  
     iterations.....................: 18539   30.74339/s
     vus............................: 50      min=50     max=300
     vus_max........................: 300     min=300    max=300
```


**Performance Overview**


**no-image-available**


**Subgraphs Overview**


**no-image-available**


**HTTP Overview**


**no-image-available**


  </details>