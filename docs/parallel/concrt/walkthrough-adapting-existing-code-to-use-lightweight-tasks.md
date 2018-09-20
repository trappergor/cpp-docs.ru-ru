---
title: 'Пошаговое руководство: Адаптация существующего кода для использования упрощенных задач | Документация Майкрософт'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- using lightweight tasks [Concurrency Runtime]
- lightweight tasks, using [Concurrency Runtime]
ms.assetid: 1edfe818-d274-46de-bdd3-e92967c9bbe0
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c8b8369075d2d931d794b8299660cb5f3aa614fe
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46424629"
---
# <a name="walkthrough-adapting-existing-code-to-use-lightweight-tasks"></a>Пошаговое руководство. Адаптация существующего кода для использования упрощенных задач

В этом разделе показано, как адаптировать имеющийся код, использующее Windows API для создания и выполнения потока используется упрощенная задача.

Объект *упрощенная задача* — это задача, планируемая непосредственно из [concurrency::Scheduler](../../parallel/concrt/reference/scheduler-class.md) или [concurrency::ScheduleGroup](../../parallel/concrt/reference/schedulegroup-class.md) объекта. Упрощенные задачи полезны при адаптации существующего кода к использованию функциональных возможностей планирования среды выполнения с параллелизмом.

## <a name="prerequisites"></a>Предварительные требования

Прежде чем приступать к этому руководству, прочитайте статью [планировщик](../../parallel/concrt/task-scheduler-concurrency-runtime.md).

## <a name="example"></a>Пример

### <a name="description"></a>Описание

В следующем примере демонстрируется типичное использование API Windows для создания и выполнения потока. В этом примере используется [CreateThread](/windows/desktop/api/processthreadsapi/nf-processthreadsapi-createthread) функция, вызываемая `MyThreadFunction` в отдельном потоке.

### <a name="code"></a>Код

[!code-cpp[concrt-windows-threads#1](../../parallel/concrt/codesnippet/cpp/walkthrough-adapting-existing-code-to-use-lightweight-tasks_1.cpp)]

### <a name="comments"></a>Комментарии

В этом примере формируются следующие данные:

```Output
Parameters = 50, 100
```

Ниже показано, как адаптировать в примере кода для использования среды выполнения с параллелизмом для выполнения той же задачи.

### <a name="to-adapt-the-example-to-use-a-lightweight-task"></a>Чтобы адаптировать этот пример для использования упрощенных задач

1. Добавление `#include` директив для файла заголовка concrt.h.

[!code-cpp[concrt-migration-lwt#2](../../parallel/concrt/codesnippet/cpp/walkthrough-adapting-existing-code-to-use-lightweight-tasks_2.cpp)]

1. Добавить `using` директив для `concurrency` пространства имен.

[!code-cpp[concrt-migration-lwt#3](../../parallel/concrt/codesnippet/cpp/walkthrough-adapting-existing-code-to-use-lightweight-tasks_3.cpp)]

1. Измените объявление `MyThreadFunction` использовать `__cdecl` соглашение о вызовах и возврата `void`.

[!code-cpp[concrt-migration-lwt#4](../../parallel/concrt/codesnippet/cpp/walkthrough-adapting-existing-code-to-use-lightweight-tasks_4.cpp)]

1. Изменить `MyData` структуры для включения [concurrency::event](../../parallel/concrt/reference/event-class.md) , сообщающий главному приложению, что задача завершена.

[!code-cpp[concrt-migration-lwt#5](../../parallel/concrt/codesnippet/cpp/walkthrough-adapting-existing-code-to-use-lightweight-tasks_5.cpp)]

1. Замените вызов `CreateThread` вызовом [Concurrency::CurrentScheduler:: ScheduleTask](reference/currentscheduler-class.md#scheduletask) метод.

[!code-cpp[concrt-migration-lwt#6](../../parallel/concrt/codesnippet/cpp/walkthrough-adapting-existing-code-to-use-lightweight-tasks_6.cpp)]

1. Замените вызов `WaitForSingleObject` вызовом [Concurrency::Event:: wait](reference/event-class.md#wait) метод для ожидания завершения задачи.

[!code-cpp[concrt-migration-lwt#7](../../parallel/concrt/codesnippet/cpp/walkthrough-adapting-existing-code-to-use-lightweight-tasks_7.cpp)]

1. Удалите вызов `CloseHandle`.

1. Изменить подпись определение `MyThreadFunction` в соответствии с шагом 3.

[!code-cpp[concrt-migration-lwt#8](../../parallel/concrt/codesnippet/cpp/walkthrough-adapting-existing-code-to-use-lightweight-tasks_8.cpp)]

9. В конце `MyThreadFunction` вызовите метод [Concurrency::Event:: set](reference/event-class.md#set) метод для указания главному приложению, что задача завершена.

[!code-cpp[concrt-migration-lwt#9](../../parallel/concrt/codesnippet/cpp/walkthrough-adapting-existing-code-to-use-lightweight-tasks_9.cpp)]

10. Удалить `return` инструкции от `MyThreadFunction`.

## <a name="example"></a>Пример

### <a name="description"></a>Описание

Завершенные пример кода, использующего упрощенной задачи вызовите `MyThreadFunction` функции.

### <a name="code"></a>Код

[!code-cpp[concrt-migration-lwt#1](../../parallel/concrt/codesnippet/cpp/walkthrough-adapting-existing-code-to-use-lightweight-tasks_10.cpp)]

### <a name="comments"></a>Комментарии

## <a name="see-also"></a>См. также

[Планировщик задач](../../parallel/concrt/task-scheduler-concurrency-runtime.md)<br/>
[Класс Scheduler](../../parallel/concrt/reference/scheduler-class.md)
