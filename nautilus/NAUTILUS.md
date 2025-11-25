# CENIC AIR Notes

SSU - namespace nrp/ssu/ssu-ee/ordingj

## Documentation & Links

<https://jupyterhub-west.nrp-nautilus.io/hub/spawn/ordingj@sonoma.edu>

<https://nationalresearchplatform.org/documentation/userdocs/jupyter/jupyter-pod/>

<https://nrp.ai/userinfo/>

<https://coder.nrp-nautilus.io/templates/universal/workspace>

<https://gitlab.nrp-nautilus.io/ordingj>

<https://librechat.nrp-nautilus.io/>

<https://github.com/nrp-nautilus/fall25training>

<https://cenic.org/blog/cenic-members-enable-data-driven-agriculture-farm-to-table-in-a-changing-environment>

<https://kubernetes.io/docs/reference/kubectl/quick-reference/>

<https://kubernetes.io/docs/tutorials/kubernetes-basics/create-cluster/cluster-intro/>

## Useful Commands

curl -H "Authorization: Bearer 9aTdiDBqP5DZHkgImj8JMjhRCzVXqUAa"
<https://ellm.nrp-nautilus.io/v1/models>

helm install vllm vllm/vllm-stack \
 -f tutorials/assets/values-01-minimal-example.yaml \
 --skip-crds

helm install vllm substratusai/vllm \
 -n ordingj --create-namespace \
 --set model=mistralai/Mistral-7B-Instruct-v0.2 \
 --set resources.limits."nvidia\.com/gpu"=1 \
 --set service.type=ClusterIP

## kubernetes commands

kubectl config set-context nautilus --namespace=<YOUR_NAMESPACE>

kubectl config get-contexts

kubectl get pods -n ordingj

kubectl create -f tensorflow-pod.yaml

kubectl describe pod sd-tools -n ordingj

kubectl logs sd-stable-diffusion-0 -n ordingj -c stable-diffusion-stable-diffusion -f

kubectl delete pod sd-stable-diffusion-0 -n ordingj

kubectl apply -f sd-ss.yaml -n ordingj

kubectl exec -it sd-tools -n ordingj -- ls /models

kubectl cp openai/clip-vit-large-patch14 ordingj/sd-tools:/models/clip-vit-large-patch14

kubectl scale statefulset sd-stable-diffusion -n ordingj --replicas=1
