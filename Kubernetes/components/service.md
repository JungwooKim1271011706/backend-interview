### Kubernetes 시스템의 구성 요소인 Service는 무엇인가요.
쿠버네티스의 서비스는 네트워크 어플리케이션으로 클러스터 내 서비스를 외부 네트워크로 연결하는 역할을 합니다.  
Selector를 이용하여 제공하고자 하는 서비스를 지정하며  
IP + Port 조합을 이용한 EndPoint를 외부로 제공하기에 Pod의 Private ip가 변경되어도 서비스는 변경되지 않습니다.