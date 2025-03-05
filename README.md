# Решения задач по математическому анализу

## Задача 9

**Решим систему уравнений тремя способами: методом Крамера, методом Гаусса и методом обратной матрицы.**

**Система уравнений:**
$$
\begin{cases}
x_1 + x_2 - 2x_3 = 1, \\
5x_1 + 3x_2 + x_3 = 1, \\
-x_1 - 2x_2 + x_3 = -3.
\end{cases}
$$

### 1. Метод Крамера

**Шаг 1: Найдем определитель матрицы системы $\Delta$.**

Матрица системы:
$$
A = \begin{pmatrix}
1 & 1 & -2 \\
5 & 3 & 1 \\
-1 & -2 & 1
\end{pmatrix}
$$

Определитель:
$$
\Delta = 1 \cdot (3 \cdot 1 - 1 \cdot (-2)) - 1 \cdot (5 \cdot 1 - 1 \cdot (-1)) + (-2) \cdot (5 \cdot (-2) - 3 \cdot (-1)) = 1 \cdot (3 + 2) - 1 \cdot (5 + 1) - 2 \cdot (-10 + 3) = 5 - 6 + 14 = 13
$$

**Шаг 2: Найдем определители $ \Delta_{x_1} $, $ \Delta_{x_2} $, $ \Delta_{x_3} $.**

$$
\Delta_{x_1} = \begin{vmatrix}
1 & 1 & -2 \\
1 & 3 & 1 \\
-3 & -2 & 1
\end{vmatrix} = 1 \cdot (3 \cdot 1 - 1 \cdot (-2)) - 1 \cdot (1 \cdot 1 - 1 \cdot (-3)) + (-2) \cdot (1 \cdot (-2) - 3 \cdot (-3)) = 5 - 4 - 14 = -13
$$

$$
\Delta_{x_2} = \begin{vmatrix}
1 & 1 & -2 \\
5 & 1 & 1 \\
-1 & -3 & 1
\end{vmatrix} = 1 \cdot (1 \cdot 1 - 1 \cdot (-3)) - 1 \cdot (5 \cdot 1 - 1 \cdot (-1)) + (-2) \cdot (5 \cdot (-3) - 1 \cdot (-1)) = 4 - 6 + 28 = 26
$$

$$
\Delta_{x_3} = \begin{vmatrix}
1 & 1 & 1 \\
5 & 3 & 1 \\
-1 & -2 & -3
\end{vmatrix} = 1 \cdot (3 \cdot (-3) - 1 \cdot (-2)) - 1 \cdot (5 \cdot (-3) - 1 \cdot (-1)) + 1 \cdot (5 \cdot (-2) - 3 \cdot (-1)) = -7 + 14 - 7 = 0
$$

**Шаг 3: Найдем решения.**

$$
x_1 = \frac{\Delta_{x_1}}{\Delta} = \frac{-13}{13} = -1, \quad x_2 = \frac{\Delta_{x_2}}{\Delta} = \frac{26}{13} = 2, \quad x_3 = \frac{\Delta_{x_3}}{\Delta} = \frac{0}{13} = 0
$$

**Ответ:**
$$
x_1 = -1, \quad x_2 = 2, \quad x_3 = 0
$$

### 2. Метод Гаусса

**Шаг 1: Запишем расширенную матрицу системы.**

$$
\begin{pmatrix}
1 & 1 & -2 & | & 1 \\
5 & 3 & 1 & | & 1 \\
-1 & -2 & 1 & | & -3
\end{pmatrix}
$$

**Шаг 2: Приведем матрицу к ступенчатому виду.**

1. Вычтем первую строку, умноженную на 5, из второй строки:
$$
\begin{pmatrix}
1 & 1 & -2 & | & 1 \\
0 & -2 & 11 & | & -4 \\
-1 & -2 & 1 & | & -3
\end{pmatrix}
$$

2. Прибавим первую строку к третьей:
$$
\begin{pmatrix}
1 & 1 & -2 & | & 1 \\
0 & -2 & 11 & | & -4 \\
0 & -1 & -1 & | & -2
\end{pmatrix}
$$

3. Поделим вторую строку на -2:
$$
\begin{pmatrix}
1 & 1 & -2 & | & 1 \\
0 & 1 & -5.5 & | & 2 \\
0 & -1 & -1 & | & -2
\end{pmatrix}
$$

4. Прибавим вторую строку к третьей:
$$
\begin{pmatrix}
1 & 1 & -2 & | & 1 \\
0 & 1 & -5.5 & | & 2 \\
0 & 0 & -6.5 & | & 0
\end{pmatrix}
$$

5. Поделим третью строку на -6.5:
$$
\begin{pmatrix}
1 & 1 & -2 & | & 1 \\
0 & 1 & -5.5 & | & 2 \\
0 & 0 & 1 & | & 0
\end{pmatrix}
$$

**Шаг 3: Обратный ход метода Гаусса.**

1. Из третьего уравнения: $ x_3 = 0 $.

2. Подставим $ x_3 = 0 $ во второе уравнение:
$$
x_2 - 5.5 \cdot 0 = 2 \Rightarrow x_2 = 2
$$

3. Подставим $ x_2 = 2 $ и $ x_3 = 0 $ в первое уравнение:
$$
x_1 + 2 - 2 \cdot 0 = 1 \Rightarrow x_1 = -1
$$

