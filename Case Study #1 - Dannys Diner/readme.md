# 🍜 Case Study #1 - Danny's Diner

## 📋 Problem biznesowy
Danny chce lepiej poznać swoich klientów: jak często odwiedzają restaurację i jakie są ich ulubione dania.

## 🏗️ Model danych (ERD)
![Diagram ERD](link_do_obrazka_z_diagramem)

## 💻 Rozwiązania zadań

### Q1: Jaka jest łączna kwota, którą każdy klient wydał?
**Logika:** Połączyłam tabelę `sales` z `menu`, aby uzyskać ceny produktów, a następnie pogrupowałam dane po kliencie.

```sql
SELECT customer_id, SUM(price) AS total_spent
FROM sales
JOIN menu ON sales.product_id = menu.product_id
GROUP BY customer_id;
