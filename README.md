## Summary

Notes from Jensen Huang’s keynote at Computex Taipei 2025

## 1. NVIDIA’s Vision: From DGX-1 to AI Factories

### 1.1 DGX-1 and the New Software Paradigm
- **DGX-1** was introduced as one of the world’s first integrated AI supercomputers, combining eight Tesla V100 GPUs, NVLink interconnect, and the NVIDIA GPU Cloud Deep Learning Stack to deliver 4× faster training compared to other GPU systems.
- AI is no longer an application but a transformative software layer—on par with electricity and the Internet—infrastructures must now be reimagined around AI.

### 1.2 Evolution of Data Centers and AI Factories
- **Data Center Transformation**: Traditional server farms are evolving into integrated AI data centers, where “units of computing” shift from individual servers to system-level nodes optimized for AI workloads.
- **Mellanox Integration**: Since acquiring Mellanox in 2019, NVIDIA has integrated [high-speed networking](#high-speed-networking) to support AI traffic, underscoring the importance of end-to-end system performance.
- **AI Factories**: describe clusters of AI-optimized data centers that generate tokens at scale, streamlining deployment and consumption.

---

## 2. Accelerated Computing and Software Innovations

### 2.1 CUDA-X and Specialized Computing
- **CUDA-X Libraries** form the foundation of NVIDIA’s accelerated computing platform, enabling developers to exploit GPU parallelism for AI tasks rather than relying on general-purpose CPUs.
- **Not General-Purpose Computing**: true acceleration requires task-specific libraries; GPUs with optimized CUDA-X deliver orders-of-magnitude speedups on AI workloads.

### 2.2 DLSS and Consumer AI Hardware
- **DLSS (Deep Learning Super Sampling)** lets developers render only ~10% of pixels and use AI to reconstruct the full image, boosting frame rates without compromising visual fidelity.
- **RTX 5060 on ASUS Laptop**: Demonstrations of an ASUS laptop equipped with GeForce RTX 5060 showcased how advanced AI inference is coming to mainstream consumer devices.

### 2.3 Code Optimization with Accelerated Libraries
- ~5% of code often consumes ~95% of runtime, emphasizing tools that accelerate these critical paths—leading to app-wide performance boosts of up to 5×.

### 2.4 cuOpt and cuLitho
- **cuOpt**: NVIDIA’s GPU-accelerated decision-optimization engine for supply-chain and logistics problems was announced as open-source, enabling rapid scenario planning and real-time adjustment.
- **cuLitho**: A library that accelerates computational lithography by up to 40× versus CPU methods, using GPU parallelism to optimize chip-manufacturing masks.

---

## 3. Quantum and Agentic AI

- **Quantum GPU Computing**: NVIDIA previewed early research into hybrid QPU/CPU/GPU systems under the “CUDA-Q” initiative, still in intermediate stages of development.
- **Agentic AI**: or AI agent, systems that can understand, think, and act autonomously—processing text, images, and video to set goals, plan, and execute—were positioned as the next frontier beyond simple [inference](#inferencing).
- **Robotic Loop**: Extending Agentic AI into “Physical AI,” NVIDIA demonstrated robots that perceive environments, reason about consequences, and execute plans in real time.

---

## 4. [Scaling AI Infrastructure](#ai-infrastructure)

### 4.1 Grace Blackwell and GB300
- **Grace Blackwell NVL72**: A server platform designed for elastic scaling—“scale-out is easy, scale-up is hard”—addresses rising inference demands.
- **GB300 Ultra Superchip**: NVIDIA’s latest chip module offering 100% liquid cooling, maintaining training throughput while cutting inference time significantly; uses advanced NVLink interconnect with nine switches on a spine for east-west data flow.

### 4.2 GB200 and CoWoS Process
- **GB200 Specs**: Delivers up to 900 Tb/s interconnect bandwidth at 120 kW power consumption, built with TSMC’s Chip-on-Wafer-on-Substrate (CoWoS) process for tight integration.
---

## 5. Collaborative and Custom Solutions

### 5.1 NVLink Fusion
- **NVLink Fusion**: A semicustom infrastructure initiative enabling integration of NVIDIA GPUs with third-party CPUs/ASICs (from partners like Marvell, MediaTek, Google), unified via NVLink fabric.

### 5.2 DGX Spark and DGX Station
- **DGX Spark**: A desktop AI computer for developers (“personal AI cloud”), powered by the Grace Blackwell chip with up to 1 PFLOP of compute and 128 GB [LPDDR](#lpddr) memory.
- **DGX Station**: A workstation capable of serving models with up to 1 trillion parameters, integrating compute, storage, and networking in a compact form factor.

---

## 6. Data Processing and Retrieval
- **AI-Q Blueprint**: NVIDIA’s framework for querying unstructured data (semantic search) versus traditional SQL databases.
- **VAST Partnership**: Collaboration delivering 1.5× faster data extraction and 50% higher retrieval accuracy using Llama-Neo reasoning models, continuous fetch/embed indexing, and fast semantic search.

---

## 7. Robotics and Physical AI

**Perception & Planning**: High-fidelity physics engines (e.g., for sand-particle simulation) train robots in realistic environments, addressing labor shortages and unlocking new commercial applications.

---

## 8. Strategic Announcements

**NVIDIA Constellation**: in Beitou–Shilin, Taipei, reinforcing long-term investment in Taiwan’s AI ecosystem.

---
### High-Speed Networking
高速網路是現代 AI 生態系統的核心，對於大型語言模型（LLM）訓練與推論的效率至關重要。NVIDIA 的 Selene 超級電腦使用 1080 顆 AMD EPYC CPU 和 4320 顆 A100 GPU，能在不到 16 秒內完成 BERT 模型的訓練，而傳統系統可能需要超過 20 分鐘。為支援如此高效的運算，NVIDIA 採用 Mellanox 的 NDR 400G InfiniBand 技術，提供每秒 400Gb 的傳輸速率和極低的延遲，成為 AI 資料中心的標準網路解決方案。此外，NVIDIA 的 SuperNICs 支援高達 800Gb/s 的資料吞吐，並透過 GPUDirect RDMA 技術實現 GPU 之間的直接資料傳輸，降低 CPU 負載，提升資料傳輸效率。在網路基礎設施方面，NVIDIA 推出的 Spectrum-4 switch 提供高達 51.2Tb/s 的交換容量，支援 128 個 400GbE 端口，滿足大規模 AI 資料中心的需求。為進一步提升網路效能，NVIDIA 推出整合矽光子技術的 Spectrum-X 和 Quantum-X switch，支援高達 1.6Tb/s 的端口速度，總吞吐量可達 400Tb/s，並將網路功耗降低 3.5 倍。同時，以太網在 AI 資料中心的應用也在快速增長。 Arista Networks 提供的以太網switch已被多家超大規模運算業者採用，預計其 AI 相關銷售在 2025 年將達到 7.5 億美元。

---
### LPDDR
NVIDIA 的 DGX Spark 採用 128GB LPDDR5x 記憶體，這是針對 AI 原生開發者設計的個人 AI cloud server。LPDDR（Low Power Double Data Rate）記憶體與傳統的 DDR（Double Data Rate）記憶體在多方面有所不同。LPDDR 記憶體主要優勢在於低功耗、高速傳輸和統一記憶體架構。例如，LPDDR4 的工作電壓約為 1.2V，而 DDR4 的工作電壓約為 1.5V，這意味著 LPDDR4 的功耗更低。在性能方面，LPDDR5x 提供高達 8533 MT/s 的數據傳輸速率，這對於需要高速資料處理的 AI 應用非常有利。DGX Spark 的記憶體頻寬為 273 GB/s，這對於本地訓練和推論大型語言模型（LLM）提供了足夠的帶寬支持。DGX Spark 採用統一記憶體架構，CPU 和 GPU 共享同一記憶體空間，這簡化了記憶體管理，並提高了資料傳輸效率。這種設計對於需要大量記憶體的 AI 模型，特別是在本地開發和測試階段，提供了便利。

---
### Inferencing
生成式 AI 的推理階段（inference）是模型將訓練所得知識應用於實際任務的過程，對於大型語言模型（LLM）而言，通過合理的推理時間擴展技術，可以在不增加模型規模的情況下，提升模型在複雜任務中的表現。然而，這也需要在計算資源和推理能力之間進行權衡，以實現最佳的應用效果。由於推理階段在每次使用時都會發生，因此其計算資源消耗和延遲成為部署 AI 系統時的重要考量。推理階段的計算成本主要取決於模型的參數量、輸入的上下文長度以及生成的輸出長度。例如，處理較長的輸入或生成較長的輸出都會增加計算需求，進而提高延遲和能源消耗。此外，為了提升模型的推理能力，研究人員引入了推理時間擴展（inference-time scaling）技術，允許模型在推理階段進行多步思考或生成中間結果，以提高複雜任務的解決能力。推理時間擴展技術包括Chain-of-Thought prompting、Self-consistency decoding和Tree of Thoughts等，這些方法通過引導模型生成中間推理步驟或評估多個可能的答案，從而提高最終輸出的準確性。然而，這些技術也會增加推理階段的計算負擔，因為它們需要模型生成更多的內容或進行多次計算。為了平衡推理能力和計算成本，研究人員探索了不同的推理時間擴展策略。例如，IBM 的 Granite 3.2 模型通過引導模型生成更長的思考鏈，並結合多數投票機制，在數學推理任務中超越了更大規模的模型，如 GPT-4o 和 Claude 3.5。這表明，即使是較小的模型，也可以通過適當的推理時間擴展技術，在特定任務中達到或超越大型模型的表現。然而，推理時間擴展的效果並非在所有任務中都一致。根據一項研究，僅僅增加推理階段的計算量，並不總是能夠提高模型在複雜任務中的表現。因此，選擇適當的推理時間擴展策略，並根據具體任務進行調整，是提升模型推理能力的關鍵。

**Chain-of-Thought prompting**：這是一種引導語言模型通過中間推理步驟來解決問題的方法。例如，模型可能會被提示：「Roger has 5 tennis balls. He buys 2 more cans of tennis balls. Each can has 3 tennis balls. How many tennis balls does he have now?」然後模型會逐步解釋其推理過程。
**Self-consistency decoding**：這種方法涉及生成多個推理路徑，然後選擇最一致的答案。例如，模型可能會生成多個解決方案，然後通過多數投票來確定最可能的正確答案。
**Tree of Thoughts**：這種技術將推理過程結構化為樹狀結構，允許模型探索多個可能的解決方案路徑，從而提高解決複雜問題的能力。例如，模型可能會在解決數學問題時，考慮不同的計算策略，並選擇最有效的路徑。


---
### AI Infrastructure
NVIDIA 的 Grace Blackwell NVL72 架構是為了支援大規模 AI 模型訓練與推論而設計的高效能運算平台。該系統整合了 36 顆 Grace CPU 和 72 顆 Blackwell GPU，透過第五代 NVLink 技術連接，形成一個統一的計算單元。每個 GB200 Superchip 包含兩顆 Blackwell GPU 和一顆 Grace CPU，透過 NVLink-C2C 介面以 900 GB/s 的雙向頻寬連接，實現統一的記憶體空間。NVLink 的第五代技術提供每個 GPU 1.8 TB/s 的互連頻寬，支援最多 72 顆 GPU 的連接，形成一個大型的 NVLink 域。在 NVL72 架構中，使用了九個 NVLink switch，每個 switch 包含兩個 NVLink 7.2T ASIC，總共提供 144 個 100 GB/s 的連接。NVL72 系統包含 18 個計算節點，每個節點配備兩個 GB200 Superchip，總共提供 72 顆 GPU 和 36 顆 CPU。每個計算節點的功耗約為 5.4 kW，整個機架的總功耗約為 132 kW。為了應對高密度運算帶來的散熱挑戰，NVL72 採用了全液冷設計，使用冷卻液在 45°C 至 65°C 的溫度範圍內循環，通過冷卻板直接冷卻處理器。這種設計提高了計算密度，減少了佔地面積，並降低了能源消耗。在性能方面，NVL72 在 FP4 精度下提供 1,440 PFLOPS 的推論性能，在 FP8 精度下提供 720 PFLOPS 的訓練性能。這使其能夠支援高達數兆參數的 AI 模型訓練與推論需求。此外，NVL72 系統還整合了 NVIDIA 的 Magnum IO 軟體，支援高效的資料處理與傳輸，進一步提升整體系統的效能與效率。
