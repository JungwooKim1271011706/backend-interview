### Q. MongoDB의 특징은 무엇인가요?
대표적인 특징으로는 먼저 Document Oriented DB라는 것입니다.  
RDB처럼 스키마가 정해져 있지 않기 때문에 Document 내의 JSON Key-Value의 형태가 정해져 있지 않습니다.  
다만 MongoEngine ODM, ORM 라이브러리를 사용하여 RDB 처럼도 쓸 수 있습니다.  
개발자가 선택하여 적용이 가능하다는 장점이 있습니다.  
    
인덱싱도 MongoDB의 장점입니다.  
RDB도 동일하게 인덱스가 존재하지만 DBA, 개발자가 개입하여 설정, 작업해주어야합니다.  
MongoDB는 기본적으로 RDB의 PK 역할을하는 hash key 값인 '_id' 값을 관리하며 자동으로 해당 키에 인덱스를 설정합니다.  
  
MongoDB는 확장성이 뛰어납니다. RDB는 바로 Scale-up 하는게 쉽지 않습니다. 
단순히 스펙만 늘려서는 저장된 데이터에 반영되지 않기 때문입니다.
MongoDB는 샤드를 이용한 분산 시스템으로 구성되어 있어 보다 쉽게 확장이 가능합니다.  
  
레플리카를 이용한 HA 구성도 가능합니다.  
RDB는 안정성 높은 시스템을 구축하기 위해서 Master-Slave 구조를 많이 구성하는데 이는 데이터 동기화, Active-Standby 구조를 별도로 구성해야합니다.  
MongoDB는 레플리카를 추가해서 보다 안정성 높은 시스템 구성이 가능합니다.  
  
Aggregation 동작에 강점을 보입니다.  
aggregation은 RDB의 groupby, orderby와 같은 동작들을 말합니다.  
MongoDB에서는 이를 위해 aggregation pipeline, map-reduce, single-purpose aggregation의 3가지의 방법들을 제공합니다.
