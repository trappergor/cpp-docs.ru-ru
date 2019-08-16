---
title: Пошаговое руководство. Адаптация существующего кода для использования упрощенных задач
ms.date: 04/25/2019
helpviewer_keywords:
- using lightweight tasks [Concurrency Runtime]
- lightweight tasks, using [Concurrency Runtime]
ms.assetid: 1edfe818-d274-46de-bdd3-e92967c9bbe0
ms.openlocfilehash: 406d4d24d0042c7bded4f94dcef1e7731ab3947f
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/15/2019
ms.locfileid: "69512150"
---
# <a name="walkthrough-adapting-existing-code-to-use-lightweight-tasks"></a>Пошаговое руководство. Адаптация существующего кода для использования упрощенных задач

В этом разделе показано, как адаптировать существующий код, использующий API Windows, для создания и выполнения потока для использования упрощенной задачи.

*Упрощенная задача* — это задача, запланированная непосредственно из объекта [Concurrency:: Scheduler](../../parallel/concrt/reference/scheduler-class.md) или [Concurrency:: ScheduleGroup](../../parallel/concrt/reference/schedulegroup-class.md) . Упрощенные задачи полезны при адаптации существующего кода к использованию функциональных возможностей планирования среды выполнения с параллелизмом.

## <a name="prerequisites"></a>Предварительные требования

Прежде чем приступить к работе с этим пошаговым руководством, ознакомьтесь с разделом [планировщик задач](../../parallel/concrt/task-scheduler-concurrency-runtime.md).

## <a name="example"></a>Пример

### <a name="description"></a>Описание

В следующем примере показано типичное использование API Windows для создания и выполнения потока. В этом примере функция [CreateThread](/windows/win32/api/processthreadsapi/nf-processthreadsapi-createthread) используется для вызова в `MyThreadFunction` отдельном потоке.

### <a name="code"></a>Код

[!code-cpp[concrt-windows-threads#1](../../parallel/concrt/codesnippet/cpp/walkthrough-adapting-existing-code-to-use-lightweight-tasks_1.cpp)]

### <a name="comments"></a>Комментарии

В этом примере формируются следующие данные:

```Output
Parameters = 50, 100
```

Ниже показано, как адаптировать пример кода, чтобы использовать среда выполнения с параллелизмом для выполнения той же задачи.

### <a name="to-adapt-the-example-to-use-a-lightweight-task"></a>Адаптация примера для использования упрощенной задачи

1. `#include` Добавьте директиву для файла заголовка ConcRT. h.

[!code-cpp[concrt-migration-lwt#2](../../parallel/concrt/codesnippet/cpp/walkthrough-adapting-existing-code-to-use-lightweight-tasks_2.cpp)]

1. Добавьте директиву `concurrency` для пространства имен. `using`

[!code-cpp[concrt-migration-lwt#3](../../parallel/concrt/codesnippet/cpp/walkthrough-adapting-existing-code-to-use-lightweight-tasks_3.cpp)]

1. Измените объявление `MyThreadFunction` , чтобы `__cdecl` использовать соглашение о вызовах и для возврата `void`.

[!code-cpp[concrt-migration-lwt#4](../../parallel/concrt/codesnippet/cpp/walkthrough-adapting-existing-code-to-use-lightweight-tasks_4.cpp)]

1. Измените структуру, включив в нее объект [Concurrency:: Event](../../parallel/concrt/reference/event-class.md) , который сигнализирует главному приложению о завершении задачи. `MyData`

[!code-cpp[concrt-migration-lwt#5](../../parallel/concrt/codesnippet/cpp/walkthrough-adapting-existing-code-to-use-lightweight-tasks_5.cpp)]

1. Замените вызов на `CreateThread` вызов метода [Concurrency:: CurrentScheduler:: ScheduleTask](reference/currentscheduler-class.md#scheduletask) .

[!code-cpp[concrt-migration-lwt#6](../../parallel/concrt/codesnippet/cpp/walkthrough-adapting-existing-code-to-use-lightweight-tasks_6.cpp)]

1. Замените вызов на `WaitForSingleObject` вызов метода [Concurrency:: Event:: wait](reference/event-class.md#wait) , чтобы дождаться завершения задачи.

[!code-cpp[concrt-migration-lwt#7](../../parallel/concrt/codesnippet/cpp/walkthrough-adapting-existing-code-to-use-lightweight-tasks_7.cpp)]

1. Удалите вызов `CloseHandle`.

1. Измените сигнатуру определения `MyThreadFunction` , чтобы она соответствовала шагу 3.

[!code-cpp[concrt-migration-lwt#8](../../parallel/concrt/codesnippet/cpp/walkthrough-adapting-existing-code-to-use-lightweight-tasks_8.cpp)]

9. В конце `MyThreadFunction` функции вызовите метод [Concurrency:: Event:: Set](reference/event-class.md#set) , чтобы сообщить главному приложению о завершении задачи.

[!code-cpp[concrt-migration-lwt#9](../../parallel/concrt/codesnippet/cpp/walkthrough-adapting-existing-code-to-use-lightweight-tasks_9.cpp)]

10. Удалите оператор из `MyThreadFunction`. `return`

## <a name="example"></a>Пример

### <a name="description"></a>Описание

В следующем завершенном примере показан код, использующий упрощенную задачу `MyThreadFunction` для вызова функции.

### <a name="code"></a>Код

[!code-cpp[concrt-migration-lwt#1](../../parallel/concrt/codesnippet/cpp/walkthrough-adapting-existing-code-to-use-lightweight-tasks_10.cpp)]

### <a name="comments"></a>Комментарии

## <a name="see-also"></a>См. также

[планировщик задач](../../parallel/concrt/task-scheduler-concurrency-runtime.md)<br/>
[Класс Scheduler](../../parallel/concrt/reference/scheduler-class.md)
