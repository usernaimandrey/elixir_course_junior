### Float

Числа с плавающей точкой реализованы по стандарту IEEE 754, как и в большинстве других языков. Это значит, что их точность ограничена, и при некоторых операциях возможна потеря точности:

```elixir
0.1 + 0.2 # 0.30000000000000004
```

Для целых чисел, и чисел с плавающей точкой реализованы обычные арифметические операции:

```elixir
20 + 22    # 42
20.0 + 22  # 42.0
50 - 8.0   # 42.0
2 * 16     # 32
4 * 16.0   # 64.0
128 / 2    # 64.0
64.0 / 4.0 # 16.0
```

Операторы `+ - *` возвращают целое число, если оба аргумента целые, и число с плавающей точкой, если хотя бы один из аргументов с плавающей точкой. Оператор `/` всегда возвращает число с плавающей точкой.

Еще есть оператор целочисленного деления `div` и оператор взятия остатка `rem`:

```elixir
div(42, 2) # 21
div(45, 2) # 22
rem(42, 2) # 0
rem(45, 2) # 1
```

## Упражнение

реализовать функцию is_equal/3, которая сравнивает два float значения на равенство с допустимой погрешностью. Погрешность передается 3-м аргументом.

Запуск:
```
iex(1)> c "lib/lesson_03/task_03_02_float.exs"
iex(2)> alias Lesson_03.Task_03_02_Float, as: TF
Lesson_03.Task_03_02_Float
iex(3)> TF.is_equal(0.1, 0.2)
false
iex(4)> TF.is_equal(0.1, 0.11)
true
iex(5)> TF.is_equal(0.1, 0.11, 0.001)
false
```

Запуск тестов:
```
elixir lib/lesson_03/task_03_02_float.exs
```