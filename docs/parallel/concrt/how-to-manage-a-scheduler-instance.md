---
title: Как выполнить Управление экземпляром планировщика
ms.date: 11/04/2016
helpviewer_keywords:
- managing a scheduler instance [Concurrency Runtime]
- scheduler instances, managing [Concurrency Runtime]
ms.assetid: 2cc804f0-5ff3-498b-97f1-a9f67a005448
ms.openlocfilehash: d8e79f7c132abd8e43f661f4dc7c7bb758cb2a6d
ms.sourcegitcommit: c85c8a1226d8fbbaa29f4691ed719f8e6cc6575c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2019
ms.locfileid: "54893994"
---
# <a name="how-to-manage-a-scheduler-instance"></a>Как выполнить Управление экземпляром планировщика

Экземпляры планировщика позволяют связывать конкретные политики планирования с различными видами рабочих нагрузок. В этом разделе содержит две простые примеры, демонстрирующие создание и управление экземпляром планировщика.

В примерах создаются планировщики, использующих политики планировщика по умолчанию. Пример создания планировщика, который использует пользовательскую политику, см. в разделе [как: Задание определенных политик планировщика](../../parallel/concrt/how-to-specify-specific-scheduler-policies.md).

### <a name="to-manage-a-scheduler-instance-in-your-application"></a>Управление экземпляром планировщика в приложении

1. Создание [concurrency::SchedulerPolicy](../../parallel/concrt/reference/schedulerpolicy-class.md) значения объекта, который содержит политику для планировщика для использования.

1. Вызовите [Concurrency::CurrentScheduler:: CREATE](reference/currentscheduler-class.md#create) метод или [Concurrency::Scheduler:: CREATE](reference/scheduler-class.md#create) метод для создания экземпляра планировщика.

   Если вы используете `Scheduler::Create` мы вызываем метод [Concurrency::Scheduler:: Attach](reference/scheduler-class.md#attach) метод, если вам нужно связать планировщик с текущим контекстом.

1. Вызовите [CreateEvent](/windows/desktop/api/synchapi/nf-synchapi-createeventa) функции для создания дескриптора объекта несигнальное, автоматического сброса события.

1. Передайте дескриптор объекта события, который вы только что создали для [Concurrency::CurrentScheduler:: registershutdownevent](reference/currentscheduler-class.md#registershutdownevent) метод или [Concurrency::Scheduler:: registershutdownevent](reference/scheduler-class.md#registershutdownevent) метод. При этом регистрируется событие для настройки при уничтожении планировщика.

1. Выполните задачи, которые должны текущий планировщик для планирования.

1. Вызовите [Concurrency::CurrentScheduler:: Detach](reference/currentscheduler-class.md#detach) метод для отсоединения текущего планировщика и восстановить предыдущий планировщик в качестве текущего.

   Если вы используете `Scheduler::Create` мы вызываем метод [Concurrency::Scheduler:: Release](reference/scheduler-class.md#release) метод, чтобы уменьшить количество ссылок на `Scheduler` объекта.

1. Передайте дескриптор события [WaitForSingleObject](/windows/desktop/api/synchapi/nf-synchapi-waitforsingleobject) функции для ожидания завершения работы планировщика.

1. Вызовите [CloseHandle](/windows/desktop/api/handleapi/nf-handleapi-closehandle) функцию, чтобы закрыть дескриптор объекта события.

## <a name="example"></a>Пример

Приведенный ниже показаны два способа управление экземпляром планировщика. В каждом примере сначала используется планировщик по умолчанию для выполнения задачи, который выводит уникальный идентификатор текущего планировщика. Затем в каждом примере используется экземпляр планировщика для выполнения той же задачи, еще раз. Наконец каждый пример восстанавливает планировщик по умолчанию, что и текущий и выполняет задачу еще раз.

В первом примере используется [concurrency::CurrentScheduler](../../parallel/concrt/reference/currentscheduler-class.md) класса для создания экземпляра планировщика и связывания его с текущим контекстом. Второй пример использует [concurrency::Scheduler](../../parallel/concrt/reference/scheduler-class.md) классом для выполнения той же задачи. Как правило `CurrentScheduler` класс используется для работы с текущего планировщика. Во втором примере, который использует `Scheduler` класса, полезно, если вы хотите управлять, когда планировщик связан с текущим контекстом, или если вы хотите связать конкретные планировщики с конкретными задачами.

[!code-cpp[concrt-scheduler-instance#1](../../parallel/concrt/codesnippet/cpp/how-to-manage-a-scheduler-instance_1.cpp)]

В этом примере формируются следующие данные:

```Output
Using CurrentScheduler class...

Current scheduler id: 0
Creating and attaching scheduler...
Current scheduler id: 1
Detaching scheduler...
Current scheduler id: 0

Using Scheduler class...

Current scheduler id: 0
Creating scheduler...
Attaching scheduler...
Current scheduler id: 2
Detaching scheduler...
Current scheduler id: 0
```

## <a name="compiling-the-code"></a>Компиляция кода

Скопируйте код примера и вставьте его в проект Visual Studio или вставьте его в файл с именем `scheduler-instance.cpp` и выполните следующую команду в окне командной строки Visual Studio.

**/ EHsc CL.exe scheduler-instance.cpp**

## <a name="see-also"></a>См. также

[Экземпляры планировщика](../../parallel/concrt/scheduler-instances.md)<br/>
[Практическое руководство. Задание определенных политик планировщика](../../parallel/concrt/how-to-specify-specific-scheduler-policies.md)

