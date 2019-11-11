# for secret
-CREATE-SECRETS: cd secrets && for fname in `ls *.example`; do if [ ! -e $fname ]; then cp $fname `basename $fname .example`; fi done

# for helm
-helm-install-tiller: helm init --history-max 200
-helm-version: helm version
-helm-repo-update: helm repo update
-helm-apply-oauth2-proxy: helm upgrade sad-sheep --install -f helm/oauth2-proxy.config.yml stable/oauth2-proxy
-helm-apply-mailhog: helm upgrade solemn-badger --install -f helm/mailhog.config.yml stable/mailhog

# for k8s
-k8s-apply: kubectl apply -f k8s/main.yml
