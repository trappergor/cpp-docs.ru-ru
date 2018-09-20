---
title: 'Практическое: использование класса combinable для комбинирования наборов | Документация Майкрософт'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- combinable class, example
- combining sets with combinable [Concurrency Runtime]
ms.assetid: 66ffe8e3-6bbb-4e9f-b790-b612922a68a7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 69f48ed099fe033ba1847a3414ed8e5c5ce88f71
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46433677"
---
# <a name="how-to-use-combinable-to-combine-sets"></a>Практическое руководство. Использование класса combinable для комбинирования наборов

В этом разделе показано, как использовать [concurrency::combinable](../../parallel/concrt/reference/combinable-class.md) класс для вычисления набора простых чисел.

## <a name="example"></a>Пример

В следующем примере вычисляется набор простых чисел в два раза. Каждого вычисления сохраняет результат в [std::bitset](../../standard-library/bitset-class.md) объекта. В примере сначала вычисляет набор последовательно и параллельно вычисляется. В этом примере в консоль также выводится время, необходимое на выполнение обоих вычислений.

В этом примере используется [concurrency::parallel_for](reference/concurrency-namespace-functions.md#parallel_for) алгоритм и `combinable` для создания локальных наборов потока. Затем он использует [concurrency::combinable::combine_each](reference/combinable-class.md#combine_each) метод для объединения наборов локального потока в конечный.

[!code-cpp[concrt-parallel-combine-primes#1](../../parallel/concrt/codesnippet/cpp/how-to-use-combinable-to-combine-sets_1.cpp)]

В следующем примере показаны выходные данные, полученные на четырехпроцессорном компьютере.

```Output
serial time: 312 ms

parallel time: 78 ms
```

## <a name="compiling-the-code"></a>Компиляция кода

Скопируйте код примера и вставьте его в проект Visual Studio или вставьте его в файл с именем `parallel-combine-primes.cpp` и выполните следующую команду в окне командной строки Visual Studio.

**/ EHsc CL.exe parallel-combine-primes.cpp**

## <a name="see-also"></a>См. также

[Параллельные контейнеры и объекты](../../parallel/concrt/parallel-containers-and-objects.md)<br/>
[Класс combinable](../../parallel/concrt/reference/combinable-class.md)<br/>
[Метод combinable::combine_each](reference/combinable-class.md#combine_each)

