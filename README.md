# my-cicd-env
Gitops repo to build up ArgoCI/CD environment

# Changes for my env

* `quick-start-postgres.yam`


  ```diff
  879a880,882
  >         env:
  >         - name: BASE_HREF
  >           value: /argo/
  ```

* ``

# Tips

```
{
. <(kubectl completion bash)
. <(flux completion bash)
alias k=kubectl
complete -F __start_kubectl k

export DOCKER_USER=<docker hub username>
export DOCKER_PASSWD=<docker hub password>
cat <<EOF > dockerconfig.json
{
  "auths": {
    "https://index.docker.io/v1/": {
      "auth": "$(echo -n "$DOCKER_USER:$DOCKER_PASSWD" | base64)"
    }
  }
}
EOF
k create secret generic regcred --from-file=dockerconfig.json -n argo-events
}
```