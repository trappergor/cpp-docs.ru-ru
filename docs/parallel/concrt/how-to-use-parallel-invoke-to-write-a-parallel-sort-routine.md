---
title: "Практическое руководство. Использование функции parallel_invoke для написания программы параллельной сортировки | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "класс task_handle, пример"
  - "класс task_group, пример"
  - "функция make_task, пример"
  - "класс structured_task_group, пример"
  - "повышение параллельной производительности с помощью групп задач [среда выполнения с параллелизмом]"
ms.assetid: 53979a2a-525d-4437-8952-f1ff85b37673
caps.latest.revision: 23
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 20
---
# Практическое руководство. Использование функции parallel_invoke для написания программы параллельной сортировки
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

В этом документе описано, как использовать алгоритм [parallel\_invoke](../Topic/parallel_invoke%20Function.md) для повышения производительности алгоритма битонной сортировки.  Алгоритм битонной сортировки рекурсивно разделяет входную последовательность на сортированные разделы меньшего размера.  Алгоритм битонной сортировки может выполняться параллельно, потому что каждая операция разделения независима от всех других операций.  
  
 Несмотря на то что битонная сортировка является примером *сети сортировки*, которая сортирует все сочетания входных последовательностей, в этом примере выполняется сортировка последовательностей, длина которых представляет собой степень числа два.  
  
> [!NOTE]
>  В этом примере используется параллельная процедура сортировка для иллюстрации.  Можно также использовать встроенные алгоритмы сортировки, предоставляемые PPL: [concurrency::parallel\_sort](../Topic/parallel_sort%20Function.md), [concurrency::parallel\_buffered\_sort](../Topic/parallel_buffered_sort%20Function.md) и [concurrency::parallel\_radixsort](../Topic/parallel_radixsort%20Function.md).  Для получения дополнительной информации см. [Параллельные алгоритмы](../Topic/Parallel%20Algorithms.md).  
  
##  <a name="top"></a> Подразделы  
 В этом документе описаны следующие задачи.  
  
-   [Последовательное выполнение битонной сортировки](#serial)  
  
-   [Использование parallel\_invoke для параллельного выполнения битонной сортировки](#parallel)  
  
##  <a name="serial"></a> Последовательное выполнение битонной сортировки  
 В следующем примере показана последовательная реализация алгоритма битонной сортировки.  Функция `bitonic_sort` разделяет последовательность на два раздела, сортирует эти разделы в противоположных направлениях и объединяет результаты.  Эта функция рекурсивно вызывает себя дважды, чтобы отсортировать каждый раздел.  
  
 [!CODE [concrt-parallel-bitonic-sort#1](../CodeSnippet/VS_Snippets_ConcRT/concrt-parallel-bitonic-sort#1)]  
  
 \[[Наверх](#top)\]  
  
##  <a name="parallel"></a> Использование parallel\_invoke для параллельного выполнения битонной сортировки  
 В этом разделе описано, как использовать алгоритм `parallel_invoke` для параллельного выполнения алгоритма битонной сортировки.  
  
### Процедуры  
  
##### Параллельное выполнение алгоритма битонной сортировки  
  
1.  Добавьте директиву `#include` для файла заголовка ppl.h.  
  
     [!CODE [concrt-parallel-bitonic-sort#10](../CodeSnippet/VS_Snippets_ConcRT/concrt-parallel-bitonic-sort#10)]  
  
2.  Добавьте директиву `using` для пространства имен `concurrency`.  
  
     [!CODE [concrt-parallel-bitonic-sort#11](../CodeSnippet/VS_Snippets_ConcRT/concrt-parallel-bitonic-sort#11)]  
  
3.  Создайте новую функцию с именем `parallel_bitonic_mege`, которая использует алгоритм `parallel_invoke`, чтобы объединить последовательности параллельно, если выполняемой работы достаточно.  В противном случае вызовите `bitonic_merge`, чтобы объединить последовательности последовательно.  
  
     [!CODE [concrt-parallel-bitonic-sort#2](../CodeSnippet/VS_Snippets_ConcRT/concrt-parallel-bitonic-sort#2)]  
  
4.  Выполните для функции `bitonic_sort` действия, аналогичные предыдущему шагу.  
  
     [!CODE [concrt-parallel-bitonic-sort#3](../CodeSnippet/VS_Snippets_ConcRT/concrt-parallel-bitonic-sort#3)]  
  
5.  Создайте перегруженную версию функции `parallel_bitonic_sort`, сортирующую массив по возрастанию.  
  
     [!CODE [concrt-parallel-bitonic-sort#4](../CodeSnippet/VS_Snippets_ConcRT/concrt-parallel-bitonic-sort#4)]  
  
 Алгоритм `parallel_invoke` снижает нагрузку на систему, выполняя последний ряд задач в вызывающем контексте.  Например, в функции `parallel_bitonic_sort` первая задача выполняется в отдельном контексте, а вторая — в контексте вызова.  
  
 [!CODE [concrt-parallel-bitonic-sort#5](../CodeSnippet/VS_Snippets_ConcRT/concrt-parallel-bitonic-sort#5)]  
  
 В следующем полном примере показаны последовательная и параллельная реализации алгоритма битонной сортировки.  В этом примере на консоль также выводится продолжительность выполнения каждого вычисления.  
  
 [!CODE [concrt-parallel-bitonic-sort#8](../CodeSnippet/VS_Snippets_ConcRT/concrt-parallel-bitonic-sort#8)]  
  
 В следующем примере показаны выходные данные, полученные на четырехпроцессорном компьютере.  
  
  **время последовательной сортировки: 4353**  
**время параллельной сортировки: 1248** \[[Наверх](#top)\]  
  
## Компиляция кода  
 Чтобы скомпилировать код, скопируйте и вставьте его в проект Visual Studio или в файл с именем `parallel-bitonic-sort.cpp`, затем выполните в окне командной строки Visual Studio следующую команду.  
  
 **cl.exe \/EHsc parallel\-bitonic\-sort.cpp**  
  
## Надежное программирование  
 В этом примере алгоритм `parallel_invoke` используется вместо класса [concurrency::task\_group](../Topic/task_group%20Class.md), потому что время существования каждой группы задач не выходит за пределы функции.  Рекомендуется по возможности использовать алгоритм `parallel_invoke`, так как при его выполнении нагрузка на систему меньше, чем при выполнении объектов `task group`, что позволяет писать более производительный код.  
  
 Параллельные версии некоторых алгоритмов функционируют более эффективно, если имеется достаточный объем работы.  Например, функция `parallel_bitonic_merge` вызывает последовательную версию, `bitonic_merge`, если в последовательности 500 элементов или меньше.  Также можно планировать общую стратегию сортировки на основании объемов работы.  Например, использование последовательной версии алгоритма быстрой сортировки может быть эффективнее, если массив содержит менее 500 элементов, как показано в следующем примере.  
  
 [!CODE [concrt-parallel-bitonic-sort#9](../CodeSnippet/VS_Snippets_ConcRT/concrt-parallel-bitonic-sort#9)]  
  
 Как и с другими параллельными алгоритмами, рекомендуется соответствующим образом профилировать и оптимизировать код.  
  
## См. также  
 [Параллелизм задач](../../parallel/concrt/task-parallelism-concurrency-runtime.md)   
 [Функция parallel\_invoke](../Topic/parallel_invoke%20Function.md)