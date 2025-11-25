# ECE 565 Project – Presentation on NRP (National Research Platform)

## What is NRP?

The National Research Platform (NRP) is a community-driven research and education
cyberinfrastructure project. It is a partnership of over 50 institutions (led by UC San Diego,
University of Nebraska–Lincoln, and MGHPCC) that connects researchers and educators with shared
advanced computing resources ￼. Backed by major U.S. agencies (National Science Foundation,
Department of Energy, Department of Defense, etc.), NRP provides free access to cutting-edge
technologies in artificial intelligence (AI), high-performance computing (HPC), data storage,
and high-speed networking for academic users ￼ ￼. Importantly, NRP is open to all non-profit
higher education institutions – from community colleges to top research universities – allowing
broad participation in advanced computing and fostering nationwide collaboration ￼.

One of NRP’s core offerings is a globally distributed computing platform known as Nautilus. The
Nautilus system is essentially a large-scale Kubernetes-based cluster (over ~300–400 nodes
across more than 70 sites) that integrates compute, storage, and networking into a unified
infrastructure ￼ ￼. This heterogeneous cluster spans multiple campuses (even multiple
continents) and features a mix of powerful CPUs, GPUs, FPGAs, and petabytes of distributed
storage, all linked by ultra-fast research networks ￼ ￼. In essence, the NRP (via Nautilus)
collapses geographical barriers by enabling researchers to leverage a nationwide pool of
computing resources as if it were one large HPC system. The scale of NRP is significant – as of
2025 it encompasses 400+ nodes at 70+ locations, serving over 5,000 users across the academic
community ￼.

(Image:nodemap.png NRP Nautilus node map – showing distributed cluster resources across the
network) ￼

• NRP homepage (overview/mission/stats): <https://nationalresearchplatform.org/> • Partners
(institutions): <https://nationalresearchplatform.org/partners> • AUP (Acceptable Use Policy,
PDF): <https://nationalresearchplatform.org/NRP-AUP.pdf> • Docs index (“Getting Started with
Nautilus Cluster”): <https://nationalresearchplatform.org/documentation/> • New user guide /
login & namespaces: <https://nrp.ai/documentation/userdocs/start/getting-started/> • Cluster
dashboard (metrics & map): <https://dash.nrp-nautilus.io/> • Nautilus cluster map
(interactive): <https://wp.nationalresearchplatform.org/nautilus-cluster-map/> ￼

### What is Nautilus?

Nautilus is the name of the NRP’s distributed, hyper-converged cluster that powers its
computing capabilities. In technical terms, Nautilus is a federation of high-performance
computing nodes orchestrated by Kubernetes, where compute, storage, and network resources are
tightly integrated. Unlike a traditional single-site supercomputer, Nautilus is spread across
dozens of institutions – individual Nautilus nodes reside at many partner campuses, but they
operate together as one logical cluster ￼. Each node typically consists of high-end servers
(often with GPUs like NVIDIA A100s, RTX 3090s, etc., or even FPGAs) plus fast local NVMe
storage and high-speed network interfaces ￼ ￼. All these distributed nodes are “stitched
together” with very fast networks to behave as a cohesive system ￼.

What distinguishes Nautilus is its ability to run containerized workloads anywhere on the
network of nodes. Users submit jobs (or launch containers) into Nautilus, and Kubernetes
intelligently schedules them on any available resources across the entire cluster ￼. This means
a researcher can deploy a computing task that utilizes CPUs or GPUs at one site, or even span
multiple sites, without having to interact with each site separately – Nautilus handles the
placement and resource allocation. The cluster’s hyper-converged design (compute + storage +
network at each site) ensures that data can be stored near where computation happens, and large
datasets can be moved or replicated quickly between sites. In summary, Nautilus is a nationwide
supercomputing cloud for academia – it provides the flexibility of cloud container
orchestration with the horsepower of HPC-grade hardware distributed across the country ￼ ￼.

