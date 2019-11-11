# for secret
-CREATE-SECRETS: cd secrets && for fname in `ls *.example`; do if [ ! -e $fname ]; then cp $fname `basename $fname .example`; fi done

# setup
-setup-install-tiller: helm init --history-max 200
-setup-version: helm version
-setup-repo-update: helm repo update

# for helm
-helm-apply-oauth2-proxy: helm upgrade symdon --install -f helm/oauth2-proxy.config.yml -f secrets/helm.yml stable/oauth2-proxy 
-helm-apply-mailhog: helm upgrade symdon-mailhog --install stable/mailhog

# for k8s
-k8s-apply: kubectl apply -f k8s/main.yml

# for ingress
-ingress-install: helm upgrade ing --install stable/nginx-ingress
-ingress-apply: kubectl apply -f ingress/main.yml


# for secrets
-secrets: kubectl apply -f secrets/k8s.yml
