---
title: Пошаговое руководство. Адаптация существующего кода для использования упрощенных задач
ms.date: 04/25/2019
helpviewer_keywords:
- using lightweight tasks [Concurrency Runtime]
- lightweight tasks, using [Concurrency Runtime]
ms.assetid: 1edfe818-d274-46de-bdd3-e92967c9bbe0
ms.openlocfilehash: e7c6096829a1cd45cfdb849a1899d6b4a2d4cb78
ms.sourcegitcommit: a8ef52ff4a4944a1a257bdaba1a3331607fb8d0f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/11/2020
ms.locfileid: "77141999"
---
# <a name="walkthrough-adapting-existing-code-to-use-lightweight-tasks"></a>Пошаговое руководство. Адаптация существующего кода для использования упрощенных задач

В этом разделе показано, как адаптировать существующий код, использующий API Windows, для создания и выполнения потока для использования упрощенной задачи.

*Упрощенная задача* — это задача, запланированная непосредственно из объекта [Concurrency:: Scheduler](../../parallel/concrt/reference/scheduler-class.md) или [Concurrency:: ScheduleGroup](../../parallel/concrt/reference/schedulegroup-class.md) . Упрощенные задачи полезны при адаптации существующего кода к использованию функциональных возможностей планирования среды выполнения с параллелизмом.

## <a name="prerequisites"></a>предварительные требования

Прежде чем приступить к работе с этим пошаговым руководством, ознакомьтесь с разделом [планировщик задач](../../parallel/concrt/task-scheduler-concurrency-runtime.md).

## <a name="example"></a>Пример

В следующем примере показано типичное использование API Windows для создания и выполнения потока. В этом примере функция [CreateThread](/windows/win32/api/processthreadsapi/nf-processthreadsapi-createthread) используется для вызова `MyThreadFunction` в отдельном потоке.

### <a name="initial-code"></a>Начальный код

[!code-cpp[concrt-windows-threads#1](../../parallel/concrt/codesnippet/cpp/walkthrough-adapting-existing-code-to-use-lightweight-tasks_1.cpp)]

В этом примере формируются следующие данные:

```Output
Parameters = 50, 100
```

Ниже показано, как адаптировать пример кода, чтобы использовать среда выполнения с параллелизмом для выполнения той же задачи.

### <a name="to-adapt-the-example-to-use-a-lightweight-task"></a>Адаптация примера для использования упрощенной задачи

1. Добавьте директиву `#include` для файла заголовка ConcRT. h.

[!code-cpp[concrt-migration-lwt#2](../../parallel/concrt/codesnippet/cpp/walkthrough-adapting-existing-code-to-use-lightweight-tasks_2.cpp)]

1. Добавьте директиву `using` для пространства имен `concurrency`.

[!code-cpp[concrt-migration-lwt#3](../../parallel/concrt/codesnippet/cpp/walkthrough-adapting-existing-code-to-use-lightweight-tasks_3.cpp)]

1. Измените объявление `MyThreadFunction` для использования `__cdecl` соглашения о вызовах и для возврата `void`.

[!code-cpp[concrt-migration-lwt#4](../../parallel/concrt/codesnippet/cpp/walkthrough-adapting-existing-code-to-use-lightweight-tasks_4.cpp)]

1. Измените структуру `MyData`, включив в нее объект [Concurrency:: Event](../../parallel/concrt/reference/event-class.md) , который сигнализирует главному приложению о завершении задачи.

[!code-cpp[concrt-migration-lwt#5](../../parallel/concrt/codesnippet/cpp/walkthrough-adapting-existing-code-to-use-lightweight-tasks_5.cpp)]

1. Замените вызов `CreateThread` вызовом метода [Concurrency:: CurrentScheduler:: ScheduleTask](reference/currentscheduler-class.md#scheduletask) .

[!code-cpp[concrt-migration-lwt#6](../../parallel/concrt/codesnippet/cpp/walkthrough-adapting-existing-code-to-use-lightweight-tasks_6.cpp)]

1. Замените вызов `WaitForSingleObject` вызовом метода [Concurrency:: Event:: wait](reference/event-class.md#wait) , чтобы дождаться завершения задачи.

[!code-cpp[concrt-migration-lwt#7](../../parallel/concrt/codesnippet/cpp/walkthrough-adapting-existing-code-to-use-lightweight-tasks_7.cpp)]

1. Удалите вызов `CloseHandle`.

1. Измените сигнатуру определения `MyThreadFunction` в соответствии с шагом 3.

[!code-cpp[concrt-migration-lwt#8](../../parallel/concrt/codesnippet/cpp/walkthrough-adapting-existing-code-to-use-lightweight-tasks_8.cpp)]

1. В конце функции `MyThreadFunction` вызовите метод [Concurrency:: Event:: Set](reference/event-class.md#set) , чтобы сообщить главному приложению о завершении задачи.

[!code-cpp[concrt-migration-lwt#9](../../parallel/concrt/codesnippet/cpp/walkthrough-adapting-existing-code-to-use-lightweight-tasks_9.cpp)]

1. Удалите инструкцию `return` из `MyThreadFunction`.

### <a name="completed-code"></a>Завершенный код

В следующем завершенном примере показан код, использующий упрощенную задачу для вызова функции `MyThreadFunction`.

[!code-cpp[concrt-migration-lwt#1](../../parallel/concrt/codesnippet/cpp/walkthrough-adapting-existing-code-to-use-lightweight-tasks_10.cpp)]

## <a name="see-also"></a>См. также раздел

[Планировщик заданий](../../parallel/concrt/task-scheduler-concurrency-runtime.md)<br/>
[Класс Scheduler](../../parallel/concrt/reference/scheduler-class.md)