Nautilus at a glance: It contains a wide variety of GPU hardware (from NVIDIA RTX 2080 Ti’s up
to A100 Tensor Core GPUs) for both standard and high-precision AI workloads ￼. It also
incorporates high-speed data transfer nodes and distributed storage (e.g., Ceph-based data
pools), enabling users to ingest and process large datasets with ease ￼. Because all software
on Nautilus runs inside containers, users can bring custom environments and be confident their
code is portable and scalable across the cluster ￼. In short, Nautilus is the technical
foundation of the NRP, delivering a federated computing environment where researchers get
on-demand access to GPUs, CPUs, and storage spread across many institutions, all through common
interfaces.

• Nautilus introduction (hyper‑converged, distributed design):
<https://nationalresearchplatform.org/documentation/userdocs/tutorial/introduction/> • Using
Nautilus (ways to access—JupyterHub, Coder, kubectl, services):
<https://nationalresearchplatform.org/documentation/userdocs/start/using-nautilus/> • Docs
index (all topics): <https://nrp.ai/documentation/> • SDSC NRP/Nautilus user guide (hardware
snapshot & access): <https://www.sdsc.edu/systems/nrp/user_guide.html> • Cluster nodes map
(visual): <https://wp.nationalresearchplatform.org/nautilus-cluster-map/>

### What Can I Do With It?

With access to NRP’s Nautilus platform, researchers and students can perform a wide range of
computing tasks that would typically require expensive or localized HPC resources. Some key
capabilities include: • AI and Machine Learning: Take advantage of Nautilus’s many GPUs
(including modern cards like NVIDIA A100 80GB Tensor Core GPUs) to train deep learning models
or run large-scale AI experiments. The cluster’s GPU variety (RTX 3090, RTX 4090, A10, A100,
etc.) allows both introductory AI projects and cutting-edge research. For example, Nautilus
provides high-memory GPUs for training large language models or other memory-intensive AI tasks
￼. Because the cluster is distributed, you can even run distributed training jobs that use
multiple GPUs across different nodes – Kubernetes will coordinate scheduling those pods on the
available GPU nodes. This means you can scale up AI workloads to many GPUs, leveraging an
entire national-scale cluster, which is especially useful for deep learning research. •
High-Performance Computing & Simulation: The NRP is effectively a distributed supercomputer.
You can run traditional HPC jobs (e.g. parallel simulations, scientific computing tasks, data
analysis pipelines) using Nautilus just as you would on a local cluster. The difference is that
Nautilus can allocate your job to any of the hundreds of nodes nationwide, potentially giving
you access to more aggregate compute power. Whether you have a CPU-heavy batch job or need GPUs
for acceleration, you can launch a Kubernetes pod or batch job in Nautilus to execute it ￼.
Researchers in fields from physics to bioinformatics can use this resource for large-scale
computations without needing to purchase their own hardware. NRP also supports containerized
HPC workflows, so complex software stacks can be run reproducibly. Additionally, specialized
hardware like FPGAs (available through certain Nautilus nodes) could be used for custom
accelerations in research projects (for advanced users with those needs) ￼. • Big Data Storage
and Analysis: Data-intensive computing is a focus of NRP. Nautilus’s design includes
distributed storage “reservoirs” and a content delivery network that caches data across
multiple sites ￼ ￼. Practically, this means you can store large datasets on NRP’s storage
system (e.g., using Ceph or S3 interfaces) and access them from any compute node with high
bandwidth. You can mount data volumes in your compute pods, enabling analysis of big datasets
without manual transfers. For example, if you have terabytes of research data, you could ingest
it into NRP’s storage once and then run analysis jobs from different institutions, all
accessing that same data repository at network speeds. The platform is optimized for fast data
movement; it can deliver data across the country within ~10 milliseconds latency via its
caching infrastructure ￼ ￼. This makes it ideal for workflows like genomics or climate science,
where large data sets need to be co-located with computing. In summary, you can use NRP to
host, share, and analyze large data collaboratively, without each researcher needing their own
local copy. • Interactive Computing and Education: NRP is also built to support educators and
students. For example, Nautilus offers a JupyterHub service that lets users spawn Jupyter
notebook environments running on the cluster’s resources ￼. This means you can do interactive
data science or coursework in a browser, but the computations are powered by the Nautilus
back-end (you can even request multiple GPUs for your Jupyter notebook server, enabling
heavy-duty interactive workloads) ￼. This is great for teaching – professors can incorporate
assignments that use real GPU-accelerated computing or large datasets, and students can log
into the NRP JupyterHub with campus credentials (e.g., via CILogon) to get a ready-to-use
notebook environment. In addition to Jupyter, Nautilus supports other high-level interfaces
(like Coder or science gateway platforms) to lower the barrier for users unfamiliar with
Kubernetes ￼ ￼. The key point is that you don’t necessarily need advanced sysadmin skills to
use NRP – if you prefer, you can stick to user-friendly tools (like Jupyter notebooks) that NRP
provides, which run on the same powerful infrastructure. This opens the door for usage in
workshops, classes, and by researchers who want quick results without configuring local HPC
environments. • Networking and Distributed Experimentation: Because Nautilus spans a wide-area
network, it enables unique experiments that involve distributed deployment. Networking
researchers, for instance, can use the geographically separated nodes to test applications
across real-world network distances and conditions – something you cannot do on a single data
center cluster ￼. If your project involves edge computing, IoT, or distributed systems, you can
deploy services on multiple Nautilus sites and study cross-site performance (taking advantage
of the high-speed R&E network backbone connecting them). Moreover, NRP’s integration with
advanced networking (including projects like PerfSonar and SENSE) means you can instrument and
optimize network pathways for your data transfers. In summary, you can treat the NRP as a
national-scale testbed, not just for high-performance compute, but also for networking and
distributed systems research.

