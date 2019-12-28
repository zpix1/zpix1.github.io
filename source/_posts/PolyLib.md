---
title: PolyLib
date: 2018-12-21 22:39:49
tags: [Programming, Math]
---

Любите головоломки, а особенно нетривиальные? Обожаете делить плоскость на равные части? Вас привлекают связные фигуры из квадратиков? Но вы ненавидите тупую машинную работу? Эта либа готова сделать ее за вас!
<!-- more -->
## Общее
Python3 библиотека для загрузки, решения и вывода на экран и сохранения в svg различных задач связанных с разделением на полимино.
![Результат работы](https://i.imgur.com/7rAd4nK.png) Пример работы программы, разделение доски 15x6 на различные тетрамино. 

```Python
import parser
import solver

figure = parser.load('figure.pol')

for idx, s in enumerate(solver.polyomino_split(figure, 4)):
    parser.save_solution_to_svg(s, str(idx)+'th_sol.svg')
    parser.pretty_print_solution(s)
    print()
    break # Потому что нам нужно только первое решение
```

А теперь давайте решим какую-нибудь детскую задачу на разрезание: 
***
1.10. Разделите фигуру (рис. 7) на четыре равные части так, что-
бы линии разрезов шли по сторонам квадратов. Найдите как можно больше решений.
![Рисунок_7](http://i.imgur.com/sHFxJq3.png)
***
Забьем фигуру в `figure.pol`:

```Txt
   X
 XXXX
XXXXX
 XXXXX
 XXXX
  X
```

А дальше воспользуемся волшебной функцией:

```Python
import parser
import solver

figure = parser.load('figure.pol')

for idx, s in enumerate(solver.auto_congruent_polyomino_split(figure, 5)):
    parser.save_solution_to_svg(s, str(idx)+'th_sol.svg')
```
А вот и все 9 решений:
![Решения](http://i.imgur.com/QFizSIQ.png)Вперед пробовать и ставить звезды: 

[https://github.com/zpix1/polyomino](https://github.com/zpix1/polyomino)