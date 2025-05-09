# Тема: Канонічні форми булевих функцій. Проектування комбінаційних схем.

## Теоретичні відомості

Оскільки в алгебрі Буля функції **І** та **АБО** є дуальними, існують дві канонічні форми булевих функцій:
- **Доконана диз'юнктивна нормальна форма (ДДНФ)**;
- **Доконана кон'юнктивна нормальна форма (ДКНФ)**.

Для визначення ДДНФ наведемо такі означення:
- Будь-яка послідовність аргументів, об'єднаних однією операцією, називається **термом**.
- Змінна із запереченням або без заперечення в термі називається **буквою**.
- Кількість букв в термі називається **рангом терма**.
- Функція, що приймає одиничне значення тільки на одному наборі аргументів, називається **конституентою одиниці**.
- Кількість конституент одиниці дорівнює кількості наборів, тобто **2ⁿ**, де *n* — кількість аргументів.

Для перемикальних функцій від трьох аргументів `f = (x₃, x₂, x₁)` конституенти одиниці наведені у таблиці нижче.

### Таблиця 2.1 – Конституенти одиниці

| x₃ | x₂ | x₁ | C₀ | C₁ | C₂ | C₃ | C₄ | C₅ | C₆ | C₇ |
|:--:|:--:|:--:|:--:|:--:|:--:|:--:|:--:|:--:|:--:|:--:|
| 0 | 0 | 0 | 1 | 0 | 0 | 0 | 0 | 0 | 0 | 0 |
| 0 | 0 | 1 | 0 | 1 | 0 | 0 | 0 | 0 | 0 | 0 |
| 0 | 1 | 0 | 0 | 0 | 1 | 0 | 0 | 0 | 0 | 0 |
| 0 | 1 | 1 | 0 | 0 | 0 | 1 | 0 | 0 | 0 | 0 |
| 1 | 0 | 0 | 0 | 0 | 0 | 0 | 1 | 0 | 0 | 0 |
| 1 | 0 | 1 | 0 | 0 | 0 | 0 | 0 | 1 | 0 | 0 |
| 1 | 1 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 1 | 0 |
| 1 | 1 | 1 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 1 |

Аналітичний запис конституенти одиниці є кон'юнктивним термом n-го рангу. Відповідно до таблиці 2.1 надамо аналітичний запис конституент одиниці:

- C₀ = x̅₃ x̅₂ x̅₁
- C₁ = x̅₃ x̅₂ x₁
- C₃ = x̅₃ x₂ x₁
- C₄ = x₃ x̅₂ x̅₁
- C₅ = x₃ x̅₂ x₁
- C₇ = x₃ x₂ x₁

Таким чином, ДДНФ — це диз'юнкція конституент одиниці, що відповідають наборам, на яких функція приймає одиничні значення, тобто:

Fₓₓₙₙₓ = ∨ᵢ (Cᵢ αᵢ),   (2.1)

де αᵢ Є {0,1} — значення функції на i-му наборі.

# Хід роботи
Задане число 2211 = 100010100011 у двійковій системі.

### Таблиця 2.2 – Таблиця істинності

| x₄ | x₃ | x₂ | x₁ | f₁ | f₂ |
|----|----|----|----|----|----|
| 0  | 0  | 0  | 0  | h₉  | 0  |
| 0  | 0  | 0  | 1  | 0   | 0  |
| 0  | 0  | 1  | 0  | h₁  | 1  |
| 0  | 0  | 1  | 1  | 1   | 1  |
| 0  | 1  | 0  | 0  | 0   | 0  |
| 0  | 1  | 0  | 1  | h₅  | 0  |
| 0  | 1  | 1  | 0  | h₂  | 1  |
| 0  | 1  | 1  | 1  | 1   | 1  |
| 1  | 0  | 0  | 0  | 0   | 0  |
| 1  | 0  | 0  | 1  | h₃  | 0  |
| 1  | 0  | 1  | 0  | 0   | 0  |
| 1  | 0  | 1  | 1  | h₄  | 0  |
| 1  | 1  | 0  | 0  | h₆  | 1  |
| 1  | 1  | 0  | 1  | 0   | 0  |
| 1  | 1  | 1  | 0  | h₇  | 0  |
| 1  | 1  | 1  | 1  | h₈  | 1  |

## Побудова комбінаційної схеми ДДНФ

$$
y_{1ДДНФ} = \overline{x_4} \, \overline{x_3} \, x_2 \, \overline{x_1} \cup \overline{x_4} \, \overline{x_3} \, x_2 \, x_1 \cup \overline{x_4} \, x_3 \, x_2 \, \overline{x_1} \cup \overline{x_4} \, x_3 \, x_2 \, x_1 \cup x_4 \, x_3 \, \overline{x_2} \, \overline{x_1} \cup x_4 \, x_3 \, x_2 \, x_1
$$

$$
y_{1ДДНФ} = 2 \cup 3 \cup 6 \cup 7 \cup 12 \cup 15
$$

### Рис. 1. Комбінаційна схема для ДДНФ
![Рис. 1. Комбінаційна схема для ДКНФ](./combinational-scheme-for-DDNF.png)

### Рис. 2. Таблиця істинності комбінаційної схеми для ДДНФ

![Рис. 2.Таблиця істинності комбінаційної схеми для ДКНФ](./truth-table-of-a-combinational-circuit-for-DDNF.png)


## Побудова комбінаційної схеми ДКНФ

$$
y_{1ДДНФ} = \overline{x_4} \, \overline{x_3} \, x_2 \, \overline{x_1} \cup \overline{x_4} \, \overline{x_3} \, x_2 \, x_1 \cup \overline{x_4} \, x_3 \, x_2 \, \overline{x_1} \cup \overline{x_4} \, x_3 \, x_2 \, x_1 \cup x_4 \, x_3 \, \overline{x_2} \, \overline{x_1} \cup x_4 \, x_3 \, x_2 \, x_1
$$

$$
y_{1ДДНФ} = 2 \cup 3 \cup 6 \cup 7 \cup 12 \cup 15
$$

### Рис. 3. Комбінаційна схема для ДКНФ
![Рис. 3. Комбінаційна схема для ДКНФ](./combinational-scheme-for-DCNF.jpg)

### Рис. 4. Таблиця істинності комбінаційної схеми для ДКНФ

![Рис. 4.Таблиця істинності комбінаційної схеми для ДКНФ](./truth-table-of-a-combinational-circuit-for-DCNF.jpg)


## Використане програмне забезпечення
Для побудови та аналізу комбінаційних схем та канонічних форм булевих функцій було використано програму AFDK.
