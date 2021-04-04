1-Arraylist:
  1-1-정의:List 인터페이스를 상속받은 클래스로 크기가 가변적으로 변하는 선형리스트
  
  1-2-특징:크기가 가변적으로 변함,한번 생성되면 크기가 변하지 않는 배열과는 달리 ArrayList는
  객체들이 추가되어 저장 용량을 초과한다면 자동으로 부족한 크기만큼 저장 용량이 늘어난다.
  
  1-3-사용방법:
  
    선언: ArrayList<String> 이름=new ArrayList<>();
    
    값 추가:stringArrayList.add("넣을 내용");
    
    값 삭제:stringArrayList.remove(없앨 변수의 순서(예:0을 넣으면 0번째칸 값이 삭제된다.);
    
2-Hashmap:
  2-1-정의:key와 value의 쌍으로 이루어진 데이터를 보관하는 Map의 일종
  
  2-2-특징:key와 value가 한 쌍으로 이루어짐,값이 순서대로 들어감
  
  2-3-사용방법:
  
    선언: HashMap<String,Integer> 이름=new HashMap<>();
  
    값 추가: 이름.put("넣을려는 key",넣을려는 value);
    
    값 삭제: 이름.remove("삭제하고싶은 key");
    
    이상 오늘은java의 Arraylist와 HashMap의 대해서 정리해 보았다.
