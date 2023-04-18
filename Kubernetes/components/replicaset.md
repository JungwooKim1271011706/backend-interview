### K8S의 ReplicaSet은 무엇인가요.
레플리카셋은 파드의 집합으로 마스터 노드의 Replication Controller에 의해 모니터링되는 요소입니다.  
컨드롤러는 High Availability를 지키기 위해 레플리카셋을 모니터링하며  
레플리카셋의 파드에 이슈가 발생할 경우 정책에 따라 폐기, 재기동 처리를 수행한다.  
이때 모니터링은 메타데이터에 정의된 Selector.matchLabels에 따라 동작한다.