In short, NRP (Nautilus) can be used for almost any computational task suited to a modern HPC
or cloud platform – AI model training, large-scale simulations, big data analytics, classroom
projects, and more – with the major benefit that it’s a free, shared resource for the research
community.

• JupyterHub service (hosted notebooks):
<https://nrp.ai/documentation/userdocs/jupyter/jupyterhub-service/> • Coder (browser
IDE/desktops, templates): <https://nrp.ai/documentation/userdocs/coder/coder/> • Deployed
services (Ray, Dask, Kubeflow; GitLab/Nextcloud/Overleaf):
<https://nrp.ai/documentation/userdocs/start/resources/> • Managed LLMs (OpenAI‑compatible
endpoint & LibreChat):
<https://nationalresearchplatform.org/documentation/userdocs/ai/llm-managed/> • Vector database
(Milvus): <https://nrp.ai/documentation/userdocs/ai/vector-database/> • Storage – CephFS / RBD
(POSIX & block): <https://nationalresearchplatform.org/documentation/userdocs/storage/ceph/> •
Object storage (Ceph S3) – admin notes:
<https://nationalresearchplatform.org/documentation/admindocs/storage/ceph-s3/> • Moving data
(S3, Nextcloud, rclone):
<https://nationalresearchplatform.org/documentation/userdocs/storage/move-data/> • Globus
Connect (for external transfers):
<https://nrp.ai/documentation/userdocs/running/globus-connect/> • Exposing services (Ingress /
HTTPS endpoints):
<https://nationalresearchplatform.org/documentation/userdocs/running/ingress/> • Cluster
policies (runtime limits, GPU guidance):
<https://nrp.ai/documentation/userdocs/start/policies/>

### Comparison with Commercial Options

