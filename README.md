# my-cicd-env
Gitops repo to build up ArgoCI/CD environment

## Changes needed for our environment

* `quick-start-postgres.yam`


  ```diff
  879a880,882
  >         env:
  >         - name: BASE_HREF
  >           value: /argo/
  ```

* `quick-start-postgres.yaml`

  Align all field of `namespace` in this manifest to `argo-events`