**Ответ:**
$$
x_1 = -1, \quad x_2 = 2, \quad x_3 = 0
$$

### 3. Метод обратной матрицы

**Шаг 1: Запишем матрицу системы $ A $ и вектор свободных членов $ B $.**

$$
A = \begin{pmatrix}
1 & 1 & -2 \\
5 & 3 & 1 \\
-1 & -2 & 1
\end{pmatrix}, \quad B = \begin{pmatrix}
1 \\
1 \\
-3
\end{pmatrix}
$$

**Шаг 2: Найдем обратную матрицу $ A^{-1} $.**

Определитель $ \Delta = 13 $ (найден ранее).

Алгебраические дополнения:
$$
A_{11} = 5, \quad A_{12} = -6, \quad A_{13} = -7, \\
A_{21} = -3, \quad A_{22} = -1, \quad A_{23} = 3, \\
A_{31} = 7, \quad A_{32} = -11, \quad A_{33} = -2.
$$

Обратная матрица:
$$
A^{-1} = \frac{1}{13} \begin{pmatrix}
5 & -3 & 7 \\
-6 & -1 & -11 \\
-7 & 3 & -2
\end{pmatrix}
$$

**Шаг 3: Найдем решение системы.**

$$
X = A^{-1} \cdot B = \frac{1}{13} \begin{pmatrix}
5 & -3 & 7 \\
-6 & -1 & -11 \\
-7 & 3 & -2
\end{pmatrix} \begin{pmatrix}
1 \\
1 \\
-3
\end{pmatrix} = \frac{1}{13} \begin{pmatrix}
5 \cdot 1 + (-3) \cdot 1 + 7 \cdot (-3) \\
-6 \cdot 1 + (-1) \cdot 1 + (-11) \cdot (-3) \\
-7 \cdot 1 + 3 \cdot 1 + (-2) \cdot (-3)
\end{pmatrix} = \frac{1}{13} \begin{pmatrix}
-13 \\
26 \\
0
\end{pmatrix} = \begin{pmatrix}
-1 \\
2 \\
0
\end{pmatrix}
$$

**Ответ:**
$$
x_1 = -1, \quad x_2 = 2, \quad x_3 = 0
$$

**Итоговый ответ:**
$$
\boxed{x_1 = -1, \quad x_2 = 2, \quad x_3 = 0}
$$

# Задача 19

**Даны векторы:**

$$
\bar{a} = (1,\,5,\,-1), \quad
\bar{b} = (1,\,3,\,-2), \quad
\bar{c} = (-2,\,1,\,1), \quad
\bar{d} = (1,\,1,\,-3)
$$

### а) Базис

Чтобы определить, образуют ли векторы $\bar{a}$, $\bar{b}$ и $\bar{c}$ базис, вычислим определитель:

$$
\det(\bar{a}, \bar{b}, \bar{c}) =
\begin{vmatrix}
1 & 1 & -2 \\
5 & 3 & 1 \\
-1 & -2 & 1 \\
\end{vmatrix}
= 13 \neq 0.
$$

Так как определитель не равен нулю, векторы $\bar{a}$, $\bar{b}$, $\bar{c}$ действительно образуют базис.

### б) Координаты $\bar{d}$ в базисе $(\bar{a}, \bar{b}, \bar{c})$:

Запишем вектор $\bar{d}$ в виде линейной комбинации базисных векторов:

$$
\bar{d} = x\bar{a} + y\bar{b} + z\bar{c}.
$$

Это приводит к системе уравнений:

$$
\begin{cases}
1 = x + y - 2z, \\
1 = 5x + 3y + z, \\
-3 = -x - 2y + z.
\end{cases}
$$

**Решение системы:**

1. Выразим $ x $ через $ y $ и $ z $ из первого уравнения:

   $$
   x = 1 - y + 2z.
   $$

2. Подставим $ x $ во второе уравнение:

   $$
   1 = 5(1 - y + 2z) + 3y + z \quad \Rightarrow \quad 1 = 5 - 5y + 10z + 3y + z,
   $$

   $$
   1 = 5 - 2y + 11z \quad \Rightarrow \quad 2y - 11z = 4.
   $$

3. Подставим $ x $ в третье уравнение:

   $$
   -3 = -(1 - y + 2z) - 2y + z \quad \Rightarrow \quad -3 = -1 + y - 2z - 2y + z,
   $$

   $$
   -3 = -1 - y - z \quad \Rightarrow \quad y + z = 2.
   $$

4. Из уравнения $ y + z = 2 $ получаем:

   $$
   y = 2 - z.
   $$

5. Подставляем $ y = 2 - z $ в уравнение $ 2y - 11z = 4 $:

   $$
   2(2 - z) - 11z = 4 \quad \Rightarrow \quad 4 - 2z - 11z = 4,
   $$

   $$
   4 - 13z = 4 \quad \Rightarrow \quad z = 0.
   $$

6. Тогда $ y = 2 - 0 = 2 $ и

   $$
   x = 1 - 2 + 2\cdot0 = -1.
   $$

**Итак, координаты вектора $\bar{d}$ в базисе $(\bar{a}, \bar{b}, \bar{c})$ равны:**

$$
(-1,\, 2,\, 0).
$$

