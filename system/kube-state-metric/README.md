helm repo add prometheus-community https://prometheus-community.github.io/helm-charts
helm repo update

helm delete kube-state-metrics

helm upgrade -i -n monitoring kube-state-metrics prometheus-community/kube-state-metrics