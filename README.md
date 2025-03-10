## 9. Решим систему уравнений тремя способами: методом Крамера, методом Гаусса и методом обратной матрицы.

**Система уравнений:**
\[
\begin{cases}
x_1 + x_2 - 2x_3 = 1, \\
5x_1 + 3x_2 + x_3 = 1, \\
-x_1 - 2x_2 + x_3 = -3.
\end{cases}
\]

### 1. Метод Крамера

**Шаг 1: Найдем определитель матрицы системы \( \Delta \).**

Матрица системы:
\[
A = \begin{pmatrix}
1 & 1 & -2 \\
5 & 3 & 1 \\
-1 & -2 & 1
\end{pmatrix}
\]

Определитель:
\[
\Delta = \begin{vmatrix}
1 & 1 & -2 \\
5 & 3 & 1 \\
-1 & -2 & 1
\end{vmatrix} = 1 \cdot (3 \cdot 1 - 1 \cdot (-2)) - 1 \cdot (5 \cdot 1 - 1 \cdot (-1)) + (-2) \cdot (5 \cdot (-2) - 3 \cdot (-1)) = 1 \cdot (3 + 2) - 1 \cdot (5 + 1) - 2 \cdot (-10 + 3) = 5 - 6 + 14 = 13
\]

**Шаг 2: Найдем определители \( \Delta_{x_1} \), \( \Delta_{x_2} \), \( \Delta_{x_3} \).**

\[
\Delta_{x_1} = \begin{vmatrix}
1 & 1 & -2 \\
1 & 3 & 1 \\
-3 & -2 & 1
\end{vmatrix} = 1 \cdot (3 \cdot 1 - 1 \cdot (-2)) - 1 \cdot (1 \cdot 1 - 1 \cdot (-3)) + (-2) \cdot (1 \cdot (-2) - 3 \cdot (-3)) = 5 - 4 - 14 = -13
\]

\[
\Delta_{x_2} = \begin{vmatrix}
1 & 1 & -2 \\
5 & 1 & 1 \\
-1 & -3 & 1
\end{vmatrix} = 1 \cdot (1 \cdot 1 - 1 \cdot (-3)) - 1 \cdot (5 \cdot 1 - 1 \cdot (-1)) + (-2) \cdot (5 \cdot (-3) - 1 \cdot (-1)) = 4 - 6 + 28 = 26
\]

\[
\Delta_{x_3} = \begin{vmatrix}
1 & 1 & 1 \\
5 & 3 & 1 \\
-1 & -2 & -3
\end{vmatrix} = 1 \cdot (3 \cdot (-3) - 1 \cdot (-2)) - 1 \cdot (5 \cdot (-3) - 1 \cdot (-1)) + 1 \cdot (5 \cdot (-2) - 3 \cdot (-1)) = -7 + 14 - 7 = 0
\]

**Шаг 3: Найдем решения.**

\[
x_1 = \frac{\Delta_{x_1}}{\Delta} = \frac{-13}{13} = -1, \quad x_2 = \frac{\Delta_{x_2}}{\Delta} = \frac{26}{13} = 2, \quad x_3 = \frac{\Delta_{x_3}}{\Delta} = \frac{0}{13} = 0
\]

**Ответ:**
\[
x_1 = -1, \quad x_2 = 2, \quad x_3 = 0
\]

### 2. Метод Гаусса

**Шаг 1: Запишем расширенную матрицу системы.**

\[
\begin{pmatrix}
1 & 1 & -2 & | & 1 \\
5 & 3 & 1 & | & 1 \\
-1 & -2 & 1 & | & -3
\end{pmatrix}
\]

**Шаг 2: Приведем матрицу к ступенчатому виду.**

1. Вычтем первую строку, умноженную на 5, из второй строки:
\[
\begin{pmatrix}
1 & 1 & -2 & | & 1 \\
0 & -2 & 11 & | & -4 \\
-1 & -2 & 1 & | & -3
\end{pmatrix}
\]

2. Прибавим первую строку к третьей:
\[
\begin{pmatrix}
1 & 1 & -2 & | & 1 \\
0 & -2 & 11 & | & -4 \\
0 & -1 & -1 & | & -2
\end{pmatrix}
\]

3. Поделим вторую строку на -2:
\[
\begin{pmatrix}
1 & 1 & -2 & | & 1 \\
0 & 1 & -5.5 & | & 2 \\
0 & -1 & -1 & | & -2
\end{pmatrix}
\]

4. Прибавим вторую строку к третьей:
\[
\begin{pmatrix}
1 & 1 & -2 & | & 1 \\
0 & 1 & -5.5 & | & 2 \\
0 & 0 & -6.5 & | & 0
\end{pmatrix}
\]