**Ответ:** Координаты $\bar{d}$ в базисе $(\bar{a}, \bar{b}, \bar{c})$: $(-1,\, 2,\, 0)$.

# Задача 29

**Решение:**

**Дано:** координаты вершин пирамиды:
$A_1(1, -1, 1)$, $A_2(2, 4, 0)$, $A_3(2, 2, -1)$, $A_4(-1, 0, 2)$.

### а) Угол между ребрами $A_1A_2$ и $A_1A_3$

1. Найдем векторы $\vec{A_1A_2}$ и $\vec{A_1A_3}$:
   $$
   \vec{A_1A_2} = A_2 - A_1 = (2-1, 4-(-1), 0-1) = (1, 5, -1)
   $$
   $$
   \vec{A_1A_3} = A_3 - A_1 = (2-1, 2-(-1), -1-1) = (1, 3, -2)
   $$

2. Найдем скалярное произведение векторов:
   $$
   \vec{A_1A_2} \cdot \vec{A_1A_3} = 1 \cdot 1 + 5 \cdot 3 + (-1) \cdot (-2) = 1 + 15 + 2 = 18
   $$

3. Найдем длины векторов:
   $$
   |\vec{A_1A_2}| = \sqrt{1^2 + 5^2 + (-1)^2} = \sqrt{1 + 25 + 1} = \sqrt{27} = 3\sqrt{3}
   $$
   $$
   |\vec{A_1A_3}| = \sqrt{1^2 + 3^2 + (-2)^2} = \sqrt{1 + 9 + 4} = \sqrt{14}
   $$

4. Найдем угол $\theta$ между векторами:
   $$
   \cos \theta = \frac{\vec{A_1A_2} \cdot \vec{A_1A_3}}{|\vec{A_1A_2}| \cdot |\vec{A_1A_3}|} = \frac{18}{3\sqrt{3} \cdot \sqrt{14}} = \frac{18}{3\sqrt{42}} = \frac{6}{\sqrt{42}} = \frac{6\sqrt{42}}{42} = \frac{\sqrt{42}}{7}
   $$
   $$
   \theta = \arccos\left(\frac{\sqrt{42}}{7}\right)
   $$

**Ответ:** $\theta = \arccos\left(\frac{\sqrt{42}}{7}\right)$.

### б) Площадь грани $A_1A_2A_3$

1. Найдем векторное произведение векторов $\vec{A_1A_2}$ и $\vec{A_1A_3}$:
   $$
   \vec{A_1A_2} \times \vec{A_1A_3} = 
   \begin{vmatrix}
   \mathbf{i} & \mathbf{j} & \mathbf{k} \\
   1 & 5 & -1 \\
   1 & 3 & -2 \\
   \end{vmatrix}
   = \mathbf{i}(5 \cdot (-2) - (-1) \cdot 3) - \mathbf{j}(1 \cdot (-2) - (-1) \cdot 1) + \mathbf{k}(1 \cdot 3 - 5 \cdot 1)
   $$
   $$
   = \mathbf{i}(-10 + 3) - \mathbf{j}(-2 + 1) + \mathbf{k}(3 - 5) = -7\mathbf{i} + \mathbf{j} - 2\mathbf{k}
   $$

2. Найдем длину векторного произведения:
   $$
   |\vec{A_1A_2} \times \vec{A_1A_3}| = \sqrt{(-7)^2 + 1^2 + (-2)^2} = \sqrt{49 + 1 + 4} = \sqrt{54} = 3\sqrt{6}
   $$

3. Площадь грани:
   $$
   S = \frac{1}{2} |\vec{A_1A_2} \times \vec{A_1A_3}| = \frac{1}{2} \cdot 3\sqrt{6} = \frac{3\sqrt{6}}{2}
   $$

**Ответ:** $S = \frac{3\sqrt{6}}{2}$.

### в) Уравнение плоскости $A_1A_2A_3$

1. Найдем нормальный вектор плоскости как векторное произведение $\vec{A_1A_2} \times \vec{A_1A_3}$:
   $$
   \vec{n} = \vec{A_1A_2} \times \vec{A_1A_3} = (-7, 1, -2)
   $$

2. Уравнение плоскости:
   $$
   -7(x - 1) + 1(y + 1) - 2(z - 1) = 0
   $$
   $$
   -7x + 7 + y + 1 - 2z + 2 = 0
   $$
   $$
   -7x + y - 2z + 10 = 0
   $$

**Ответ:** $-7x + y - 2z + 10 = 0$.

### г) Уравнение высоты, проходящей через вершину $A_4$

1. Высота проходит через $A_4(-1, 0, 2)$ и перпендикулярна плоскости $A_1A_2A_3$. Направляющий вектор высоты совпадает с нормальным вектором плоскости:
   $$
   \vec{n} = (-7, 1, -2)
   $$

2. Параметрические уравнения высоты:
   $$
   x = -1 - 7t, \quad y = 0 + t, \quad z = 2 - 2t
   $$

**Ответ:** 
$$
\begin{cases}
x = -1 - 7t, \\
y = t, \\
z = 2 - 2t.
\end{cases}
$$

### д) Объем пирамиды

1. Найдем векторы $\vec{A_1A_2}$, $\vec{A_1A_3}$, $\vec{A_1A_4}$:
   $$
   \vec{A_1A_2} = (1, 5, -1), \quad \vec{A_1A_3} = (1, 3, -2), \quad \vec{A_1A_4} = (-2, 1, 1)
   $$

