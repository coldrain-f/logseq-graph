deck:: 🌐 Logseq graph/📂 Computer Science/📂 프로그래밍/📖 JPA

- JPA에서 EntityManager를 사용하여 JPQL을 작성하는 메서드는? #card
  id:: 678f3ea3-5568-4f54-8f2d-3273f90e95af
	- ```java
	  createQuery()
	  ```
- JPA의 EntityManager에서 `createQuery()` 또는 `createNativeQuery()` 메서드를 사용하여 JPQL/SQL을 작성할 때, 결과를 1개만 조회하고 싶으면 어떤 메서드를 사용해야 하는가? #card
  id:: 678f3ee9-d1df-495e-8193-5ca3e359874c
	- ```java
	  getSingleResult()
	  ```
- JPA의 EntityManager에서 `createQuery()` 또는 `createNativeQuery()` 메서드를 사용하여 JPQL/SQL을 작성할 때, 결과를 여러 건 조회하고 싶으면 어떤 메서드를 사용해야 하는가? #card
  id:: 678f408a-cc11-4913-9007-64eb93dcb679
	- ```java
	  getResultList()
	  ```
- JPA의 EntityManager에서 `createQuery()` 또는 `createNativeQuery()` 메서드를 사용하여 JPQL/SQL을 작성할 때, 삭제나 수정 쿼리를 실행하는 메서드는? #card
  id:: 678f40e4-8e9b-49b4-95b9-10be534e47a2
	- ```java
	  .executeUpdate()
	  ```