How does the NRP/Nautilus platform stack up against using commercial cloud services? Here we
compare it with three obvious alternatives – Amazon AWS, Google Cloud Platform, and Microsoft
Azure – particularly in terms of access and cost: • NRP/Nautilus (Academic) – The NRP is free
to use for qualified academic researchers and educators (those from institutions participating
in InCommon) ￼. Users do not pay for compute time or storage, thanks to NSF and other agency
funding. However, access is limited to the research/education community and governed by
fair-use policies (for instance, there may be resource quotas or scheduling queues to ensure
equitable sharing). Using Nautilus requires some setup (e.g., logging in via campus
credentials, installing Kubernetes kubectl client, etc.) and understanding of its acceptable
use policies ￼ ￼. The trade-off is that while you get powerful resources at no monetary cost,
you might face wait times if the cluster is busy and you are expected to use the platform for
legitimate research/educational purposes. There’s also a learning curve for tools like
Kubernetes (though, as noted, one can use easier interfaces like JupyterHub to mitigate this).
In summary, NRP provides huge cost savings – essentially providing cloud-like HPC resources
without usage fees – but is exclusive to the academic community and requires adhering to
community rules. • Amazon Web Services (AWS) – AWS is a leading commercial cloud provider where
anyone (with a credit card) can rent computing resources on-demand. AWS offers a range of GPU
instance types in its Elastic Compute Cloud (EC2) service comparable to NRP’s capabilities. For
example, AWS’s p4d.24xlarge instance comes with 8 NVIDIA A100 GPUs and costs about $32 per hour
on-demand ￼ (which is roughly $4 per GPU-hour). If you only need a single GPU, smaller
instances (like EC2 g4dn or g5 series with NVIDIA T4 or A10G GPUs) are available, often on the
order of $1–2 per hour for those lower-end GPUs ￼ ￼. However, for the cutting-edge GPUs
equivalent to what Nautilus provides (e.g. A100 40GB), expect to pay around $4/hour per GPU on
AWS ￼. This means that a multi-node, multi-GPU experiment running for days could cost thousands
of dollars on AWS – a significant expense for a research lab without dedicated funds. AWS does
offer economies of scale (and discounted rates via reserved instances or spot pricing), but in
general, the pay-as-you-go cost is substantial. On the upside, AWS provides very polished
services, a vast ecosystem of managed tools, and usually immediate scalability (you can often
get resources on-demand, assuming you have the budget and any required quota approvals). In
contrast to NRP, there’s no waiting for a “slot” – if you can pay, you get the resources
dedicated to you. There’s also no restriction on use-case (beyond AWS’s terms of service) –
commercial, personal, or any type of project can run on AWS, whereas NRP is restricted to
non-profit research/education use. • Google Cloud Platform (GCP) – Google Cloud similarly
offers GPU-equipped virtual machines in its Compute Engine service. GCP’s pricing and hardware
options are in the same ballpark as AWS. For instance, a single NVIDIA A100 (40GB) instance on
GCP is roughly $3.50–$4.00 per hour in on-demand mode, depending on the region ￼. An 8-GPU A100
server (e.g., the A2 MegaGPU-8g instance) costs about $32–$33 per hour on-demand, which again
is about $4/GPU-hour (comparable to AWS) ￼. Google often touts sustained-use discounts or
committed-use discounts – so long-running jobs might get a small automatic discount after a
certain usage duration, and one can get lower rates (sometimes ~30% lower) by committing to
usage for 1 or 3 years. Even so, the on-demand pricing for high-end GPUs remains several
dollars per hour per GPU. GCP may be “slightly cheaper” than AWS in some cases ￼ – for example,
one source noted Google’s GPU rates were marginally more affordable than AWS and Azure for
comparable instances – but the difference is not dramatic without special discounts. Like AWS,
Google Cloud offers credits (especially for educational or startup users) which can offset
costs in the short term. But once credits run out, an active AI training project on GCP can
burn through funds quickly. In terms of user experience, GCP provides integrated tools and
managed services (like BigQuery, AI Platform, etc.) which can be easier to use for certain
tasks than setting up everything on Nautilus. However, these conveniences come at the direct
cost of metered billing for every hour of GPU, every GB of storage, and even network egress. •
Microsoft Azure – Azure is Microsoft’s cloud platform, and it too provides GPU VM instances for
machine learning and HPC (Azure’s GPU instances have names like NC-series or ND-series).
Azure’s pricing is also on par with AWS/GCP: for example, Azure’s NC A100 v4 virtual machines
(with NVIDIA A100 80GB GPUs) cost roughly $3.60–$4.00 per GPU-hour in pay-as-you-go pricing ￼.
This means a VM with 4×A100 GPUs might be billed around $14.7/hour, and an 8×A100 setup near
$29/hour, very similar to the other clouds. Azure and AWS even had identical pricing for some
older GPU models (both charged about $3.06/hr for an NVIDIA V100 in one comparison) ￼. Azure’s
cloud is often used by enterprises and also offers specialized HPC scheduling via Azure Batch
and AI-specific services. From a researcher’s perspective, Azure might be less commonly used
than AWS/GCP, but it is equally commercial (paid) – you either pay on-demand or seek out Azure
for Education credits or grants to cover the expenses. The benefit Azure touts is integration
with Windows and productivity tools, and some unique hardware options (at one point Azure had
early access to certain FPGA and InfiniBand features). But for pure GPU compute, Azure’s
capabilities and costs are in the same league as its cloud competitors. In short, any
hyperscaler cloud (AWS, Google, Azure) will provide excellent hardware and flexibility, but
cost will be a limiting factor for academic projects – running a large GPU job for a week could
cost as much as a new high-end PC, which is why platforms like NRP are so valuable.