5. Поделим третью строку на -6.5:
\[
\begin{pmatrix}
1 & 1 & -2 & | & 1 \\
0 & 1 & -5.5 & | & 2 \\
0 & 0 & 1 & | & 0
\end{pmatrix}
\]

**Шаг 3: Обратный ход метода Гаусса.**

1. Из третьего уравнения: \( x_3 = 0 \).

2. Подставим \( x_3 = 0 \) во второе уравнение:
\[
x_2 - 5.5 \cdot 0 = 2 \Rightarrow x_2 = 2
\]

3. Подставим \( x_2 = 2 \) и \( x_3 = 0 \) в первое уравнение:
\[
x_1 + 2 - 2 \cdot 0 = 1 \Rightarrow x_1 = -1
\]

**Ответ:**
\[
x_1 = -1, \quad x_2 = 2, \quad x_3 = 0
\]

### 3. Метод обратной матрицы

**Шаг 1: Запишем матрицу системы \( A \) и вектор свободных членов \( B \).**

\[
A = \begin{pmatrix}
1 & 1 & -2 \\
5 & 3 & 1 \\
-1 & -2 & 1
\end{pmatrix}, \quad B = \begin{pmatrix}
1 \\
1 \\
-3
\end{pmatrix}
\]

**Шаг 2: Найдем обратную матрицу \( A^{-1} \).**

Определитель \( \Delta = 13 \) (найден ранее).

Алгебраические дополнения:
\[
A_{11} = 5, \quad A_{12} = -6, \quad A_{13} = -7, \\
A_{21} = -3, \quad A_{22} = -1, \quad A_{23} = 3, \\
A_{31} = 7, \quad A_{32} = -11, \quad A_{33} = -2.
\]

Обратная матрица:
\[
A^{-1} = \frac{1}{13} \begin{pmatrix}
5 & -3 & 7 \\
-6 & -1 & -11 \\
-7 & 3 & -2
\end{pmatrix}
\]

**Шаг 3: Найдем решение системы.**

\[
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
\]

**Ответ:**
\[
x_1 = -1, \quad x_2 = 2, \quad x_3 = 0
\]

**Итоговый ответ:**
\[
\boxed{x_1 = -1, \quad x_2 = 2, \quad x_3 = 0}
\]

---

## Задача 19.

**Даны векторы:**

$$
\bar{a} = (1,\,5,\,-1), \quad
\bar{b} = (1,\,3,\,-2), \quad
\bar{c} = (-2,\,1,\,1), \quad
\bar{d} = (1,\,1,\,-3)
$$

---

**а) Базис:**

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

---

**б) Координаты $\bar{d}$ в базисе $(\bar{a}, \bar{b}, \bar{c})$:**

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

1. Выразим \( x \) через \( y \) и \( z \) из первого уравнения:

   $$
   x = 1 - y + 2z.
   $$

2. Подставим \( x \) во второе уравнение:

   $$
   1 = 5(1 - y + 2z) + 3y + z \quad \Rightarrow \quad 1 = 5 - 5y + 10z + 3y + z,
   $$

   $$
   1 = 5 - 2y + 11z \quad \Rightarrow \quad 2y - 11z = 4.
   $$

3. Подставим \( x \) в третье уравнение:

   $$
   -3 = -(1 - y + 2z) - 2y + z \quad \Rightarrow \quad -3 = -1 + y - 2z - 2y + z,
   $$

   $$
   -3 = -1 - y - z \quad \Rightarrow \quad y + z = 2.
   $$

4. Из уравнения \( y + z = 2 \) получаем:

   $$
   y = 2 - z.
   $$

5. Подставляем \( y = 2 - z \) в уравнение \( 2y - 11z = 4 \):

   $$
   2(2 - z) - 11z = 4 \quad \Rightarrow \quad 4 - 2z - 11z = 4,
   $$

   $$
   4 - 13z = 4 \quad \Rightarrow \quad z = 0.
   $$

6. Тогда \( y = 2 - 0 = 2 \) и

   $$
   x = 1 - 2 + 2\cdot0 = -1.
   $$

**Итак, координаты вектора \(\bar{d}\) в базисе \((\bar{a}, \bar{b}, \bar{c})\) равны:**

$$
(-1,\, 2,\, 0).
$$

**Ответ:** Координаты $\bar{d}$ в базисе $(\bar{a}, \bar{b}, \bar{c})$: $(-1,\, 2,\, 0)$.

---

## Задача 29.

**Решение:**

