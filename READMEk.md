-- ══════════════════════════════════════════
-- TechStore — Consultas Básicas SELECT
-- Autor: Carolina Povis Vinces
-- Fecha: 09/07/2026
-- ══════════════════════════════════════════
*/# SQL Select Fundamentals

## ¿Por qué es mala práctica usar `SELECT *` en producción?

Usar `SELECT *` puede ser útil para explorar una tabla durante el desarrollo, pero en un entorno de producción no es una buena práctica por varias razones:

1. **Rendimiento:** Trae todas las columnas de la tabla, incluso las que no se necesitan. Esto aumenta el consumo de memoria, el tráfico de red y puede hacer que las consultas sean más lentas.

2. **Mantenibilidad:** Si en el futuro se agregan o eliminan columnas de la tabla, las aplicaciones que usan `SELECT *` pueden verse afectadas sin que el desarrollador lo note.

3. **Seguridad:** Puede devolver información sensible (por ejemplo, datos personales o financieros) que la consulta realmente no necesitaba mostrar.

Por estas razones, es recomendable seleccionar únicamente las columnas que se van a utilizar.

---

## ¿Por qué son importantes los alias para un stakeholder no técnico?

Los alias permiten mostrar nombres de columnas más claros y fáciles de entender para personas que no conocen la estructura de la base de datos.

Por ejemplo, en lugar de mostrar: /*
SELECT total_amount
FROM sales;

--podemos escribir:


SELECT total_amount AS monto_total
FROM sales;
```

*/De esta manera, una persona del área de finanzas entiende inmediatamente que la columna representa el monto total de la venta, sin necesidad de conocer el nombre técnico `total_amount`.

Los alias mejoran la legibilidad de los reportes y facilitan la comunicación entre los equipos técnicos y de negocio./*