In summary, the National Research Platform’s Nautilus cluster offers university researchers a
way to perform large-scale computing without direct fees, whereas commercial cloud options
charge by consumption. To put it in perspective, a project that might consume, say, 100
GPU-hours would cost on the order of $300–$400 on AWS/GCP/Azure, but $0 on NRP (assuming you
have access and abide by fair use) ￼. For long-running or resource-intensive experiments, this
difference is enormous. The trade-off is that NRP is a shared academic resource – you might
need to work within queue limits and support channels, and it may require more hands-on
management (containerizing your app, etc.) compared to some one-click cloud services. Yet, for
those in academia, the cost savings and collaborative spirit of NRP often outweigh the
convenience of commercial clouds. In fact, NRP can be seen as a way to level the playing field,
giving researchers (even at smaller colleges) access to world-class computing infrastructure
without needing large grants for cloud budgets. Commercial clouds remain an option if you need
guaranteed resources or proprietary services, but the NRP is an excellent first resort for
research computing in terms of performance per dollar (with “dollar” being essentially zero,
thanks to funding). ￼

Amazon Web Services (AWS) • EC2 P4 (A100) instances overview:
<https://aws.amazon.com/ec2/instance-types/p4/> • EC2 on‑demand pricing (GPU instances listed
by region): <https://aws.amazon.com/ec2/pricing/on-demand/>

Google Cloud Platform (GCP) • GPU machine types (A2/A3 families):
<https://cloud.google.com/compute/docs/gpus/> • GPU pricing (on‑demand & Spot):
<https://cloud.google.com/compute/gpus-pricing>

Microsoft Azure • NC_A100 v4 series (A100 VMs) overview:
<https://learn.microsoft.com/en-us/azure/virtual-machines/sizes/gpu-accelerated/nca100v4-series>
• Linux VM pricing (price selector by region):
<https://azure.microsoft.com/en-us/pricing/details/virtual-machines/linux/>

Optional convenience (third‑party price trackers): AWS p4d.24xlarge:
<https://cloudprice.net/aws/ec2/instances/p4d.24xlarge> Azure NC24ads A100 v4:
<https://instances.vantage.sh/azure/vm/nc24ads-v4> ￼

## NRP/Nautilus services & capabilities (

Legend. “How you use it” gives the primary user entry point(s). “Notes/limits” highlights the
most relevant operational constraints.

