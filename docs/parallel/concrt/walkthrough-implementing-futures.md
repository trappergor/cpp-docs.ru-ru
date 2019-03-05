---
title: Пошаговое руководство. Реализация фьючерсов
ms.date: 11/04/2016
helpviewer_keywords:
- implementing futures [Concurrency Runtime]
- futures, implementing [Concurrency Runtime]
ms.assetid: 82ea75cc-aaec-4452-b10d-8abce0a87e5b
ms.openlocfilehash: 7164919d649751ac11fefa5be3cb2e5b7798ee4f
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/04/2019
ms.locfileid: "57262133"
---
# <a name="walkthrough-implementing-futures"></a>Пошаговое руководство. Реализация фьючерсов

В этом разделе показано, как реализовывать futures в приложении. Разделе показано, как объединить существующие функциональные возможности в среде выполнения с параллелизмом в нечто, что делает больше.

> [!IMPORTANT]
>  В этом разделе рассматривается понятие фьючерсов для демонстрационных целей. Мы рекомендуем использовать [std::future следует](../../standard-library/future-class.md) или [concurrency::task](../../parallel/concrt/reference/task-class.md) , если необходимо асинхронная задача, которая вычисляет значение для последующего использования.

Объект *задачи* — это вычисление, которое можно разложить на дополнительные, более мелкие вычислений. Объект *будущих* — это асинхронная задача, которая вычисляет значение для последующего использования.

Чтобы реализовать futures, в этом разделе описываются `async_future` класса. `async_future` Класса используются следующие компоненты среды выполнения с параллелизмом: [concurrency::task_group](reference/task-group-class.md) класс и [concurrency::single_assignment](../../parallel/concrt/reference/single-assignment-class.md) класса. `async_future` Класс использует `task_group` класс для вычисления значения асинхронно и `single_assignment` класса для хранения результата вычисления. Конструктор `async_future` класс не принимает рабочую функцию, которая вычисляет результат, и `get` метод позволяет получить результат.

### <a name="to-implement-the-asyncfuture-class"></a>Реализация класса async_future

1. Объявите класс с именем шаблона `async_future` , параметризован на типе результирующего вычисления. Добавить `public` и `private` разделы для этого класса.

[!code-cpp[concrt-futures#2](../../parallel/concrt/codesnippet/cpp/walkthrough-implementing-futures_1.cpp)]

1. В `private` раздел `async_future` объявите `task_group` и `single_assignment` данные-член.

[!code-cpp[concrt-futures#3](../../parallel/concrt/codesnippet/cpp/walkthrough-implementing-futures_2.cpp)]

1. В `public` раздел `async_future` , следует реализовать конструктор. Конструктор — это шаблон, который параметризуется по рабочей функции, вычисляющей результат. Конструктор асинхронно выполняет рабочую функцию в `task_group` данных и использует [concurrency::send](reference/concurrency-namespace-functions.md#send) функцию для записи результата `single_assignment` элемент данных.

[!code-cpp[concrt-futures#4](../../parallel/concrt/codesnippet/cpp/walkthrough-implementing-futures_3.cpp)]

1. В `public` раздел `async_future` , следует реализовать деструктор. Деструктор ожидает завершения задачи.

[!code-cpp[concrt-futures#5](../../parallel/concrt/codesnippet/cpp/walkthrough-implementing-futures_4.cpp)]

1. В `public` раздел `async_future` , следует реализовать `get` метод. Этот метод использует [concurrency::receive](reference/concurrency-namespace-functions.md#receive) функции для извлечения результата рабочей функции.

[!code-cpp[concrt-futures#6](../../parallel/concrt/codesnippet/cpp/walkthrough-implementing-futures_5.cpp)]

## <a name="example"></a>Пример

### <a name="description"></a>Описание

В следующем примере показан полный `async_future` класс и пример его использования. `wmain` Функция создает объект std::[вектор](../../standard-library/vector-class.md) , содержащий 10 000 случайных целых чисел. Затем он использует `async_future` объектов, чтобы найти наименьшее и наибольшее значения, содержащиеся в `vector` объекта.

### <a name="code"></a>Код

[!code-cpp[concrt-futures#1](../../parallel/concrt/codesnippet/cpp/walkthrough-implementing-futures_6.cpp)]

### <a name="comments"></a>Комментарии

В этом примере выводятся следующие данные:

```Output
smallest: 0
largest:  9999
average:  4981
```

В примере используется `async_future::get` метод для получения результатов вычисления. `async_future::get` Метод ожидает завершения, если вычисление по-прежнему активна вычисления.

## <a name="robust-programming"></a>Отказоустойчивость

Чтобы расширить `async_future` класса, чтобы обрабатывать исключения, вызываемые рабочей функцией, измените `async_future::get` метод для вызова [Concurrency::task_group:: wait](reference/task-group-class.md#wait) метод. `task_group::wait` Метод создает все исключения, которые были созданы в рабочей функции.

В следующем примере показано измененную версию `async_future` класса. `wmain` Функция использует `try` - `catch` блока для печати результата `async_future` объекта или для вывода значения исключения, созданного рабочей функции.

[!code-cpp[concrt-futures-with-eh#1](../../parallel/concrt/codesnippet/cpp/walkthrough-implementing-futures_7.cpp)]

В этом примере выводятся следующие данные:

```Output
caught exception: error
```

Дополнительные сведения о модели обработки исключений в среде выполнения с параллелизмом, см. в разделе [обработка исключений](../../parallel/concrt/exception-handling-in-the-concurrency-runtime.md).

## <a name="compiling-the-code"></a>Компиляция кода

Скопируйте код примера и вставьте его в проект Visual Studio или вставьте его в файл с именем `futures.cpp` и выполните следующую команду в окне командной строки Visual Studio.

**CL.exe futures.cpp/EHsc**

## <a name="see-also"></a>См. также

[Пошаговые руководства по среде выполнения с параллелизмом](../../parallel/concrt/concurrency-runtime-walkthroughs.md)<br/>
[Обработка исключений](../../parallel/concrt/exception-handling-in-the-concurrency-runtime.md)<br/>
[Класс task_group](reference/task-group-class.md)<br/>
[Класс single_assignment](../../parallel/concrt/reference/single-assignment-class.md)
