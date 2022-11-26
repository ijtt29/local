# 설치 가이드


metallb-system namespace에서 관리하기 위해 namespace 생성
```
kubectl create namespace metallb-system
```

kube-proxy ipvs 모드를 사용하는 경우 
```
kubectl get configmap kube-proxy -n kube-system -o yaml | \
sed -e "s/strictARP: false/strictARP: true/" | \
kubectl apply -f - -n kube-system
```

helm 으로 설치
```
helm repo add metallb https://metallb.github.io/metallb
helm repo update

helm upgrade -i -n metallb-system metallb metallb/metallb -f values.yaml
```

IPAddressPool, L2Advertisement 설치
```
kubectl apply -f IPAddressPool.yaml
```


# 참고
* https://kubernetes.github.io/ingress-nginx/deploy/baremetal/#a-pure-software-solution-metallb
* https://metallb.universe.tf/configuration/