2. Найдем смешанное произведение векторов:
   $$
   \vec{A_1A_2} \cdot (\vec{A_1A_3} \times \vec{A_1A_4}) = 
   \begin{vmatrix}
   1 & 5 & -1 \\
   1 & 3 & -2 \\
   -2 & 1 & 1 \\
   \end{vmatrix}
   $$
   $$
   = 1(3 \cdot 1 - (-2) \cdot 1) - 5(1 \cdot 1 - (-2) \cdot (-2)) + (-1)(1 \cdot 1 - 3 \cdot (-2))
   $$
   $$
   = 1(3 + 2) - 5(1 - 4) + (-1)(1 + 6) = 5 + 15 - 7 = 13
   $$

3. Объем пирамиды:
   $$
   V = \frac{1}{6} |\vec{A_1A_2} \cdot (\vec{A_1A_3} \times \vec{A_1A_4})| = \frac{13}{6}
   $$

**Ответ:** $V = \frac{13}{6}$.

# Задача 39

**Дано уравнение:**

$$
(4x + 5y)^2 = 40(10 + xy)
$$

**Решение:**

1. **Раскроем скобки:**
   - Левая часть:
     $$
     (4x + 5y)^2 = 16x^2 + 40xy + 25y^2
     $$
   - Правая часть:
     $$
     40(10 + xy) = 400 + 40xy
     $$

2. **Подставим в исходное уравнение:**
   $$
   16x^2 + 40xy + 25y^2 = 400 + 40xy
   $$

3. **Упростим:**
   Вычтем $40xy$ из обеих частей:
   $$
   16x^2 + 25y^2 = 400
   $$

4. **Приведем к каноническому виду:**
   Разделим на 400:
   $$
   \frac{x^2}{25} + \frac{y^2}{16} = 1
   $$
   Это уравнение эллипса с центром в точке $(0, 0)$, где $a^2 = 25$, $b^2 = 16$.

5. **Найдем параметры эллипса:**
   - Большая полуось: $a = 5$ (по оси $x$).
   - Малая полуось: $b = 4$ (по оси $y$).
   - Вершины: $(\pm5, 0)$ и $(0, \pm4)$.
   - Фокусы:
     $$
     c = \sqrt{a^2 - b^2} = \sqrt{25 - 16} = 3
     $$
     Координаты фокусов: $(\pm3, 0)$.

**Ответ:**
- Каноническое уравнение: $\frac{x^2}{25} + \frac{y^2}{16} = 1$.
- Вершины: $(\pm5, 0)$, $(0, \pm4)$.
- Фокусы: $(\pm3, 0)$.

**Построение чертежа эллипса:**

1. **Нарисуйте оси координат:**
   - Проведите горизонтальную ось $x$ и вертикальную ось $y$.
   - Отметьте центр эллипса в точке $(0, 0)$.

2. **Отметьте вершины:**
   - По оси $x$: точки $( -5, 0 )$ и $( 5, 0 )$.
   - По оси $y$: точки $( 0, -4 )$ и $( 0, 4 )$.

3. **Постройте эллипс:**
   - Соедините вершины плавной симметричной кривой, формируя овал. Эллипс должен быть симметричен относительно обеих осей.

4. **Отметьте фокусы:**
   - На оси $x$ на расстоянии $3$ от центра: точки $( -3, 0 )$ и $( 3, 0 )$.

# Задача 49

**Найти пределы:**

**49. а)**

$$
\lim_{x \to \infty} \frac{x^3 - x^2 + x}{x^3 + 2x^2 - x + 3}
$$

**Решение:**

Разделим числитель и знаменатель на $x^3$:

$$
\frac{1 - \frac{1}{x} + \frac{1}{x^2}}{1 + \frac{2}{x} - \frac{1}{x^2} + \frac{3}{x^3}}
$$

При $x \to \infty$ слагаемые с $\frac{1}{x}$ стремятся к 0:

$$
\frac{1 - 0 + 0}{1 + 0 - 0 + 0} = \frac{1}{1} = 1
$$

**Ответ:** $1$.

**49. б)**

$$
\lim_{x \to 3} \frac{x^3 - 27}{\sqrt{3x} - x}
$$

**Решение:**

1. Разложим числитель ($x^3 - 27$ — разность кубов):

$$
x^3 - 27 = (x - 3)(x^2 + 3x + 9)
$$

2. Умножим числитель и знаменатель на сопряженное ($ \sqrt{3x} + x $):

$$
\frac{(x - 3)(x^2 + 3x + 9)(\sqrt{3x} + x)}{(\sqrt{3x} - x)(\sqrt{3x} + x)} = \frac{(x - 3)(x^2 + 3x + 9)(\sqrt{3x} + x)}{3x - x^2}
$$

3. Упростим знаменатель:

$$
3x - x^2 = -x(x - 3)
$$

4. Сократим $(x - 3)$:

$$
\frac{(x^2 + 3x + 9)(\sqrt{3x} + x)}{-x}
$$

5. Подставим $x = 3$:

$$
\frac{(9 + 9 + 9)(\sqrt{9} + 3)}{-3} = \frac{27 \cdot 6}{-3} = -54
$$

**Ответ:** $-54$.

