This page documents the tokens per second (tps) for the various models and devices I've tested using llama.cpp and the server.
All devices, except for the Dell Xeon, are CPU only.

### Linux Mint
|Model|HP i3<br>8GB RAM|HP i3<br>16 GB RAM|Dell i7<br>32GB RAM|Dell Xeon<br>64GB RAM|
|---|---|---|---|---|
|Llama 3 8B instruct Q4_K_M|May 5: 1.9&nbsp;tps|May 5: 2.0&nbsp;tps|May 5: 4.6&nbsp;tps|May 5: 4.5&nbsp;tps (CPU only)<br>Couldn’t test GPU with the binary|
|Llama 3 8B instruct Q8_0|X|May 5: 1.6&nbsp;tps|May 5: 3.1&nbsp;tps|May 5: 2.9&nbsp;tps (CPU only)<br>Couldn’t test GPU with the binary|
|Llama 3 8B instruct BF16|X|X|May 5: 1.8&nbsp;tps|May 5: 1.6&nbsp;tps (CPU only)<br>GPU not supported as of test date|
|Llama 3 70B Instruct Q4_K_M|X|X|X|May 5: 0.5&nbsp;tps (CPU only)<br>Couldn’t test GPU with the binary|
|||||
|Mistral 7B instruct Q4_K_M|May 5: 2.2&nbsp;tps|May 5: 2.3&nbsp;tps|May 5: 5.1&nbsp;tps|May 5: 4.8&nbsp;tps (CPU only)<br>Couldn’t test GPU with the binary|
|Mistral 7B instruct Q8_0|X|May 5: 1.8&nbsp;tps|May 5: 3.3&nbsp;tps|May 5: 3.1&nbsp;tps (CPU only)<br>Couldn’t test GPU with the binary|
|||||
|Phi-3 mini 4k instruct Q4_K_M|May 5: 3.6&nbsp;tps|May 5: 3.7&nbsp;tps|May 5: 8.7&nbsp;tps|May 5: 8.3&nbsp;tps (CPU only)<br>Couldn’t test GPU with the binary|
|Phi-3 mini 4k instruct Q8|May 5: 2.9&nbsp;tps|May 5: 3.2&nbsp;tps|May 5: 6.0&nbsp;tps|May 5: 5.5&nbsp;tps (CPU only)<br>Couldn’t test GPU with the binary|

X = Not supported - Model/quant too large OR so slow it’s unusable (such as 1 token every few minutes)

### Intel Mac
|Model|2018 MacBook Pro 8GB RAM|
|---|---|
|Llama 3 8B instruct Q4_K_M| |
|Llama 3 8B instruct Q8_0| |
|Llama 3 8B instruct BF16| |
|Llama 3 70B Instruct Q4_K_M|X|
|||||
|Mistral 7B instruct Q4_K_M| |
|Mistral 7B instruct Q8_0| |
|||||
|Phi-3 mini 4k instruct Q4_K_M| |
|Phi-3 mini 4k instruct Q8| |
