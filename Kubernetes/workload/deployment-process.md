### Kubernetes의 Deployment가 생성될 경우 통신, 프로세스를 설명하시오.
먼저 디플로이먼트 내 어플리케이션은 stateless application으로 가정하며 kubectl로 apply하는 과정을 설명하겠습니다.  
kubectl에서 디플로이먼트 생성 명령을 전달할 경우 해당 컨피그에 등륵된 클러스터의 마스터 노드가 호출됩니다.  
해당 마스터 노드 내 kube api server에서 k8s 스케줄러에 요청된 잡이 등록됩니다.  
스케줄러를 통해 대상이 되는 노드의 kubelet과 통신하여 deployment, replicaSet, Pod를 생성합니다.