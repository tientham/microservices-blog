## Install NGINX-INGRESS

Ref: https://kubernetes.github.io/ingress-nginx/deploy/

[Obsolete]
kubectl apply -f https://raw.githubusercontent.com/kubernetes/ingress-nginx/nginx-0.30.0/deploy/static/mandatory.yaml
kubectl apply -f https://raw.githubusercontent.com/kubernetes/ingress-nginx/nginx-0.30.0/deploy/static/provider/cloud-generic.yaml

[Option1]
kubectl apply -f https://raw.githubusercontent.com/kubernetes/ingress-nginx/master/deploy/static/provider/cloud/deploy.yaml

[Option2]
helm repo add ingress-nginx https://kubernetes.github.io/ingress-nginx
helm install my-release ingress-nginx/ingress-nginx

### Trouble-shooting installation of NGINX-INGRESS in MACOs

If following lessions but unable to view posts.com -> probably you need to stop apache server preinstalled inside MACOs
TienTham:~ tientham\$ sudo apachectl stop

### Restart all deployments

TienTham:~ tientham\$ k rollout restart deployment comments-depl && k rollout restart deployment event-bus-depl && k rollout restart deployment moderation-depl && k rollout restart deployment posts-depl && k rollout restart deployment query-depl

### Fix install Skaffold on macOS Catalina:

sudo chown -R \$(whoami):admin /usr/local/_ && sudo chmod -R g+rwx /usr/local/_

### Run skaffold

TienTham:~ tientham\$ skaffold dev
