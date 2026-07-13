# Academic Research & Literature Reports

A curated collection of my technical research, literature reports, and system architectures, demonstrating my ability to evaluate complex engineering trade-offs, design resilient systems, and structure publication-grade documentation.

## Featured Reports

### 1. [Mini-CLIP Framework Evaluation (Deep Learning)](./Mini-clip-report.pdf)
* **Type:** Individual Project
* **Overview:** A compact re-implementation of OpenAI's Contrastive Language-Image Pre-training (CLIP) framework fine-tuned on the Flickr30k dataset.
* **Architecture:** Utilizes a partially-frozen ResNet-50 image encoder and a DistilBERT text encoder projecting into a shared 256-dimensional embedding space, optimized via symmetric InfoNCE loss.
* **Key Metrics:** Achieved 21.1% Text→Image R@1 and 61.7% R@10 on a 1,000-sample test set. Ablation studies confirmed performance saturation at batch size $B=64$. 
* **Source Code:** [prajwl7676/mini-clip-DLAI](https://github.com/prajwl7676/mini-clip-DLAI)

### 2. [AWS Lambda Performance & Cost Analytics](./Aws-lambda-evaluation-report.pdf)
* **Type:** Group Contribution
* **Overview:** A rigorous empirical evaluation analyzing the scalability, latency profiles, and cost boundaries of serverless architectures for heavy image processing pipelines.
* **Methodology:** Designed a factorial load-testing matrix (72 scenarios, 52,272 total invocations) utilizing Locust over public endpoints paired with server-side Amazon CloudWatch metrics.
* **Key Findings:** Uncovered a critical bottleneck where upstream Amazon API Gateway drops connection handling (up to 57% HTTP failures at 100 concurrent users) despite zero server-side Lambda throttling. Modeled a 6-month financial projection establishing a break-even threshold against EC2 instances at 5.5 million invocations/month.

### 3. [Resilient OTA Attestation for Connected Vehicles](./Connected-vehicle-security-report.pdf)
* **Type:** Group Contribution
* **Overview:** Proposes a two-path architecture to solve availability gaps in standard hardware-rooted Over-the-Air (OTA) firmware attestation frameworks across automotive Electronic Control Unit (ECU) networks.
* **Architecture:** 
  * *Deterministic Real-Time Path:* Microsecond-scale gateway-level isolation that injects fallback frames to trigger a limp-home mode for non-critical failures, while safely locking the vehicle for safety-critical failures.
  * *Asynchronous Out-of-Band Path:* Decoupled Edge AI loop running a quantized Small Language Model (SLM) on the Telematics Control Unit to analyze hardware telemetry logs and generate targeted micro-patch remediation manifests.
