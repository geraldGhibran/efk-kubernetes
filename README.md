# efk-kubernetes

`kops create cluster --zones=ap-southeast-1a --node-count=2 --master-count=1 --node-size=t2.medium --master-size=t2.large --name=${KOPS_CLUSTER_NAME} --ssh-public-key=~/.ssh/id_rsa.pub`

`kubectl create -f kube-logging.yaml`

`kubectl create -f elasticsearch_svc.yaml`

`kubectl create -f elasticsearch_statefulset.yaml`

`kubectl rollout status sts/es-cluster --namespace=kube-logging`

`kubectl create -f kibana.yaml`

`kubectl create -f fluentd.yaml`

## Create ingress
 `kubectl apply -f https://raw.githubusercontent.com/kubernetes/ingress-nginx/nginx-0.27.1/deploy/static/mandatory.yaml`
 
 `kubectl apply -f https://raw.githubusercontent.com/kubernetes/ingress-nginx/nginx-0.27.1/deploy/static/provider/aws/service-l4.yaml`
 
`kubectl apply -f https://raw.githubusercontent.com/kubernetes/ingress-nginx/nginx-0.27.1/deploy/static/provider/aws/patch-configmap-l4.yaml`

`kubectl apply -f p-p-ekf-ingress.yaml`

`kubectl create -f counter.yaml`


https://www.digitalocean.com/community/tutorials/how-to-set-up-an-elasticsearch-fluentd-and-kibana-efk-logging-stack-on-kubernetes