Area What you get on NRP/Nautilus How you use it Notes / limits Identity & access
Org→Lab→Project hierarchy that maps to Kubernetes namespaces; access via Authentik/CILogon;
donation‑based fair‑share with YuniKorn Web portal + kubectl Hierarchical management,
faculty/lab admins can self‑manage users/namespaces; fair‑share scheduling integrates with
Apache YuniKorn. ￼ General compute Multi‑site Kubernetes cluster with CPU nodes;
job/long‑running controllers for batch & services kubectl, Jobs/Deployments, JupyterHub, Coder
Use Jobs for batch, Deployments for long‑running services. Resource requests/limits matter for
QoS & placement. ￼ GPUs (NVIDIA) Broad mix (A100, A40, RTX A6000, GH200, MIG profiles, etc.)
with scheduling by resource type (e.g., nvidia.com/a100) YAML pod specs, Jobs; JupyterHub
spawner; Coder templates A100 usually requires reservation; interactive pods: ≤2 GPUs;
high‑memory & GH200 need specific resources/arm64 images. ￼ Non‑GPU accelerators Qualcomm Cloud
AI 100 Ultra (32 allocatable devices cluster‑wide), OpenAI‑compatible vLLM image Request
qualcomm.com/qaic resource; use provided image Each card has 4 SoCs; up to ~25B‑param LLM per
device (SDK/vLLM build provided). ￼ FPGAs / SmartNICs AMD/Xilinx Alveo U55C with Vivado/Vitis
licenses and P4 (VitisNetP4) support; SmartNIC workflows Coder “U55C Vitis” / “ESnet SmartNICs”
workspace templates One‑click development envs with license server; SmartNIC framework &
workflows provided. ￼ Distributed frameworks Ray, Dask, Kubeflow for scalable
training/inference & pipelines Helm charts & CRDs (RayCluster), operators, Kubeflow components
Turnkey recipes & dashboards for clusters; works inside your namespace. ￼ User entry points 1)
JupyterHub West (no Kubernetes needed), 2) Coder (remote dev desktops, VS Code, CUDA/TF/PT,
FPGA templates), 3) GUI desktop (Selkies) Browser (SSO), spawner templates JupyterHub home
initially 5 GB; idle shutdown after ~1 h of browser disconnect; Coder allows up to 5 active
workspaces per user. ￼ Storage (POSIX) CephFS (shared POSIX), RBD (block), Linstor (low‑latency
VM disks) PVCs in YAML; region‑aware Choose CephFS for shared dirs; RBD for per‑pod block;
Linstor is fastest for KubeVirt VMs. ￼ Object storage Ceph S3 object store (access
inside/outside cluster) S3 clients/SDKs; access keys via portal Best option for large datasets
and high fan‑out transfers; request an account and bind secrets. Image stacks Curated
Scientific images (TF/PT, CUDA, ARM64 variants) for Jupyter & pods Pick from Jupyter spawner or
image: in YAML NRP images extend Jupyter Docker Stacks; registry hosted on NRP GitLab. ￼ Data
movement Moving data patterns: kubectl cp (small), S3 sync, Nextcloud, Globus Connect endpoint
rclone/gsutil/S3 clients; personal Globus endpoint container Use S3 for scale; avoid kubectl cp
for large transfers; Globus recipe repo provided. ￼ Networking / testbeds FABRIC integration &
ESnet SENSE/Multus; VLAN/L2 paths from FABRIC into Nautilus FABRIC slice + Nautilus pod with
VLAN attach Guides include VLAN maps and connectivity validation; good for network systems
research. ￼ Virtualization KubeVirt VMs (Linux/Windows) with GPU passthrough via VFIO nodes VM
manifests; nautilus.io/vfio nodes Choose region near Linstor; specify nvidia.com/\* device in
VM spec for GPU passthrough. ￼ CI/CD & registry Managed GitLab (SCM, CI, Container Registry)
hosted on Nautilus GitLab runners; Kaniko/Docker Buildx Container images live close to cluster;
nightly backups to Google storage. ￼ LLM services NRP‑Managed LLMs (open‑weights) via Envoy AI
gateway, web chats (LibreChat), plus vector DB Get token → OpenAI‑compatible endpoint; or use
chat UIs Model catalog & examples provided; team membership controls API access. ￼
Monitoring/observability Grafana namespace & GPU dashboards; utilization guidance Grafana web
dashboards Target GPU utilization ≥40%; tune requests/limits to match real usage. ￼ Policies
(key ops limits) AUP acceptance; resource violations page; interactive pods ≤6 h, 2‑week purge
of long‑idle Deployments; A100 by request Cluster Policies page Use Jobs for long runs;
Deployments must be minimal; permanent services require exception. ￼

