# ECE 565 Project - Presentation on NRP

## What is NRP?

## What is Nautilus?

"The NRP is a community-owned research and education platform connecting researchers and
educators to foster collaboration, accelerate innovation, and share resources. Supported by
over 50 institutions, including leadership from UC San Diego, the University of
Nebraska-Lincoln, and the Massachusetts Green High Performance Computing Center, the NRP
provides access to cutting-edge technologies in AI, high-performance computing, data storage,
and networking. Open to all nonprofit higher education institutions, from community colleges to
top research universities, the NRP advances learning and scientific breakthroughs with support
from the U.S. National Science Foundation, Department of Energy, and Department of Defense
among others."

![Nodemap](nodemap.png)

## How Do I Access It?

### Getting Started

Open <https://nrp.ai/>, click on the Log In button at the top right corner.

- Use your SSU credentials to log in (via CILogon).

After logging in, contact your professor to be added to the 'SSU-EE' namespace. You can verify
your nameserver access by visiting <https://nrp.ai/namespaces/>.

Make sure you read the cluster policies before starting to use it:

- Read the NRP Acceptable Use Policy (AUP). <https://nationalresearchplatform.org/NRP-AUP.pdf>
- Read the Cluster Policies.
  <https://nationalresearchplatform.org/documentation/userdocs/start/policies/>

#### Installing Kubernetes

Install the Kubernetes command-line tool, kubectl.

Install kubelogin plugin - must do this step for authentication to work.

Save the config file as config (without any extension) and put it in your $HOME/.kube folder.
<https://nationalresearchplatform.org/config>

Issue the kubectl command. It will authenticate via CiLogon by opening the browser window, and
close one in the end.

kubectl get nodes

Verify cluster access using kubectl. Run the following command on your terminal.

kubectl get pods -n <YOUR_NAMESPACE>

## Demonstration - Jupyter Notebook TTS

Navigate to NRP's JupyterHub at <https://jupyterhub-west.nrp-nautilus.io/>

## Resources

- [Nautilus Documentation](http://nationalresearchplatform.org/documentation)
