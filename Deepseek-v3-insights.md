# Insights into DeepSeek-V3: Scaling Challenges and Reflections on Hardware for AI Architectures

DeepSeek-AI, Beijing, China

## Abstract

The rapid scaling of large language models (LLMs) has unveiled critical limitations in current hardware architectures, including constraints in memory capacity, computational efficiency, and interconnection bandwidth. DeepSeek-V3, trained on 2,048 NVIDIA H800 GPUs, demonstrates how hardware-aware model co-design can effectively address these challenges, enabling cost-efficient training and inference at scale. This paper presents an in-depth analysis of the DeepSeek-V3/R1 model architecture and its AI infrastructure, highlighting key innovations such as Multi-head Latent Attention (MLA) for enhanced memory efficiency, Mixture of Experts (MoE) architectures for optimized computation-communication trade-offs, FP8 mixed-precision training to unlock the full potential of hardware capabilities, and a Multi-Plane Network Topology to minimize cluster-level network overhead. Building on the hardware bottlenecks encountered during DeepSeek-V3’s development, we engage in a broader discussion with academic and industry peers on potential future hardware directions, including precise low-precision computation units, scale-up and scale-out convergence, and innovations in low-latency communication fabrics. These insights underscore the critical role of hardware and model co-design in meeting the escalating demands of AI workloads, offering a practical blueprint for innovation in next-generation AI systems.

大语言模型的迅速增长，暴露了当前硬件架构的关键局限，包括内存容量，计算效率和互联带宽方面的限制。DeepSeek-V3是在2048块NVidia H800 GPUs上训练的，展现了感知硬件的模型协同设计可以有效的处理这些挑战，可以在很大规模上进行高效的训练和推理。本文给出了DeepSeek-V3/R1模型架构及其AI基础设施的深度分析，强调了其中的关键创新，如多头隐注意力(MLA)-可以增强内存效率，混合专家模型(MoE)-可以优化计算-通信折中，FP8混合精度训练-可以解锁硬件潜能，多平面网络拓扑-可以让cluster级的网络开销最小化。在开发DeepSeek-V3的过程中遇到了一些硬件瓶颈，在此基础上，关于未来硬件发展的方向，我们与学术同行、业界同行进行了广泛的讨论，包括低精度计算单元，scale-up和scale-out的收敛，以及低延迟通信架构的创新。这些洞见强调了在满足AI workload的需求中，硬件、模型共同设计的关键角色，给出了下一代AI系统创新中的实际蓝图。

## Keywords

Large Language Model, Mixture-of-Experts, Deep Learning, FP8 Mixed-Precision Training, Multi-Plane Network, Co-Design