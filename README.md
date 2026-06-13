# MiniShop REST API

![CI Pipeline](https://github.com/diegohuacca-hub/minishop/actions/workflows/ci.yml/badge.svg)

API REST para gestión de productos desarrollada con Spring Boot.

## Tecnologías
- Java 17
- Spring Boot 3.x
- H2 (base de datos en memoria para pruebas)
- JUnit 5 + Mockito
- Maven

## Ejecutar localmente
```bash
mvn clean verify
```

## Pipeline de CI
Cada push a main ejecuta automáticamente:
1. Compilación del proyecto
2. Pruebas unitarias
3. Pruebas de integración
4. Publicación del reporte de pruebas