**49. в)**

$$
\lim_{x \to 0} \frac{\tg^2 8x}{x \sin 3x}
$$

**Решение:**

Используем эквивалентные бесконечно малые ($x \to 0$):

$$
\tg 8x \sim 8x, \quad \sin 3x \sim 3x
$$

Подставим:

$$
\frac{(8x)^2}{x \cdot 3x} = \frac{64x^2}{3x^2} = \frac{64}{3}
$$

**Ответ:** $\frac{64}{3}$.

# Задача 59

**Исследование функции на непрерывность**

**Дано:**

$$ f(x) = \begin{cases} 
-x - 1, & x \leq -1; \\ 
(x + 1)^2, & -1 < x \leq 0; \\ 
x, & x > 0.
\end{cases} \]

**Найти:** Точки разрыва функции и построить схематический график.

### Анализ непрерывности:

1. **Точка $ x = -1 $:**
   - Значение функции: $ f(-1) = -(-1) - 1 = 0 $.
   - Левый предел ($ x \to -1^- $): $ \lim_{x \to -1^-} (-x - 1) = 0 $.
   - Правый предел ($ x \to -1^+ $): $ \lim_{x \to -1^+} (x + 1)^2 = 0 $.
   - Все условия непрерывности выполнены.
   **Вывод:** В точке $ x = -1 $ функция непрерывна.

2. **Точка $ x = 0 $:**
   - Значение функции: $ f(0) = (0 + 1)^2 = 1 $.
   - Левый предел ($ x \to 0^- $): $ \lim_{x \to 0^-} (x + 1)^2 = 1 $.
   - Правый предел ($ x \to 0^+ $): $ \lim_{x \to 0^+} x = 0 $.
   - Левый предел ≠ правому пределу.
   **Вывод:** В точке $ x = 0 $ функция имеет разрыв первого рода (скачок).

### График функции:

Схематически:

1. При $ x \leq -1 $: прямая $ y = -x - 1 $ (угол наклона -1, пересекает ось Y в (0, -1)).
2. При $ -1 < x \leq 0 $: парабола $ y = (x + 1)^2 $ (вершина в (-1, 0), возрастает до точки (0, 1)).
3. При $ x > 0 $: прямая $ y = x $ (угол наклона 1).

В точке $ x = 0 $ наблюдается скачок от $ y = 1 $ (слева) до $ y = 0 $ (справа).

### Ответ:
Точка разрыва — $ x = 0 $. График имеет скачок в этой точке.

**Чертёж функции для задачи 59:**

1. **При $ x \leq -1 $:**
   - Прямая $ y = -x - 1 $.
   - Примерные точки: $ (-2, 1) $, $ (-1, 0) $.
   - Направление: убывает с углом наклона -1.

2. **При $ -1 < x \leq 0 $:**
   - Парабола $ y = (x + 1)^2 $.
   - Вершина: $ (-1, 0) $.
   - Примерные точки: $ (-0.5, 0.25) $, $ (0, 1) $.
   - Плавная кривая, возрастающая от $ (-1, 0) $ до $ (0, 1) $.

3. **При $ x > 0 $:**
   - Прямая $ y = x $.
   - Примерные точки: $ (0, 0) $, $ (1, 1) $, $ (2, 2) $.
   - Направление: возрастает с углом наклона 1.

**Особые отметки:**
- В точке $ x = 0 $:
  - Слева: $ y = 1 $ (закрашенная точка).
  - Справа: $ y = 0 $ (открытая точка).
  - Скачок от $ (0, 1) $ к $ (0, 0) $.

# Задача 69

**Найти производные функций:**

**69. a) $\frac{1}{(x+2)^4}$**

Чтобы найти производную этой функции, удобно представить ее в виде степени:

$y = \frac{1}{(x+2)^4} = (x+2)^{-4}$

Теперь применим правило дифференцирования сложной функции (цепное правило) и правило степени: $(u^n)' = n u^{n-1} \cdot u'$, где $u = x+2$ и $n = -4$.

$y' = -4 (x+2)^{-4-1} \cdot (x+2)'$

Производная внутренней функции $(x+2)' = 1 + 0 = 1$.

$y' = -4 (x+2)^{-5} \cdot 1 = -4 (x+2)^{-5}$

Запишем ответ в виде дроби:

$y' = -\frac{4}{(x+2)^5}$

**Ответ: $y' = -\frac{4}{(x+2)^5}$**

**69. б) $2 \operatorname{arctg}^3 e^x$**

Здесь у нас произведение константы на сложную функцию. Константу можно вынести за знак производной.  Функция является композицией нескольких функций: степень, арктангенс, экспонента.  Применяем цепное правило последовательно.

$y = 2 \operatorname{arctg}^3 e^x = 2 (\operatorname{arctg} e^x)^3$

$y' = 2 \cdot \frac{d}{dx} (\operatorname{arctg} e^x)^3$

Сначала дифференцируем внешнюю функцию (степень):
$y' = 2 \cdot 3 (\operatorname{arctg} e^x)^{3-1} \cdot \frac{d}{dx} (\operatorname{arctg} e^x)$

$y' = 6 \operatorname{arctg}^2 e^x \cdot \frac{d}{dx} (\operatorname{arctg} e^x)$

