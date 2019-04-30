---
title: Расширения SIMD
ms.date: 03/20/2019
helpviewer_keywords:
- SIMD
- OpenMP in Visual C++, new features
- explicit parallelization, new features
ms.openlocfilehash: 52402aa553c6d68d3073aba26ecac7b784522ee9
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62363275"
---
# <a name="simd-extension"></a>Расширения SIMD

Visual C++ в настоящее время поддерживает стандарт OpenMP 2.0, однако 2019 г. Visual Studio также предлагает функциональные возможности SIMD.

> [!NOTE]
> Чтобы использовать SIMD, компиляцию с параметром `-openmp:experimental` коммутатор, который включает дополнительные функции OpenMP, недоступные при использовании `-openmp` переключения.
>
> `-openmp:experimental` Subsumes коммутатора `-openmp`, то есть все компоненты OpenMP 2.0 включены в его использования.

Дополнительные сведения см. в разделе [SIMD-расширения для C++ OpenMP в Visual Studio](https://devblogs.microsoft.com/cppblog/simd-extension-to-c-openmp-in-visual-studio/).

## <a name="openmp-simd-in-visual-c"></a>OpenMP SIMD в визуальном элементеC++

SIMD OpenMP, представленными в OpenMP 4.0 standard, целевые объекты, что циклы вектор с поддержкой. С помощью `simd` директив до запуска цикла, компилятор может игнорировать векторные зависимости, адаптировать цикла как вектор устройств максимально и учитывает намерение пользователей имеют одновременно выполнять несколько итераций цикла.

```c
    #pragma omp simd
    for (i = 0; i < count; i++)
    {
        a[i] = a[i-1] + 1;
        b[i] = *c + 1;
        bar(i);
    }
```

Visual C++ предоставляет аналогичные директивы pragma цикла не OpenMP, такие как `#pragma vector` и `#pragma ivdep`, однако с помощью OpenMP SIMD, компилятор может делать больше как:

- Всегда может игнорировать присутствует векторные зависимости.
- `/fp:fast` включено в цикле.
- Внешние циклы и циклы в случае вызова функций — вектор с поддержкой.
- Можно, объединенных в один цикл и внесенные вектор с поддержкой вложенных циклов.
- Ускорение гибридного с `#pragma omp for simd` для включения недетализированного многопоточность и точные векторов.  

Вектор с поддержкой циклов For компилятор остается автоматической, если вы не используете параметр журнала вектора поддержки:

```cmd
    cl -O2 -openmp:experimental -Qvec-report:2 mycode.cpp
```

```Output
    mycode.cpp(84) : info C5002: Omp simd loop not vectorized due to reason '1200'
    mycode.cpp(90) : info C5002: Omp simd loop not vectorized due to reason '1200'
    mycode.cpp(96) : info C5001: Omp simd loop vectorized
```

Вектор понятное циклов For компилятор выдает каждого сообщения:

```cmd
    cl -O2 -openmp:experimental mycode.cpp
```

```Output
    mycode.cpp(84) : info C5002: Omp simd loop not vectorized due to reason '1200'
    mycode.cpp(90) : info C5002: Omp simd loop not vectorized due to reason '1200'
```

### <a name="clauses"></a>Предложения

Директива OpenMP SIMD также могут использовать нижеследующие предложения для улучшения поддержки вектора:

|Директива|Описание|
|---|---|
|`simdlen(length)`|Укажите количество полос вектор.|
|`safelen(length)`|Укажите расстояние зависимостей вектор.|
|`linear(list[ : linear-step]`)|Линейный сопоставление между индукционная переменная цикла в массиве подписку.|
|`aligned(list[ : alignment])`|Выравнивание данных.|
|`private(list)`|Укажите приватизации данных.|
|`lastprivate(list)`|Укажите данные приватизации окончательного значения из последней итерации.|
|`reduction(reduction-identifier:list)`|Укажите настраиваемые сокращения операций.|
|`collapse(n)`|Объединения со значением вложенной в цикл подпрограммы.|

> [!NOTE]
> Предложения не вступают в силу SIMD анализируются и игнорируется компилятором с предупреждением.
>
> Например используйте код следующее предупреждение:
>
> ```c
>    #pragma omp simd simdlen(8)
>    for (i = 0; i < count; i++)
>    {
>        a[i] = a[i-1] + 1;
>        b[i] = *c + 1;
>        bar(i);
>    }
> ```
>
> ```Output
>    warning C4849: OpenMP 'simdlen' clause ignored in 'simd' directive
> ```

### <a name="example"></a>Пример
  
Директива OpenMP SIMD предоставляет пользователям способ диктовки марки циклы компилятора вектор с поддержкой. Добавив аннотации цикл с директивой OpenMP SIMD, пользователи будут иметь одновременно выполнять несколько итераций цикла.

Например следующий цикл помечается с помощью директивы OpenMP SIMD. Имеется не идеальный параллелизма между итерации цикла с момента обратной зависимость из [i] [i-1], но из-за SIMD директивы, которые компилятор по-прежнему может pack последовательными итерациями первым оператором в одну инструкцию вектор и запуска их параллельно.

```c
    #pragma omp simd
    for (i = 0; i < count; i++)
    {
        a[i] = a[i-1] + 1;
        b[i] = *c + 1;
        bar(i);
    }
```

Таким образом, имеет следующую форму преобразованный вектор цикла **юридические** так как компилятор сохраняет последовательные поведение каждой исходной итерации цикла. Другими словами `a[i]` выполняется после `a[-1]`, `b[i]` после `a[i]` и вызов `bar` происходит последней.

```c
    for (i = 0; i < count; i+=4)
    {
        a[i:i+3] = a[i-1:i+2] + 1;
        b[i:i+3] = *c + 1;
        bar(i);
        bar(i+1);
        bar(i+2);
        bar(i+3);
    }
```

Он имеет **недопустимые** для перемещения ссылку на область памяти `*c` из цикла, если псевдоним может с `a[i]` или `b[i]`. Он также не является допустимым для изменения порядка инструкции, содержащиеся в одной исходной итерации, если это нарушает последовательных зависимостей. Например следующий цикл преобразованные не юридические:

```c
    c = b;
    t = *c;
    for (i = 0; i < count; i+=4)
    {
        a[i:i+3] = a[i-1:i+2] + 1;
        bar(i);            // illegal to reorder if bar[i] depends on b[i]
        b[i:i+3] = t + 1;  // illegal to move *c out of the loop
        bar(i+1);
        bar(i+2);
        bar(i+3);
    }
```

## <a name="see-also"></a>См. также

[/openmp (включение поддержки OpenMP 2.0)](../../build/reference/openmp-enable-openmp-2-0-support.md)<br/>
