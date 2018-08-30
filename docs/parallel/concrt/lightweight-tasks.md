---
title: Упрощенные задачи | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- lightweight tasks
ms.assetid: b6dcfc7a-9fa9-4144-96a6-2845ea272017
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 8548412436be6e505c0ea08a2991e6948496f592
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/29/2018
ms.locfileid: "43210288"
---
# <a name="lightweight-tasks"></a>Упрощенные задачи
В этом документе описывается роль упрощенных задач в среде выполнения с параллелизмом. Объект *упрощенная задача* — это задача, планируемая непосредственно из `concurrency::Scheduler` или `concurrency::ScheduleGroup` объекта. Упрощенная задача похоже на функцию, который предоставляется Windows API [CreateThread](/windows/desktop/api/processthreadsapi/nf-processthreadsapi-createthread) функции. Таким образом упрощенные задачи полезны при адаптации существующего кода для использования функции планирования среды выполнения с параллелизмом. Сама среда выполнения с параллелизмом использует упрощенных задач для планирования асинхронных агентов и обмен сообщениями между асинхронные блоки сообщений.  
  
> [!TIP]
>  Среда выполнения с параллелизмом предоставляет планировщик по умолчанию, и таким образом не требуется создавать планировщик в приложении. Поскольку планировщик задач помогает оптимизировать производительность приложений, мы рекомендуем начать с [библиотеки параллельных шаблонов (PPL)](../../parallel/concrt/parallel-patterns-library-ppl.md) или [Asynchronous Agents Library](../../parallel/concrt/asynchronous-agents-library.md) при наличии создать среду выполнения с параллелизмом.  
  
 Упрощенные задачи дают меньше ресурсов, чем асинхронные агенты и группы задач. Например среда выполнения не информирует после завершения упрощенной задачи. Кроме того среда выполнения не перехватывать и обрабатывать исключения, возникающие в упрощенной задачи. Дополнительные сведения об обработке исключений и упрощенных задач см. в разделе [обработка исключений](../../parallel/concrt/exception-handling-in-the-concurrency-runtime.md).  
  
 Для выполнения большинства задач рекомендуется использовать более надежные функции, такие как группы задач и параллельных алгоритмов так как они позволяют более легко разбить сложные задачи на более простые. Дополнительные сведения о группах задач см. в разделе [параллелизм задач](../../parallel/concrt/task-parallelism-concurrency-runtime.md). Дополнительные сведения об алгоритмах параллельных операций, см. в разделе [параллельные алгоритмы](../../parallel/concrt/parallel-algorithms.md).  
  
 Для создания упрощенной задачи вызовите [Concurrency::ScheduleGroup:: ScheduleTask](reference/schedulegroup-class.md#scheduletask), [Concurrency::CurrentScheduler:: ScheduleTask](reference/currentscheduler-class.md#scheduletask), или [Concurrency::Scheduler:: ScheduleTask ](reference/scheduler-class.md#scheduletask) метод. Чтобы дождаться завершения упрощенной задачи, дождитесь родительского планировщика выключить или использовать механизм синхронизации, такие как [concurrency::event](../../parallel/concrt/reference/event-class.md) объекта.  
  
## <a name="example"></a>Пример  
 Пример, демонстрирующий способы адаптации существующего кода к использованию упрощенной задачи, см. в разделе [Пошаговое руководство: адаптации существующего кода для использования упрощенных задач](../../parallel/concrt/walkthrough-adapting-existing-code-to-use-lightweight-tasks.md).  
  
## <a name="see-also"></a>См. также  
 [Планировщик задач](../../parallel/concrt/task-scheduler-concurrency-runtime.md)   
 [Пошаговое руководство. Адаптация существующего кода для использования упрощенных задач](../../parallel/concrt/walkthrough-adapting-existing-code-to-use-lightweight-tasks.md)