Теперь дифференцируем $\operatorname{arctg} e^x$. Производная $\operatorname{arctg} u = \frac{1}{1+u^2} \cdot u'$, где $u = e^x$.
$\frac{d}{dx} (\operatorname{arctg} e^x) = \frac{1}{1+(e^x)^2} \cdot \frac{d}{dx} (e^x) = \frac{1}{1+e^{2x}} \cdot e^x = \frac{e^x}{1+e^{2x}}$

Подставляем это обратно в выражение для $y'$:
$y' = 6 \operatorname{arctg}^2 e^x \cdot \frac{e^x}{1+e^{2x}}$

$y' = \frac{6 e^x \operatorname{arctg}^2 e^x}{1+e^{2x}}$

**Ответ: $y' = \frac{6 e^x \operatorname{arctg}^2 e^x}{1+e^{2x}}$**

**69. в) $x\sqrt{\operatorname{tg} \left(\frac{x}{2} + \frac{1}{x}\right)}$**

Здесь у нас произведение двух функций: $u(x) = x$ и $v(x) = \sqrt{\operatorname{tg} \left(\frac{x}{2} + \frac{1}{x}\right)}$. Применяем правило произведения: $(uv)' = u'v + uv'$.

$u = x$, $u' = 1$
$v = \sqrt{\operatorname{tg} \left(\frac{x}{2} + \frac{1}{x}\right)} = \left(\operatorname{tg} \left(\frac{x}{2} + \frac{1}{x}\right)\right)^{1/2}$

Найдем производную $v'$. Снова цепное правило.  Внешняя функция - корень (степень 1/2), затем тангенс, затем сумма дробей.
$v' = \frac{1}{2} \left(\operatorname{tg} \left(\frac{x}{2} + \frac{1}{x}\right)\right)^{1/2 - 1} \cdot \frac{d}{dx} \left(\operatorname{tg} \left(\frac{x}{2} + \frac{1}{x}\right)\right)$

$v' = \frac{1}{2\sqrt{\operatorname{tg} \left(\frac{x}{2} + \frac{1}{x}\right)}} \cdot \frac{d}{dx} \left(\operatorname{tg} \left(\frac{x}{2} + \frac{1}{x}\right)\right)$

Производная $\operatorname{tg} u = \frac{1}{\cos^2 u} \cdot u' = \sec^2 u \cdot u'$, где $u = \frac{x}{2} + \frac{1}{x}$.
$\frac{d}{dx} \left(\operatorname{tg} \left(\frac{x}{2} + \frac{1}{x}\right)\right) = \frac{1}{\cos^2 \left(\frac{x}{2} + \frac{1}{x}\right)} \cdot \frac{d}{dx} \left(\frac{x}{2} + \frac{1}{x}\right)$

Производная $\left(\frac{x}{2} + \frac{1}{x}\right)' = \frac{1}{2} - \frac{1}{x^2}$.

$\frac{d}{dx} \left(\operatorname{tg} \left(\frac{x}{2} + \frac{1}{x}\right)\right) = \frac{1}{\cos^2 \left(\frac{x}{2} + \frac{1}{x}\right)} \cdot \left(\frac{1}{2} - \frac{1}{x^2}\right)$

Подставляем все обратно в $v'$:
$v' = \frac{1}{2\sqrt{\operatorname{tg} \left(\frac{x}{2} + \frac{1}{x}\right)}} \cdot \frac{1}{\cos^2 \left(\frac{x}{2} + \frac{1}{x}\right)} \cdot \left(\frac{1}{2} - \frac{1}{x^2}\right)$

Теперь находим $y' = u'v + uv'$:
$y' = 1 \cdot \sqrt{\operatorname{tg} \left(\frac{x}{2} + \frac{1}{x}\right)} + x \cdot \frac{1}{2\sqrt{\operatorname{tg} \left(\frac{x}{2} + \frac{1}{x}\right)} \cos^2 \left(\frac{x}{2} + \frac{1}{x}\right)} \cdot \left(\frac{1}{2} - \frac{1}{x^2}\right)$

$y' = \sqrt{\operatorname{tg} \left(\frac{x}{2} + \frac{1}{x}\right)} + \frac{x \left(\frac{1}{2} - \frac{1}{x^2}\right)}{2\sqrt{\operatorname{tg} \left(\frac{x}{2} + \frac{1}{x}\right)} \cos^2 \left(\frac{x}{2} + \frac{1}{x}\right)}$

**Ответ: $y' = \sqrt{\operatorname{tg} \left(\frac{x}{2} + \frac{1}{x}\right)} + \frac{x \left(\frac{1}{2} - \frac{1}{x^2}\right)}{2\sqrt{\operatorname{tg} \left(\frac{x}{2} + \frac{1}{x}\right)} \cos^2 \left(\frac{x}{2} + \frac{1}{x}\right)}$**

**69. г) $\frac{2^{3x}}{2^{3x} - 1}$**

Здесь у нас частное двух функций. Применяем правило частного: $\left(\frac{u}{v}\right)' = \frac{u'v - uv'}{v^2}$, где $u = 2^{3x}$ и $v = 2^{3x} - 1$.

