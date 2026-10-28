# file-service-manifests

file-service의 쿠버네티스 배포 설정. 로컬 kubeadm 클러스터와 EKS에 같은 base를 overlay로 나누어 적용함.

- apps/file-service/base: Deployment, Service(ClusterIP), ConfigMap, Secret(예시값), 공통 label
- apps/file-service/overlays/local: Ingress(nginx, file.local), HPA, replicas, 이미지 태그
- apps/file-service/overlays/eks: (Kubernetes 활용 주제에서 추가)
- platform/local: MetalLB IP 풀, Namespace dev, RBAC
- examples: 비교용 단독 Pod

적용: kubectl apply -k apps/file-service/overlays/local
