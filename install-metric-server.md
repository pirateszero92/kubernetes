    wget kubectl https://github.com/kubernetes-sigs/metrics-server/releases/latest/download/components.yaml

Edit file components.yaml

    nano  components.yaml

add to line -->   - --kubelet-insecure-tls

spec:
 containers:
 - args:
   - --cert-dir=/tmp
   - --secure-port=10250
   - --kubelet-insecure-tls

save and then run 

    kubectl apply -f components.yaml

run

    kubectl top pods
    kubectl top nodes