Найдем производные $u'$ и $v'$. Производная $a^{kx} = a^{kx} \ln a \cdot k$.
$u' = \frac{d}{dx} (2^{3x}) = 2^{3x} \ln 2 \cdot \frac{d}{dx} (3x) = 2^{3x} \ln 2 \cdot 3 = 3 \cdot 2^{3x} \ln 2$
$v' = \frac{d}{dx} (2^{3x} - 1) = \frac{d}{dx} (2^{3x}) - \frac{d}{dx} (1) = 3 \cdot 2^{3x} \ln 2 - 0 = 3 \cdot 2^{3x} \ln 2$

Подставляем в формулу для производной частного:
$y' = \frac{(3 \cdot 2^{3x} \ln 2)(2^{3x} - 1) - (2^{3x})(3 \cdot 2^{3x} \ln 2)}{(2^{3x} - 1)^2}$

Вынесем общий множитель $3 \cdot 2^{3x} \ln 2$ из числителя:
$y' = \frac{3 \cdot 2^{3x} \ln 2 \cdot [(2^{3x} - 1) - 2^{3x}]}{(2^{3x} - 1)^2}$

$y' = \frac{3 \cdot 2^{3x} \ln 2 \cdot (2^{3x} - 1 - 2^{3x})}{(2^{3x} - 1)^2}$

$y' = \frac{3 \cdot 2^{3x} \ln 2 \cdot (-1)}{(2^{3x} - 1)^2}$

$y' = -\frac{3 \cdot 2^{3x} \ln 2}{(2^{3x} - 1)^2}$

**Ответ: $y' = -\frac{3 \cdot 2^{3x} \ln 2}{(2^{3x} - 1)^2}$**

**69. д) $\ln \sqrt[4]{\frac{1 + \cos 4x}{1 - \cos 4x}}$**

Сначала упростим выражение, используя свойства логарифмов:
$y = \ln \sqrt[4]{\frac{1 + \cos 4x}{1 - \cos 4x}} = \ln \left(\frac{1 + \cos 4x}{1 - \cos 4x}\right)^{1/4} = \frac{1}{4} \ln \left(\frac{1 + \cos 4x}{1 - \cos 4x}\right)$

$y = \frac{1}{4} \left[ \ln (1 + \cos 4x) - \ln (1 - \cos 4x) \right]$

Теперь дифференцируем, используя цепное правило и производную $\ln u = \frac{1}{u} \cdot u'$.
$y' = \frac{1}{4} \left[ \frac{1}{1 + \cos 4x} \cdot \frac{d}{dx} (1 + \cos 4x) - \frac{1}{1 - \cos 4x} \cdot \frac{d}{dx} (1 - \cos 4x) \right]$

Производная $\frac{d}{dx} (1 + \cos 4x) = 0 - \sin 4x \cdot 4 = -4 \sin 4x$
Производная $\frac{d}{dx} (1 - \cos 4x) = 0 - (-\sin 4x) \cdot 4 = 4 \sin 4x$

Подставляем обратно:
$y' = \frac{1}{4} \left[ \frac{-4 \sin 4x}{1 + \cos 4x} - \frac{4 \sin 4x}{1 - \cos 4x} \right]$

Сокращаем на 4:
$y' = \frac{1}{4} \cdot 4 \left[ -\frac{\sin 4x}{1 + \cos 4x} - \frac{\sin 4x}{1 - \cos 4x} \right] = -\sin 4x \left[ \frac{1}{1 + \cos 4x} + \frac{1}{1 - \cos 4x} \right]$

Приводим к общему знаменателю:
$y' = -\sin 4x \left[ \frac{(1 - \cos 4x) + (1 + \cos 4x)}{(1 + \cos 4x)(1 - \cos 4x)} \right] = -\sin 4x \left[ \frac{2}{1 - \cos^2 4x} \right]$

Используем тождество $1 - \cos^2 \theta = \sin^2 \theta$:
$y' = -\sin 4x \left[ \frac{2}{\sin^2 4x} \right] = -\frac{2 \sin 4x}{\sin^2 4x} = -\frac{2}{\sin 4x}$

**Ответ: $y' = -\frac{2}{\sin 4x}$**

# Задача 99

**Найти наибольшее и наименьшее значения функции**

**Дано:**

$$ y = x \ln x + 1 $$

### Шаг 1: Найдем производную функции

$$ y = x \ln x + 1 $$

Производная функции:

$$ y' = \frac{d}{dx}(x \ln x) + \frac{d}{dx}(1) = \ln x + x \cdot \frac{1}{x} = \ln x + 1 $$

### Шаг 2: Найдем критические точки

Приравняем производную к нулю:

$$ \ln x + 1 = 0 \implies \ln x = -1 \implies x = e^{-1} = \frac{1}{e} $$

Проверим, принадлежит ли критическая точка $ x = \frac{1}{e} $ отрезку $[1, e]$:

$$ \frac{1}{e} \approx 0.367 < 1 $$

Так как $ \frac{1}{e} $ не принадлежит отрезку $[1, e]$, то на данном отрезке функция не имеет критических точек.

### Шаг 3: Найдем значения функции на концах отрезка

Вычислим значение функции в точке $ x = 1 $:

$$ y(1) = 1 \cdot \ln 1 + 1 = 0 + 1 = 1 $$

Вычислим значение функции в точке $ x = e $:

$$ y(e) = e \cdot \ln e + 1 = e \cdot 1 + 1 = e + 1 $$

### Шаг 4: Определим наибольшее и наименьшее значения

