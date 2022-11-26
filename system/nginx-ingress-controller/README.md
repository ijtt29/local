# 설치 가이드

ingress-nginx namespace에서 관리하기 위해 namespace 생성
```
kubectl create namespace ingress-nginx
```

helm 으로 설치
```
helm repo add ingress-nginx https://kubernetes.github.io/ingress-nginx
helm repo update

helm upgrade -i -n ingress-nginx ingress-nginx ingress-nginx/ingress-nginx -f values.yaml
```

# 참고
* https://github.com/kubernetes/ingress-nginx/
* https://docs.nginx.com/nginx-ingress-controller/intro/how-nginx-ingress-controller-works/
* https://www.nginx.com/blog/inside-nginx-how-we-designed-for-performance-scale/