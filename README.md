# postgres-keycloak

Valide se o contexto do kubernetes está correto.

Nossa primeira configuração será um ConfigMap o qual possuirá as informações de acesso do banco e suas variáveis de ambiente e evitaremos replicação desses dados nos yaml’s posteriores.

```bash
kubectl apply -f postgres-config.yaml
```

Um PersistentVolume (PV) que é um pedaço de armazenamento no cluster que foi provisionado por um administrador ou provisionado dinamicamente usando as classes de armazenamento.

```bash
kubectl apply -f psql-pv.yaml
```

E um PersistentVolumeClaim (PVC) é uma solicitação de armazenamento por um usuário. PVCs consomem recursos de PV.

```bash
kubectl apply -f psql-claim.yaml
```

A criação de um deployment do PostgreSQL no Kubernetes envolve a definição de um manifesto do tipo Deployment para orquestrar os pods do PostgreSQL.

```bash
kubectl apply -f ps-deployment.yaml
```

No Kubernetes, um Service é utilizado para definir um conjunto lógico de Pods, permitindo que outros Pods dentro do cluster se comuniquem com esse conjunto sem a necessidade de conhecer os endereços IP específicos desses Pods.

```bash
kubectl apply -f ps-service.yaml
```

Depois de identificar o Pod do PostgreSQL, utilize o comando `kubectl exec` para se conectar ao Pod do PostgreSQL.

```bash
kubectl exec -it postgres-665b7554dc-cddgq -- psql -h localhost -U ps_user --password -p 5432 ps_db
```
