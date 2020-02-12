---
title: Пошаговое руководство. Реализация фьючерсов
ms.date: 04/25/2019
helpviewer_keywords:
- implementing futures [Concurrency Runtime]
- futures, implementing [Concurrency Runtime]
ms.assetid: 82ea75cc-aaec-4452-b10d-8abce0a87e5b
ms.openlocfilehash: 2b9d889dac195bb60651cbb76110d54b6231a5fd
ms.sourcegitcommit: a8ef52ff4a4944a1a257bdaba1a3331607fb8d0f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/11/2020
ms.locfileid: "77141978"
---
# <a name="walkthrough-implementing-futures"></a>Пошаговое руководство. Реализация фьючерсов

В этом разделе показано, как реализовать фьючерсы в приложении. В этом разделе показано, как объединить существующие функции в среда выполнения с параллелизмом в что-то, которое делает больше.

> [!IMPORTANT]
> В этом разделе рассматривается понятие фьючерсов для демонстрационных целей. Рекомендуется использовать [std:: future](../../standard-library/future-class.md) или [Concurrency:: Task](../../parallel/concrt/reference/task-class.md) , если требуется асинхронная задача, которая выполняет вычисление значения для последующего использования.

*Задача* — это вычисление, которое можно разложить на дополнительные, более детализированные вычисления. *Будущее* — это асинхронная задача, которая выполняет вычисление значения для последующего использования.

Для реализации фьючерсов в этом разделе определяется класс `async_future`. Класс `async_future` использует следующие компоненты среда выполнения с параллелизмом: класс [Concurrency:: task_group](reference/task-group-class.md) и класс [concurrency:: single_assignment](../../parallel/concrt/reference/single-assignment-class.md) . Класс `async_future` использует класс `task_group` для асинхронного вычисления значения и класс `single_assignment` для хранения результата вычисления. Конструктор класса `async_future` принимает рабочую функцию, которая вычисляет результат, а метод `get` извлекает результат.

### <a name="to-implement-the-async_future-class"></a>Реализация класса async_future

1. Объявите класс шаблона с именем `async_future`, параметризованный для типа результирующего вычисления. Добавьте `public` и `private` разделы в этот класс.

[!code-cpp[concrt-futures#2](../../parallel/concrt/codesnippet/cpp/walkthrough-implementing-futures_1.cpp)]

1. В разделе `private` класса `async_future` объявите `task_group` и элемент данных `single_assignment`.

[!code-cpp[concrt-futures#3](../../parallel/concrt/codesnippet/cpp/walkthrough-implementing-futures_2.cpp)]

1. В разделе `public` класса `async_future` реализуйте конструктор. Конструктор является шаблоном, параметризованным в рабочей функции, которая выполняет вычисление результата. Конструктор асинхронно выполняет рабочую функцию в элементе данных `task_group` и использует функцию [Concurrency:: send](reference/concurrency-namespace-functions.md#send) для записи результата в `single_assignment`ный элемент данных.

[!code-cpp[concrt-futures#4](../../parallel/concrt/codesnippet/cpp/walkthrough-implementing-futures_3.cpp)]

1. В разделе `public` класса `async_future` реализуйте деструктор. Деструктор ожидает завершения задачи.

[!code-cpp[concrt-futures#5](../../parallel/concrt/codesnippet/cpp/walkthrough-implementing-futures_4.cpp)]

1. В разделе `public` класса `async_future` реализуйте метод `get`. Этот метод использует функцию [Concurrency:: Receive](reference/concurrency-namespace-functions.md#receive) для получения результата работы функции.

[!code-cpp[concrt-futures#6](../../parallel/concrt/codesnippet/cpp/walkthrough-implementing-futures_5.cpp)]

## <a name="example"></a>Пример

### <a name="description"></a>Description

В следующем примере показан полный класс `async_future` и пример его использования. Функция `wmain` создает объект std::[vector](../../standard-library/vector-class.md) , содержащий 10 000 случайных целочисленных значений. Затем он использует `async_future` объекты для поиска наименьшего и самого крупного значения, содержащегося в объекте `vector`.

### <a name="code"></a>Код

[!code-cpp[concrt-futures#1](../../parallel/concrt/codesnippet/cpp/walkthrough-implementing-futures_6.cpp)]

### <a name="comments"></a>Комментарии

В примере получается следующий вывод.

```Output
smallest: 0
largest:  9999
average:  4981
```

В примере используется метод `async_future::get` для получения результатов вычисления. Метод `async_future::get` ожидает завершения вычислений, если вычисления все еще активны.

## <a name="robust-programming"></a>Отказоустойчивость

Чтобы расширить класс `async_future` для обработки исключений, вызываемых рабочей функцией, измените метод `async_future::get`, чтобы вызвать метод [Concurrency:: task_group:: wait](reference/task-group-class.md#wait) . Метод `task_group::wait` создает исключения, созданные рабочей функцией.

В следующем примере показана измененная версия класса `async_future`. Функция `wmain` использует блок `try`-`catch` для вывода результата объекта `async_future` или для вывода значения исключения, созданного рабочей функцией.

[!code-cpp[concrt-futures-with-eh#1](../../parallel/concrt/codesnippet/cpp/walkthrough-implementing-futures_7.cpp)]

В примере получается следующий вывод.

```Output
caught exception: error
```

Дополнительные сведения о модели обработки исключений в среда выполнения с параллелизмом см. в разделе [обработка исключений](../../parallel/concrt/exception-handling-in-the-concurrency-runtime.md).

## <a name="compiling-the-code"></a>Компиляция кода

Скопируйте пример кода и вставьте его в проект Visual Studio или вставьте в файл с именем `futures.cpp`, а затем выполните следующую команду в окне командной строки Visual Studio.

**CL. exe/EHsc Futures. cpp**

## <a name="see-also"></a>См. также раздел

[Пошаговые руководства по среде выполнения с параллелизмом](../../parallel/concrt/concurrency-runtime-walkthroughs.md)<br/>
[Обработка исключений](../../parallel/concrt/exception-handling-in-the-concurrency-runtime.md)<br/>
[Класс task_group](reference/task-group-class.md)<br/>
[Класс single_assignment](../../parallel/concrt/reference/single-assignment-class.md)
