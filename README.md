# QPoland Global Quantum Hackathon 2024 | QVTM

Project Submission to Open track of Global Quantum Hackathon 2024
By Qpoland and QuantumAI on DoraHacks platform

TeamName: Spin-LIQUID Pro’s
Members: 
Sabarikirishwaran Ponnambalam @Sabari_india 
Devin Bae @Death04 
Sk Saif Ibna Ezhar Arko @saifarko

We implemented a novel Quantum Variable Topic Model (QVTM) using variational quantum circuits and an encoder-decoder-like structure using KL-divergence as the training loss function. For a given group of $N = D_1,D_2,...,D_N$ documents represented by the input tensor $X_{N,V}$ (where $N$ is the number of documents and $V$ is the corresponding vocabulary size) containing a Bag-Of-Words (BoW) representation of both the documents and their corresponding word distributions, the encoder portion of the model maps this to a probability distribution $p_{enc}(θ|D)$ corresponding to a parameterized amplitude embedding, where the input tensor $X = X_{real} + iX_{imaginary}$ contains a real portion $X_{real}$ and imaginary portion $X_{imaginary}$ produced by a classical encoder with 2 layers. This feature engineering is crucial for taking advantage of amplitude embedding, where both the phase and amplitude are used to represent data. 

The wavefunction for the encoder is given by: $$|ϕ_α(X)⟩ = V(α_L^ϕ)...V(α_2^ϕ)V(α_1^ϕ)|X⟩$$, where the initial quantum state $|X⟩$ (representing the input tensor $X$) undergoes evolution by passing through the variational layers $|ψ_α(X)⟩$. We utilize the following numerically stable Gaussian metric kernel to minimze the distance between the encoder and Dirichlet prior distribution $p(θ)$, allowing the encoder to properly match the distribution: $$k(x,y)=exp(-\frac{||x-y||^2}{2σ^2})$$

After taking measurement probabilities over all possible quantum states, we utilize a decoder to output the topic distribution $p'(D_t|θ)$ for a given dataset. Similar to the encoder, the wavefunction for the decoder is given by: $$|μ_α(W)⟩ = V(α_L^μ)...V(α_2^μ)V(α_1^μ)|W⟩$$.

The parameterized layers utilize the entire Hilbert space correspoding to $2^n$ (where $n$ is the number of qubits) quantum states. By extracting the probabilities over all possible quantum states of the system (instead of simply taking expectation values), we are able to take full advantage of the rich representation offered by the Hilbert space. For normalization and computational purposes, the number of qubits used for the encoder is $n_{enc}=log_2(K)$ (where $K$ represents the desired number of topics) and the number of qubits used for the decoder is $n_{dec}=log_2(V)$ (where $V$ represents the total vocabulary size of the dataset). 

# Architecture
![arch](https://github.com/user-attachments/assets/6dbf4627-586a-4ecf-aca1-4f60f05ee07f)


# Results
![image](https://github.com/user-attachments/assets/82b2f1be-d0d6-4258-8b3e-c365c6e090c2)

# video
[https://drive.google.com/file/d/10QQlWQcv1cXID7X9qov9vV3Ch125X5n/view?usp=drive_link](https://drive.google.com/file/d/1Ccr9PtVWH-wVnn1Y2v3I0cEEx57vMlbQ/view?usp=drive_link)

# Presentation
https://docs.google.com/presentation/d/1zuz3kxSnFRrWQ9ZKAiZYKj0-BqkCH_an/edit?usp=sharing&ouid=101409929004152227685&rtpof=true&sd=true
