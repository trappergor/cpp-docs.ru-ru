---
title: Практическое руководство. Создание задачи, выполняемой после задержки
description: Создание задачи, которая завершается после задержки с помощью библиотеки PPL ConcRT.
ms.date: 10/19/2020
helpviewer_keywords:
- task_completion_event class, example
- create a task that completes after a delay, example [C++]
ms.assetid: 3fc0a194-3fdb-4eba-8b8a-b890981a985d
ms.openlocfilehash: 694b6190a7ec60043a5674e920dc54e6e7bf0eb6
ms.sourcegitcommit: 19016630f9d35f365e9ba249e0f3617515d7ca33
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/20/2020
ms.locfileid: "92274557"
---
# <a name="how-to-create-a-task-that-completes-after-a-delay"></a>Практическое руководство. Создание задачи, выполняемой после задержки

В этом примере показано, как использовать [`concurrency::task`](../../parallel/concrt/reference/task-class.md) классы,, [`concurrency::cancellation_token_source`](../../parallel/concrt/reference/cancellation-token-source-class.md) [`concurrency::cancellation_token`](../../parallel/concrt/reference/cancellation-token-class.md) ,, [`concurrency::task_completion_event`](../../parallel/concrt/reference/task-completion-event-class.md) [`concurrency::timer`](../../parallel/concrt/reference/timer-class.md) и [`concurrency::call`](../../parallel/concrt/reference/call-class.md) для создания задачи, которая завершается после некоторой задержки. Этот метод можно использовать для создания циклов, которые периодически опрашивают данные. Можно также ввести время ожидания, отложенную обработку вводимых пользователем данных для предварительно определенного времени и т. д.

## <a name="example-complete_after-and-cancel_after_timeout-functions"></a>Пример: функции complete_after и cancel_after_timeout

В следующем примере показаны функции `complete_after` и `cancel_after_timeout`. Функция `complete_after` создает объект `task`, который выполняется после заданной задержки. Она использует объект `timer` и объект `call` для установки объекта `task_completion_event` после заданной задержки. С помощью класса `task_completion_event` можно определить задачу, которая выполняется после того, как поток или другая задача сообщает, что значение доступно. Когда событие установлено, задачи прослушивателя выполняются и их продолжения планируются для запуска.

> [!TIP]
> Дополнительные сведения о `timer` `call` классах и, которые являются частью библиотеки асинхронных агентов, см. в разделе [асинхронные блоки сообщений](../../parallel/concrt/asynchronous-message-blocks.md).

`cancel_after_timeout`Функция создает `complete_after` функцию для отмены задачи, если эта задача не завершается до заданного времени ожидания. Функция `cancel_after_timeout` создает две задачи. Первая задача указывает на успешное выполнение и завершение после выполнения указанной задачи. Вторая задача указывает на сбой и завершается через указанное время ожидания. Функция `cancel_after_timeout` создает задачу продолжения, которая выполняется после выполнения задачи, связанной с успешным или неудачным результатом. Если задача, связанная с неудачным результатом, завершается первой, продолжение отменяет источник токена для отмены всей задачи.

[!code-cpp[concrt-task-delay#1](../../parallel/concrt/codesnippet/cpp/how-to-create-a-task-that-completes-after-a-delay_1.cpp)]

## <a name="example-compute-count-of-prime-numbers"></a>Пример. Вычисление количества простых чисел

В следующем примере вычисляется количество простых чисел в диапазоне [0, 100000] несколько раз. Операция завершается ошибкой, если она не завершается в течение заданного предела времени. Функция `count_primes` демонстрирует, как использовать функцию `cancel_after_timeout`. Он подсчитывает количество простых значений в заданном диапазоне и завершается ошибкой, если задача не завершается в указанное время. Функция `wmain` несколько раз вызывает функцию `count_primes`. Каждый раз она сокращает выделенное время в два раза. Программа завершает работу после того, как операция не завершится за текущий предел времени.

[!code-cpp[concrt-task-delay#2](../../parallel/concrt/codesnippet/cpp/how-to-create-a-task-that-completes-after-a-delay_2.cpp)]

При использовании этого метода для отмены задач после некоторой задержки все незапущенные задачи не запускаются после отмены общей задачи. Однако очень важно, чтобы все длительные задачи быстро отвечали на отмену. Дополнительные сведения об отмене задач см. [в разделе Отмена в библиотеке PPL](cancellation-in-the-ppl.md).

## <a name="complete-code-example"></a>Полный пример кода

Ниже приведен полный код этого примера.

[!code-cpp[concrt-task-delay#3](../../parallel/concrt/codesnippet/cpp/how-to-create-a-task-that-completes-after-a-delay_3.cpp)]

## <a name="compiling-the-code"></a>Компиляция кода

Чтобы скомпилировать код, скопируйте его и вставьте в проект Visual Studio или вставьте в файл с именем, `task-delay.cpp` а затем выполните следующую команду в окне командной строки Visual Studio.

**cl.exe/EHsc ТАСК-делай. cpp**

## <a name="see-also"></a>См. также раздел

[Параллельное выполнение задач](../../parallel/concrt/task-parallelism-concurrency-runtime.md)<br/>
[Класс Task (среда выполнения с параллелизмом)](../../parallel/concrt/reference/task-class.md)<br/>
[Класс cancellation_token_source](../../parallel/concrt/reference/cancellation-token-source-class.md)<br/>
[Класс cancellation_token](../../parallel/concrt/reference/cancellation-token-class.md)<br/>
[Класс task_completion_event](../../parallel/concrt/reference/task-completion-event-class.md)<br/>
[Класс Timer](../../parallel/concrt/reference/timer-class.md)<br/>
[Класс Call](../../parallel/concrt/reference/call-class.md)<br/>
[Асинхронные блоки сообщений](../../parallel/concrt/asynchronous-message-blocks.md)<br/>
[Отмена в библиотеке параллельных шаблонов](cancellation-in-the-ppl.md)
