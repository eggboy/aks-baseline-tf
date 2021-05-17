# aks-baseline-tf

helm install nginx-ingress ingress-nginx/ingress-nginx \
    --namespace ingress \
    --set controller.replicaCount=2 \
    --set controller.service.externalTrafficPolicy="Local" \
    --set controller.nodeSelector."beta\\.kubernetes\\.io/os"=linux \
    --set defaultBackend.nodeSelector."beta\\.kubernetes\.io/os"=linux \
    --set controller.service.loadBalancerIP="100.64.2.4" \
    --set controller.service.annotations."service\\.beta\\.kubernetes\\.io/azure-load-balancer-internal"=true \
    --set controller.service.annotations."service\\.beta\\.kubernetes\\.io/azure-load-balancer-internal-subnet"="jayprodsvcsubnet"
    
