# postgres-keycloak

Nossa primeira configuração será um ConfigMap o qual possuirá as informações de acesso do banco e suas variáveis de ambiente e evitaremos replicação desses dados nos yaml’s posteriores.

Para aplicar o configmap, digite o comando abaixo:

```bash
kubectl apply -f postgres-config.yaml
```

Um PersistentVolume (PV) que é um pedaço de armazenamento no cluster que foi provisionado por um administrador ou provisionado dinamicamente usando as classes de armazenamento.

E um PersistentVolumeClaim (PVC) é uma solicitação de armazenamento por um usuário. PVCs consomem recursos de PV.

Para aplicar o PV e o PVC, digite o comando abaixo:

```bash
kubectl apply -f pv-pvc.yaml
```

