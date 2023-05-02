### Q1. GC의 영역에 대해서 설명해보세요.
 - GC의 영역에는 Young Area와 , Old Area가 있습니다. Young Area는 Eden과 Survivor로 Area를 나누어 관리하고 있습니다.


### Q2. 그렇게 나누어서 관리하는 이유는 무엇인가요?
 - 기본적으로 GC는 두 가지 가설을 기준으로 동작합니다. 첫쨰는 "Object는 생성 후 금방 Garbage 상태가 된다." 이며, 둘째는 "Older Object가 Younger Object를 참조할 일은 드물다" 입니다.
 - 이에 따라 Older Object는 Old Area에, 참조 빈도가 낮고 금방 Garbage 상태가 되는 Young Object는 Young Area로 분류하도록 공간을 나누었습니다.
 - 추가로, young area의 Eden은 Object 할당만을 위한 공간으로, GC가 빈번하게 이루어지며 그로 인한 heap 단편화를 최소화하기 위한 공간이며, GC 당시에 Live한 Object는 Garbage가 될 확률이 적으므로 따로 관리하기 위해 Survivor area가 할당되었습니다.