## Example Use Cases

Each example ties back to specific, documented NRP capabilities (cited).

1. Multi‑GPU deep learning for mmWave beam selection / channel estimation • What: Train and
   sweep large CNN/Transformer models on realistic RF datasets; scale out hyperparameter
   search. • How on NRP: • Request appropriate GPU type (e.g., nvidia.com/a100 for large batch
   sizes; nvidia.com/gh200 for ARM/GH200 nodes) and run as Jobs; monitor utilization in Grafana
   and aim for ≥40% GPU util. ￼ • Use Ray or Dask clusters for distributed trials; leverage the
   Ray dashboard or Dask diagnostics. ￼ • Stage datasets in Ceph S3 and mount CephFS for shared
   code/results. ￼ • Build/push your container with GitLab CI so images pull fast inside
   Nautilus. ￼
2. FPGA‑accelerated packet processing / P4 SmartNIC pipeline at 100 Gb/s • What: Prototype a P4
   programmable NIC for in‑network aggregation or traffic shaping in experimental topologies. •
   How on NRP: • Start a Coder workspace using the ESnet SmartNICs or U55C Vitis template;
   Vivado/Vitis license server & P4 workflow are pre‑integrated. ￼ • Connect to external FABRIC
   slice with VLAN/L2 path to the Nautilus pod; run traffic generation and measure
   latency/throughput; automate with SENSE/Multus as in the example guide. ￼
3. LLM‑powered lab assistant with RAG for lab notebooks & datasheets • What: Serve an internal
   assistant that answers questions about your lab’s design docs, measurement logs, and
   datasheets. • How on NRP: • Use NRP‑Managed LLMs via the OpenAI‑compatible Envoy gateway
   from Python or curl; put your embeddings and chunks in the vector database service. ￼ •
   Optionally run GPU inference on A100/GH200 pods for custom vLLM models; front with a simple
   FastAPI service deployed as a Deployment + Ingress. ￼
4. Real‑time radar/SDR signal processing on GPUs • What: Implement batched FFT/CFAR/STFT
   pipelines and deep denoisers; evaluate latency/throughput vs. CPU. • How on NRP: • Spin up
   GPU pods (e.g., A40/L40 for good FP32/TF32) and orchestrate multi‑stage graphs with Dask
   (array/dataframe) to pipeline ingest→FFT→DNN. ￼ • Persist intermediate artifacts to Ceph S3;
   use Grafana to verify compute/memory balance. ￼
5. Windows‑only EDA tools or instrument control inside a VM with GPU • What: Run vendor tools
   that require Windows (e.g., waveform viewers, instrument SDKs) or test CUDA on Windows for
   toolchain compatibility. • How on NRP: • Launch KubeVirt VMs in a region near Linstor for
   fast disks; request GPU passthrough on VFIO nodes (nautilus.io/vfio=true) and attach
   nvidia.com/\* device in the VM spec. ￼ • For interactive GUI performance, use the GUI
   Desktop (Selkies) pattern or a Coder desktop and tunnel ports as needed. ￼

Tips to turn these into slides/demos • For live demos without kubectl, use JupyterHub (quick
spawn) or Coder (more control, persistent workspace, FPGA templates). ￼ • For datasets, prefer
S3 (scale) over kubectl cp; consider Globus if data sits at another site. ￼ • Respect policy
limits: interactive pods ≤ 6 h, Deployments purged after ~2 weeks unless whitelisted; A100
access requires a request. ￼

## References (these links survive copy/paste)

