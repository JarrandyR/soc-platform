\# Preflight Checklist (Run Before Every Push)



\## 1) Kustomize build must succeed

kubectl kustomize .\\gitops\\clusters\\dev > $null

echo $LASTEXITCODE  # must be 0



\## 2) Vector config must validate

kubectl -n platform-wazuh exec wazuh-manager-0 -c vector -- vector validate --config-yaml /etc/vector/vector.yaml



\## 3) Pod health

kubectl -n platform-wazuh get pods



