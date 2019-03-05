---
title: Практическое руководство. Использование обработки исключений для выхода из параллельного цикла
ms.date: 11/04/2016
helpviewer_keywords:
- search algorithm, writing [Concurrency Runtime]
- writing a search algorithm [Concurrency Runtime]
ms.assetid: 16d7278c-2d10-4014-9f58-f1899e719ff9
ms.openlocfilehash: 19d732d98f24172471d96cd5e2962b2a99ab0203
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/04/2019
ms.locfileid: "57262315"
---
# <a name="how-to-use-exception-handling-to-break-from-a-parallel-loop"></a>Практическое руководство. Использование обработки исключений для выхода из параллельного цикла

В этом разделе показано, как создание алгоритма поиска для базовой древовидной структуры.

Раздел [отмены](cancellation-in-the-ppl.md) описывается роль отмены в библиотеке параллельных шаблонов. Использование обработки исключений является менее эффективным способом отмены параллельной работы, чем использование [Concurrency::task_group:: Cancel](reference/task-group-class.md#cancel) и [Concurrency::structured_task_group:: Cancel](reference/structured-task-group-class.md#cancel) методы. Тем не менее, один сценарий, где использование обработки исключений для отмены работы — при вызове в библиотеку независимых производителей, использующего задачами или параллельными алгоритмами, но не предоставляет `task_group` или `structured_task_group` объект для отмены.

## <a name="example"></a>Пример

В следующем примере показано базовое `tree` тип, который содержит элемент данных и список дочерних узлов. В следующем разделе показано, тело `for_all` метод, который рекурсивно выполняет рабочую функцию на каждом дочернем узле.

[!code-cpp[concrt-task-tree-search#2](../../parallel/concrt/codesnippet/cpp/how-to-use-exception-handling-to-break-from-a-parallel-loop_1.cpp)]

## <a name="example"></a>Пример

В следующем примере показан `for_all` метод. Она использует [concurrency::parallel_for_each](reference/concurrency-namespace-functions.md#parallel_for_each) алгоритм для выполнения функции работы на каждый узел дерева в параллельном режиме.

[!code-cpp[concrt-task-tree-search#1](../../parallel/concrt/codesnippet/cpp/how-to-use-exception-handling-to-break-from-a-parallel-loop_2.cpp)]

## <a name="example"></a>Пример

В следующем примере показана функция `search_for_value`, которая выполняет поиск значения в предоставленном объекте `tree`. Эта функция передает `for_all` метод рабочую функцию, которая создает исключение при обнаружении узла дерева, содержащий указанное значение.

Предполагается, что `tree` предоставляет класс стороннюю библиотеку и изменять его. В этом случае подходит использование обработки исключений, так как `for_all` метод не предоставляет `task_group` или `structured_task_group` вызывающему объекту. Таким образом эта рабочая функция не может непосредственно отменить свою родительскую группу задач.

Если рабочая функция, чтобы группа задач создает исключение, среда выполнения останавливает все задачи, которые находятся в группе задач (включая любые дочерние группы задач) и удаляет все задачи, которые еще не запущено. `search_for_value` Функция использует `try` - `catch` блока для захвата исключения и вывести результат на консоль.

[!code-cpp[concrt-task-tree-search#3](../../parallel/concrt/codesnippet/cpp/how-to-use-exception-handling-to-break-from-a-parallel-loop_3.cpp)]

## <a name="example"></a>Пример

В следующем примере создается `tree` объекта и выполняется поиск нескольких значений в параллельном режиме. `build_tree` Функция показан далее в этом разделе.

[!code-cpp[concrt-task-tree-search#4](../../parallel/concrt/codesnippet/cpp/how-to-use-exception-handling-to-break-from-a-parallel-loop_4.cpp)]

В этом примере используется [concurrency::parallel_invoke](reference/concurrency-namespace-functions.md#parallel_invoke) алгоритм для поиска значений в параллельном режиме. Дополнительные сведения об этом алгоритме см. в разделе [параллельные алгоритмы](../../parallel/concrt/parallel-algorithms.md).

## <a name="example"></a>Пример

Приведенный ниже полный пример использует обработку исключений для поиска значений в базовой древовидной структуры.

[!code-cpp[concrt-task-tree-search#5](../../parallel/concrt/codesnippet/cpp/how-to-use-exception-handling-to-break-from-a-parallel-loop_5.cpp)]

В этом примере получается следующий результат.

```Output
Found a node with value 32614.
Found a node with value 86131.
Did not find node with value 17522.
```

## <a name="compiling-the-code"></a>Компиляция кода

Скопируйте код примера и вставьте его в проект Visual Studio или вставьте его в файл с именем `task-tree-search.cpp` и выполните следующую команду в окне командной строки Visual Studio.

**/ EHsc CL.exe задач дерева search.cpp**

## <a name="see-also"></a>См. также

[Отмена в библиотеке параллельных шаблонов](cancellation-in-the-ppl.md)<br/>
[Обработка исключений](../../parallel/concrt/exception-handling-in-the-concurrency-runtime.md)<br/>
[Параллелизм задач](../../parallel/concrt/task-parallelism-concurrency-runtime.md)<br/>
[Параллельные алгоритмы](../../parallel/concrt/parallel-algorithms.md)<br/>
[Класс task_group](reference/task-group-class.md)<br/>
[Класс structured_task_group](../../parallel/concrt/reference/structured-task-group-class.md)<br/>
[Функция parallel_for_each](reference/concurrency-namespace-functions.md#parallel_for_each)
