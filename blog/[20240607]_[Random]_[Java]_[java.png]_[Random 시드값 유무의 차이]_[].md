Random 클래스를 활용해 난수를 생성하는 방법은 2가지다.

```java
Random random1 = new Random();
Random random2 = new Random(100);
```

위와 같이 2가지 방법이 있는데, Random 클래스 인스턴스를 생성할 때 인수를 넣는 것과 안 넣는 것은 무슨 차이가 있을까?

random1의 경우 난수 생성 시 '시스템 시간'을 기반으로 하는 임의의 시드(seed) 값이 사용되어 매번 실행할 때마다 다른 시드 값이 사용되므로, 매 실행 시 생성되는 난수 시퀀스가 달라진다. 어렵게 생각할 것 없이 항상 다른 난수가 생성된다는 것이다.

반면 random2의 경우 명시적으로 지정된 시드 값 `100`이 사용된다. 동일한 시드 값을 사용하면 항상 동일한 난수 시퀀스가 생성되고 여러 번 실행해도 항상 같은 난수 시퀀스가 생성되어 난수가 일정한 패턴으로 생성된다.

```java
Random random1 = new Random();
Random random2 = new Random(100);

System.out.println("=== 시드값 지정 X ===");
System.out.println(random.nextInt(10));
System.out.println(random.nextInt(10));
System.out.println(random.nextInt(10));

System.out.println();

System.out.println("=== 시드값 지정 O ===");
System.out.println(random2.nextInt(10));
System.out.println(random2.nextInt(10));
System.out.println(random2.nextInt(10));
```

위의 코드로 5번을 실행해 보았다.

![1.png](img/random_seed/1.png)

![2.png](img/random_seed/2.png)

![3.png](img/random_seed/3.png)

![4.png](img/random_seed/4.png)

![5.png](img/random_seed/5.png)