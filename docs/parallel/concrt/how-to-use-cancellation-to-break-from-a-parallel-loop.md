---
title: Практическое руководство. Использование отмены для выхода из параллельного цикла
ms.date: 11/04/2016
helpviewer_keywords:
- writing a parallel search algorithm [Concurrency Runtime]
- parallel search algorithm, writing [Concurrency Runtime]
ms.assetid: 421cd2de-f058-465f-b890-dd8fcc0df273
ms.openlocfilehash: 08f33a75bc5c5391333a2d9368d4ed6563e117c2
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/04/2019
ms.locfileid: "57299573"
---
# <a name="how-to-use-cancellation-to-break-from-a-parallel-loop"></a>Практическое руководство. Использование отмены для выхода из параллельного цикла

В этом примере показано, как использовать отмену для реализации простого алгоритма параллельного поиска.

## <a name="example"></a>Пример

В следующем примере отмены для поиска элемента в массиве. `parallel_find_any` Функция использует [concurrency::parallel_for](reference/concurrency-namespace-functions.md#parallel_for) алгоритм и [concurrency::run_with_cancellation_token](reference/concurrency-namespace-functions.md#run_with_cancellation_token) функции для поиска позиции, которая содержит заданное значение. Если параллельный цикл находит это значение, он вызывает [Concurrency::cancellation_token_source:: Cancel](reference/cancellation-token-source-class.md#cancel) метод для отмены дальнейшей работы.

[!code-cpp[concrt-parallel-array-search#1](../../parallel/concrt/codesnippet/cpp/how-to-use-cancellation-to-break-from-a-parallel-loop_1.cpp)]

[Concurrency::parallel_for](reference/concurrency-namespace-functions.md#parallel_for) алгоритм действует одновременно. Таким образом он не выполняет операции в заранее определенный порядок. Если массив содержит несколько вхождений значения, результат может быть любого из его позиции.

## <a name="compiling-the-code"></a>Компиляция кода

Скопируйте код примера и вставьте его в проект Visual Studio или вставьте его в файл с именем `parallel-array-search.cpp` и выполните следующую команду в окне командной строки Visual Studio.

**/ EHsc CL.exe параллельного array-search.cpp**

## <a name="see-also"></a>См. также

[Отмена в библиотеке параллельных шаблонов](cancellation-in-the-ppl.md)<br/>
[Параллельные алгоритмы](../../parallel/concrt/parallel-algorithms.md)<br/>
[Функция parallel_for](reference/concurrency-namespace-functions.md#parallel_for)<br/>
[Класс cancellation_token_source](../../parallel/concrt/reference/cancellation-token-source-class.md)
