\# MiniShop — Lab 12: Pruebas de Integración



\*\*Curso:\*\* Construcción y Pruebas de Software — IV Ciclo  

\*\*Alumno:\*\* Diego Huacca Ccaso  

\*\*Docente:\*\* Mg. Edwin Córdova Benavente  

\*\*Semana:\*\* 12



\---



\## Descripción



API REST para gestionar productos de una tienda, desarrollada con Spring Boot.  

El objetivo del laboratorio es implementar pruebas de integración en tres capas.



\---



\## Tecnologías



\- Java 17

\- Spring Boot 3.2.5

\- Spring Data JPA

\- H2 Database (en memoria)

\- Lombok

\- JUnit 5 + MockMvc + Mockito



\---



\## Estructura del proyecto



src/

├── main/java/com/tecsup/minishop/

│   ├── controller/ProductController.java

│   ├── controller/GlobalExceptionHandler.java

│   ├── service/ProductService.java

│   ├── repository/ProductRepository.java

│   └── model/Product.java

└── test/java/com/tecsup/minishop/

├── controller/ProductControllerIntegrationTest.java

├── repository/ProductRepositoryIntegrationTest.java

└── service/ProductServiceIntegrationTest.java


---



\## Pruebas de integración



| Clase | Anotación | Tests |

|---|---|---|

| ProductRepositoryIntegrationTest | `@DataJpaTest` | 4 |

| ProductServiceIntegrationTest | `@SpringBootTest` + `@MockBean` | 5 |

| ProductControllerIntegrationTest | `@SpringBootTest` + `MockMvc` | 4 |



\---



\## Resultados



\### mvn compile

!\[compile](evidencias/compile.png)



\### Estructura del proyecto

!\[estructura](evidencias/estructura.png)



\### mvn test — 13 tests en verde

!\[test](evidencias/test.png)



\---



\## Conclusiones



1\. Comprendí que las pruebas de integración complementan a las unitarias verificando que los contratos entre capas funcionen correctamente.

2\. Apliqué `@DataJpaTest` para probar el repositorio de forma aislada contra H2 sin levantar el contexto completo de Spring.

3\. Utilicé `@MockBean` junto con `@SpringBootTest` para verificar la lógica del servicio sin depender de la base de datos real.

4\. Implementé pruebas end-to-end con `MockMvc` que recorren el flujo completo desde la petición HTTP hasta la base de datos H2 y de vuelta.

5\. Identifiqué que en Spring Boot 3.x es necesario un `@RestControllerAdvice` para convertir excepciones de negocio en respuestas HTTP correctas validables desde los tests.

