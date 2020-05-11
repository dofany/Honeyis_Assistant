# Honeyis_Assistant

### 프로젝트 참여  
> Web_server: cafeCoder  
> DataBase: dofany


### 애자일 소프트웨어 개발 선언  
우리는 소프트웨어를 개발하고, 또 다른 사람의 개발을 도와주면서 소프트웨어 개발의 더 나은 방법들을 찾아가고 있다.   
이 작업을 통해 우리는 다음을 가치 있게 여기게 되었다:   

공정과 도구보다 **개인과 상호작용을**   
포괄적인 문서보다 **작동하는 소프트웨어를**   
계약 협상보다 **고객과의 협력을**   
계획을 따르기보다 **변화에 대응하기를**  

가치 있게 여긴다.
이 말은, 왼쪽에 있는 것들도 가치가 있지만, 우리는 오른쪽에 있는 것들에 더 높은 가치를 둔다는 것이다.   
Kent Beck, Mike Beedle, Arie van Bennekum, Alistair Cockburn, Ward Cunningham, Martin Fowler,   
James Grenning, Jim Highsmith, Andrew Hunt, Ron Jeffries, Jon Kern, Brian Marick, Robert C. Martin   
Steve Mellor, Ken Schwaber, Jeff Sutherland, Dave Thomas  
© 2001, 상기 저자들   
이 선언문은 어떤 형태로든 자유로이 복사할 수 있지만, 본 고지와 함께 전문으로서만 가능하다.   

### 2020-05-09 요구사항   
> 요구사항 1  

기본적인 베이스
전날 재고조사 -&gt; 다음날 물건이 얼마나 나가는지 모르지만,
물건을 사용하면, 재고가 거기서 삭감이 될 것이다.
중요한 것은 아침에 거래처에서 받아오는 물량도 재고에 플러스가 된다.
총 재고에서 그날 빼야 할 물건을 마이너스 시켜야 한다.  

> 요구사항 2

송장 뺄 때, 엑셀이 있는데, 주문확인 엑셀을 업로드를 하면, 혹은 입력을 하면,
거기에서 재고 수량이 파악된 개수를 입력해 놓으면, 시간 차례로 어디까지 
뺄 수 있는지 자동으로 나왔으면 좋겠다. (오래된 시간순으로)

직접 주문 건수가 많은 상품 우선으로 뺀다. 그러니 수량에 대한 우선순위는 제외한다.

출력 이전에 표시되었으면 좋겠다.

나갈 수 있는 애들이 색깔로 표시되던가, 표시되었으면 좋겠다.
그러면 그것들을 뽑으면 된다.    

### 2020-05-11 분석  
> 요구사항 1에 대한 분석  

* 첫 1회, 모든 재고에대한 정보를 입력받아 데이터베이스에 저장한다. 
* 사용한 물건에 대해 재고 데이터베이스를 수정한다.   
* 받아온 재고에대한 입력을 받는다.  

> 요구사항 2에 대한 분석   

* 엑셀 파일을 입력받았을 때, 현재 데이터베이스의 수량과 비교하여, 발송이 가능한 항목을 추린다.   
단, 시간의 오름차순으로 정렬한다.  

* 발송이 가능한 항목이 하이라이트 처리 되었으면 좋겠다.  