**Дано:** координаты вершин пирамиды:
$A_1(1, -1, 1)$, $A_2(2, 4, 0)$, $A_3(2, 2, -1)$, $A_4(-1, 0, 2)$.

---

**а) Угол между ребрами $A_1A_2$ и $A_1A_3$**

1. Найдем векторы $\vec{A_1A_2}$ и $\vec{A_1A_3}$:
   \[
   \vec{A_1A_2} = A_2 - A_1 = (2-1, 4-(-1), 0-1) = (1, 5, -1)
   \]
   \[
   \vec{A_1A_3} = A_3 - A_1 = (2-1, 2-(-1), -1-1) = (1, 3, -2)
   \]

2. Найдем скалярное произведение векторов:
   \[
   \vec{A_1A_2} \cdot \vec{A_1A_3} = 1 \cdot 1 + 5 \cdot 3 + (-1) \cdot (-2) = 1 + 15 + 2 = 18
   \]

3. Найдем длины векторов:
   \[
   |\vec{A_1A_2}| = \sqrt{1^2 + 5^2 + (-1)^2} = \sqrt{1 + 25 + 1} = \sqrt{27} = 3\sqrt{3}
   \]
   \[
   |\vec{A_1A_3}| = \sqrt{1^2 + 3^2 + (-2)^2} = \sqrt{1 + 9 + 4} = \sqrt{14}
   \]

4. Найдем угол $\theta$ между векторами:
   \[
   \cos \theta = \frac{\vec{A_1A_2} \cdot \vec{A_1A_3}}{|\vec{A_1A_2}| \cdot |\vec{A_1A_3}|} = \frac{18}{3\sqrt{3} \cdot \sqrt{14}} = \frac{18}{3\sqrt{42}} = \frac{6}{\sqrt{42}} = \frac{6\sqrt{42}}{42} = \frac{\sqrt{42}}{7}
   \]
   \[
   \theta = \arccos\left(\frac{\sqrt{42}}{7}\right)
   \]

**Ответ:** $\theta = \arccos\left(\frac{\sqrt{42}}{7}\right)$.

---

**б) Площадь грани $A_1A_2A_3$**

1. Найдем векторное произведение векторов $\vec{A_1A_2}$ и $\vec{A_1A_3}$:
   \[
   \vec{A_1A_2} \times \vec{A_1A_3} =
   \begin{vmatrix}
   \mathbf{i} & \mathbf{j} & \mathbf{k} \\
   1 & 5 & -1 \\
   1 & 3 & -2 \\
   \end{vmatrix}
   = \mathbf{i}(5 \cdot (-2) - (-1) \cdot 3) - \mathbf{j}(1 \cdot (-2) - (-1) \cdot 1) + \mathbf{k}(1 \cdot 3 - 5 \cdot 1)
   \]
   \[
   = \mathbf{i}(-10 + 3) - \mathbf{j}(-2 + 1) + \mathbf{k}(3 - 5) = -7\mathbf{i} + \mathbf{j} - 2\mathbf{k}
   \]

2. Найдем длину векторного произведения:
   \[
   |\vec{A_1A_2} \times \vec{A_1A_3}| = \sqrt{(-7)^2 + 1^2 + (-2)^2} = \sqrt{49 + 1 + 4} = \sqrt{54} = 3\sqrt{6}
   \]

3. Площадь грани:
   \[
   S = \frac{1}{2} |\vec{A_1A_2} \times \vec{A_1A_3}| = \frac{1}{2} \cdot 3\sqrt{6} = \frac{3\sqrt{6}}{2}
   \]

**Ответ:** $S = \frac{3\sqrt{6}}{2}$.

---

**в) Уравнение плоскости $A_1A_2A_3$**

1. Найдем нормальный вектор плоскости как векторное произведение $\vec{A_1A_2} \times \vec{A_1A_3}$:
   \[
   \vec{n} = \vec{A_1A_2} \times \vec{A_1A_3} = (-7, 1, -2)
   \]

2. Уравнение плоскости:
   \[
   -7(x - 1) + 1(y + 1) - 2(z - 1) = 0
   \]
   \[
   -7x + 7 + y + 1 - 2z + 2 = 0
   \]
   \[
   -7x + y - 2z + 10 = 0
   \]

**Ответ:** $-7x + y - 2z + 10 = 0$.

---

**г) Уравнение высоты, проходящей через вершину $A_4$**

1. Высота проходит через $A_4(-1, 0, 2)$ и перпендикулярна плоскости $A_1A_2A_3$. Направляющий вектор высоты совпадает с нормальным вектором плоскости:
   \[
   \vec{n} = (-7, 1, -2)
   \]

2. Параметрические уравнения высоты:
