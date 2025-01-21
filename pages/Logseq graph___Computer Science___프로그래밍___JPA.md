deck:: 🌐 Logseq graph/📂 Computer Science/📂 프로그래밍/📖 JPA

- JPA에서 EntityManager를 사용하여 JPQL을 작성하는 메서드는? #card
	- createQuery()
	  #+BEGIN_EXTRA
	  ```java
	  // 예시1: 타입 지정
	  TypedQuery<Member> query = em.createQuery("SELECT m FROM Member m", Member.class);
	  
	  // 예시2: 파라미터 바인딩
	  TypedQuery<Member> query = em.createQuery("SELECT m FROM Member m WHERE m.name = :name", Member.class)
	      .setParameter("name", "kim");
	  ```
	  #+END_EXTRA
- JPA의 EntityManager에서 `createQuery()` 또는 `createNativeQuery()` 메서드를 사용하여 JPQL/SQL을 작성할 때, 결과를 1개만 조회하고 싶으면 어떤 메서드를 사용해야 하는가? #card
	- getSingleResult()
	  #+BEGIN_EXTRA
	  ```java
	  // 예시
	  Member member = em.createQuery("SELECT m FROM Member m WHERE m.id = :id", Member.class)
	      .setParameter("id", 1L)
	      .getSingleResult();
	  ```
	  
	  주의점: 결과가 없거나 둘 이상이면 예외 발생
	  - NoResultException: 결과가 없는 경우
	  - NonUniqueResultException: 결과가 둘 이상인 경우
	  #+END_EXTRA
- JPA의 EntityManager에서 `createQuery()` 또는 `createNativeQuery()` 메서드를 사용하여 JPQL/SQL을 작성할 때, 결과를 여러 건 조회하고 싶으면 어떤 메서드를 사용해야 하는가? #card
	- getResultList()
	  #+BEGIN_EXTRA
	  ```java
	  // 예시1: 전체 조회
	  List<Member> members = em.createQuery("SELECT m FROM Member m", Member.class)
	      .getResultList();
	      
	  // 예시2: 조건부 조회
	  List<Member> members = em.createQuery("SELECT m FROM Member m WHERE m.age > :age", Member.class)
	      .setParameter("age", 20)
	      .getResultList();
	  ```
	  
	  참고: 결과가 없으면 빈 리스트 반환 (null이 아님)
	  #+END_EXTRA
- JPA의 EntityManager에서 `createQuery()` 또는 `createNativeQuery()` 메서드를 사용하여 JPQL/SQL을 작성할 때, 삭제나 수정 쿼리를 실행하는 메서드는? #card
	- executeUpdate()
	  #+BEGIN_EXTRA
	  ```java
	  // 예시1: 수정
	  int updatedCount = em.createQuery("UPDATE Member m SET m.age = m.age + 1 WHERE m.age >= :age")
	      .setParameter("age", 20)
	      .executeUpdate();
	      
	  // 예시2: 삭제
	  int deletedCount = em.createQuery("DELETE FROM Member m WHERE m.age < :age")
	      .setParameter("age", 20)
	      .executeUpdate();
	  ```
	  #+END_EXTRA
- EntityManager의 createQuery()와 createNativeQuery()의 차이는? #card
	- createQuery()는 JPQL을 사용하여 객체지향적인 쿼리를 작성하고 데이터베이스에 독립적입니다.
	  createNativeQuery()는 순수 SQL을 사용하여 특정 데이터베이스의 고유 기능을 활용할 수 있습니다.
	  #+BEGIN_EXTRA
	  ```java
	  // createQuery() 예시
	  String jpql = "SELECT m FROM Member m WHERE m.name = :name";
	  TypedQuery<Member> query = em.createQuery(jpql, Member.class);
	  
	  // createNativeQuery() 예시
	  String sql = "SELECT * FROM members WHERE name = ?";
	  Query query = em.createNativeQuery(sql, Member.class);
	  ```
	  #+END_EXTRA
- JPQL에서 페이징 처리는 어떻게 하는가? #card
	- setFirstResult()로 시작 위치를, setMaxResults()로 조회할 데이터 수를 지정합니다.
	  #+BEGIN_EXTRA
	  ```java
	  List<Member> members = em.createQuery("SELECT m FROM Member m ORDER BY m.age DESC", Member.class)
	      .setFirstResult(0)   // 시작 위치 (0부터 시작)
	      .setMaxResults(10)   // 조회할 데이터 수
	      .getResultList();
	  ```
	  #+END_EXTRA
- JPA의 EntityManager에서 getSingleResult() 메서드 사용 시 어떤 경우에 예외가 발생하나요? #card #incremental
	- 결과가 없는 경우 (NoResultException)
	- 결과가 둘 이상인 경우 (NonUniqueResultException)
	  #+BEGIN_EXTRA
	  ```java
	  // 예시: 단일 결과를 기대하는 쿼리
	  try {
	     Member member = em.createQuery("SELECT m FROM Member m WHERE m.id = :id", Member.class)
	         .setParameter("id", 1L)
	         .getSingleResult();
	  } catch (NoResultException e) {
	     // 결과가 없는 경우 처리
	  } catch (NonUniqueResultException e) {
	     // 결과가 둘 이상인 경우 처리
	  }
	  ```
	  #+END_EXTRA
- JPA의 EntityManager에서 getResultList() 메서드는 결과가 없을 때 어떤 값을 반환하나요? #card
	- null이 아닌 빈 리스트를 반환합니다.