На отрезке $[1, e]$ функция $ y = x \ln x + 1 $ возрастает, так как её производная $ y' = \ln x + 1 $ положительна при $ x \geq 1 $.

Следовательно:

- Наименьшее значение функции на отрезке $[1, e]$ равно $ y(1) = 1 $.
- Наибольшее значение функции на отрезке $[1, e]$ равно $ y(e) = e + 1 $.

### Ответ:

$$ \boxed{\text{Наибольшее значение: } e + 1, \quad \text{Наименьшее значение: } 1} $$

Для исследования функции $ y = (x+5)(x+2)^2 $ и построения её графика выполним следующие шаги:

### 1. Найдем область определения функции
Функция определена для всех действительных чисел, так как это многочлен.  
**Область определения:** $ x \in \mathbb{R} $.

### 2. Найдем нули функции (точки пересечения с осью $ x $)
Решим уравнение $ y = 0 $:
$$ (x+5)(x+2)^2 = 0 $$
Это уравнение выполняется, если:
- $ x + 5 = 0 $ → $ x = -5 $,
- $ (x + 2)^2 = 0 $ → $ x = -2 $.

**Нули функции:** $ x = -5 $ и $ x = -2 $.

### 3. Найдем точку пересечения с осью $ y $
Подставим $ x = 0 $ в функцию:
$$ y = (0 + 5)(0 + 2)^2 = 5 \cdot 4 = 20. $$
**Точка пересечения с осью $ y $:** $ (0, 20) $.

### 4. Исследуем поведение функции на бесконечности
Рассмотрим пределы при $ x \to \pm\infty $:
$$ \lim_{x \to +\infty} y = \lim_{x \to +\infty} (x+5)(x+2)^2 = +\infty, $$
$$ \lim_{x \to -\infty} y = \lim_{x \to -\infty} (x+5)(x+2)^2 = -\infty. $$
Функция стремится к $ +\infty $ при $ x \to +\infty $ и к $ -\infty $ при $ x \to -\infty $.

### 5. Найдем экстремумы и интервалы монотонности
Вычислим первую производную:
$$ y = (x+5)(x+2)^2. $$
Используем правило дифференцирования произведения:
$$ y' = \frac{d}{dx}[(x+5)] \cdot (x+2)^2 + (x+5) \cdot \frac{d}{dx}[(x+2)^2]. $$
Вычислим производные:
$$ \frac{d}{dx}[(x+5)] = 1, $$
$$ \frac{d}{dx}[(x+2)^2] = 2(x+2). $$
Подставим:
$$ y' = 1 \cdot (x+2)^2 + (x+5) \cdot 2(x+2). $$
Упростим:
$$ y' = (x+2)^2 + 2(x+5)(x+2). $$
Вынесем общий множитель $ (x+2) $:
$$ y' = (x+2) \left[ (x+2) + 2(x+5) \right]. $$
Упростим выражение в скобках:
$$ (x+2) + 2(x+5) = 3x + 12. $$
Таким образом:
$$ y' = (x+2)(3x+12). $$
Найдем критические точки, приравняв $ y' = 0 $:
$$ (x+2)(3x+12) = 0. $$
Решения:
- $ x + 2 = 0 $ → $ x = -2 $,
- $ 3x + 12 = 0 $ → $ x = -4 $.

**Критические точки:** $ x = -4 $ и $ x = -2 $.

### 6. Определим характер критических точек
Используем вторую производную:
$$ y'' = \frac{d}{dx}[y'] = \frac{d}{dx}[(x+2)(3x+12)]. $$
Раскроем скобки:
$$ y' = (x+2)(3x+12) = 3x^2 + 18x + 24. $$
Дифференцируем:
$$ y'' = 6x + 18. $$
Подставим критические точки:
- Для $ x = -4 $:
  $$ y''(-4) = 6 \cdot (-4) + 18 = -24 + 18 = -6 < 0. $$
  **Точка $ x = -4 $ — локальный максимум.**
- Для $ x = -2 $:
  $$ y''(-2) = 6 \cdot (-2) + 18 = -12 + 18 = 6 > 0. $$
  **Точка $ x = -2 $ — локальный минимум.**

### 7. Построим график функции
1. **Нули функции:** $ x = -5 $ и $ x = -2 $.
2. **Точка пересечения с осью $ y $:** $ (0, 20) $.
3. **Экстремумы:**
   - Локальный максимум в точке $ x = -4 $:
     $$ y(-4) = (-4 + 5)(-4 + 2)^2 = 1 \cdot 4 = 4. $$
     Точка $ (-4, 4) $.
   - Локальный минимум в точке $ x = -2 $:
     $$ y(-2) = (-2 + 5)(-2 + 2)^2 = 3 \cdot 0 = 0. $$
     Точка $ (-2, 0) $.

4. **Поведение на бесконечности:**
   - При $ x \to +\infty $, $ y \to +\infty $.
   - При $ x \to -\infty $, $ y \to -\infty $.

### Итоговый график
1. Начинаем с левой нижней части, проходим через $ (-6, -16) $, $ (-5, 0) $, поднимаемся до $ (-4, 4) $, опускаемся до $ (-3, 2) $, касаемся $ (-2, 0) $ и уходим вверх через $ (0, 20) $ и $ (1, 54) $.

2. Кривая должна быть плавной, без изломов.
