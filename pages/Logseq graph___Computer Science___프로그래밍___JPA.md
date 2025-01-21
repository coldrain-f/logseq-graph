deck:: 🌐 Logseq graph/📂 Computer Science/📂 프로그래밍/📖 JPA

- JPA에서 EntityManager를 사용하여 JPQL을 작성하는 메서드는? #card
	- ```java
	  createQuery()
	  ```
- JPA의 EntityManager에서 `createQuery()` 또는 `createNativeQuery()` 메서드를 사용하여 JPQL/SQL을 작성할 때, 결과를 1개만 조회하고 싶으면 어떤 메서드를 사용해야 하는가? #card
	- ```java
	  getSingleResult()
	  ```
- JPA의 EntityManager에서 `createQuery()` 또는 `createNativeQuery()` 메서드를 사용하여 JPQL/SQL을 작성할 때, 결과를 여러 건 조회하고 싶으면 어떤 메서드를 사용해야 하는가? #card
	- ```java
	  getResultList()
	  ```
- JPA의 EntityManager에서 `createQuery()` 또는 `createNativeQuery()` 메서드를 사용하여 JPQL/SQL을 작성할 때, 삭제나 수정 쿼리를 실행하는 메서드는? #card
	- ```java
	  .executeUpdate()
	  ```