• [R1] A New Way to Manage Resources on the NRP (hierarchy → namespaces) —
<https://nationalresearchplatform.org/documentation/userdocs/start/hierarchy/> • [R2] Getting
started: sign‑in & portal — <https://nrp.ai/documentation/userdocs/start/getting-started/> •
[R3] CILogon (federated SSO) — <https://www.cilogon.org/home> • [R4] Authentik (NRP admin doc)
— <https://nrp.ai/documentation/admindocs/cluster/authentik/> • [R5] JupyterHub Service
(hosted) —
<https://nationalresearchplatform.org/documentation/userdocs/jupyter/jupyterhub-service/> •
[R6] Using Coder — <https://nrp.ai/documentation/userdocs/coder/coder/> • [R7] Using Nautilus
(resource summary, multi‑site) —
<https://nationalresearchplatform.org/documentation/userdocs/start/using-nautilus/> • [R8]
Running batch jobs —
<https://nationalresearchplatform.org/documentation/userdocs/tutorial/jobs/> • [R9] Scheduling
(YuniKorn transition) —
<https://nationalresearchplatform.org/documentation/userdocs/running/scheduling/> • [R10] MIG
GPUs (admin) — <https://nationalresearchplatform.org/documentation/admindocs/cluster/mig-gpus/>
• [R11] Cloud AI 100 Ultra on NRP (8 cards → 32 devices) —
<https://nationalresearchplatform.org/documentation/userdocs/ai/qaic/> • [R12] NRP‑Managed LLMs
(LibreChat, OpenAI‑compatible endpoint) —
<https://nationalresearchplatform.org/documentation/userdocs/ai/llm-managed/> • [R13] Envoy AI
Gateway (project docs) — <https://aigateway.envoyproxy.io/docs/> • [R14] NRP‑Managed vector
database (Milvus) — <https://nrp.ai/documentation/userdocs/ai/vector-database/> • [R15]
Deployed Services (Ray, Dask, Kubeflow; GitLab/Nextcloud/Overleaf) —
<https://nrp.ai/documentation/userdocs/start/resources/> • [R16] Virtualization – general
(KubeVirt storage locality; Linstor) —
<https://nationalresearchplatform.org/documentation/userdocs/running/virtualization-general/> •
[R17] KubeVirt GPU (VFIO) admin steps —
<https://nationalresearchplatform.org/documentation/admindocs/cluster/kubevirt-gpu/> • [R18]
CephFS / RBD storage classes —
<https://nationalresearchplatform.org/documentation/userdocs/storage/ceph/> • [R19] Local NVMe
scratch — <https://nationalresearchplatform.org/documentation/userdocs/storage/local/> • [R20]
Moving Data (S3/Nextcloud; rclone) —
<https://nationalresearchplatform.org/documentation/userdocs/storage/move-data/> • [R21] Ceph
S3 (admin) — <https://nationalresearchplatform.org/documentation/admindocs/storage/ceph-s3/> •
[R22] Globus Connect on NRP —
<https://nationalresearchplatform.org/documentation/userdocs/running/globus-connect/> • [R23]
Exposing HTTP / Ingress —
<https://nationalresearchplatform.org/documentation/userdocs/running/ingress/> • [R24]
SENSE/Multus (L2 path provisioning) —
<https://nationalresearchplatform.org/documentation/admindocs/cluster/sense-multus/> • [R25]
Visualization links (Grafana dashboards) —
<https://nationalresearchplatform.org/documentation/admindocs/links/vis/> • [R26] Cluster
policies (GPU utilization guidance) —
<https://nationalresearchplatform.org/documentation/userdocs/start/policies/> • [R27] Long idle
pods (limits, no GPU for idle deployments) —
<https://nrp.ai/documentation/userdocs/running/long-idle/> • [R28] Docs index / “Getting
Started with Nautilus Cluster” — <https://nationalresearchplatform.org/documentation/> • [R29]
NRP training sessions — <https://nationalresearchplatform.org/training/> • [R30] ESnet SmartNIC
(overview) — <https://nationalresearchplatform.org/documentation/userdocs/fpgas/esnet/> • [R31]
ESnet SmartNIC (running tutorial) —
<https://nationalresearchplatform.org/documentation/userdocs/fpgas/esnet_running/>
