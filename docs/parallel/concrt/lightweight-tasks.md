---
title: Упрощенные задачи | Документы Microsoft
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
ms.openlocfilehash: d602f83cfe2da6bc1506e07720d3ef021ebce04a
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2018
ms.locfileid: "33687417"
---
# <a name="lightweight-tasks"></a>Упрощенные задачи
В этом документе описывается роль упрощенных задач в среде выполнения с параллелизмом. Объект *упрощенной задачи* — это задача, планируемая непосредственно из `concurrency::Scheduler` или `concurrency::ScheduleGroup` объекта. Упрощенная задача похоже на функцию, указываемое в API Windows [CreateThread](http://msdn.microsoft.com/library/windows/desktop/ms682453) функции. Таким образом упрощенные задачи полезны при адаптации существующего кода для использования функциональных возможностей планирования среды выполнения с параллелизмом. Среда выполнения с параллелизмом упрощенные задачи используются для планирования асинхронных агентов и отправки сообщений между асинхронные блоки сообщений.  
  
> [!TIP]
>  Среда выполнения с параллелизмом предоставляет планировщик по умолчанию, и таким образом не требуется создавать планировщик в приложении. Поскольку планировщик задач помогает оптимизировать производительность приложений, рекомендуется начать с [библиотеки параллельных шаблонов (PPL)](../../parallel/concrt/parallel-patterns-library-ppl.md) или [библиотеки асинхронных агентов](../../parallel/concrt/asynchronous-agents-library.md) при наличии новые и среда выполнения с параллелизмом.  
  
 Упрощенные задачи дают меньше ресурсов, чем асинхронные агенты и группы задач. Например среда выполнения не сообщит о завершении упрощенной задачи. Кроме того среда выполнения не перехватывать и обрабатывать исключения, возникающие в упрощенной задачи. Дополнительные сведения об обработке исключений и упрощенных задач см. в разделе [обработка исключений](../../parallel/concrt/exception-handling-in-the-concurrency-runtime.md).  
  
 Для большинства задач рекомендуется использовать более надежные функциональные возможности, такие как группы задач и параллельные алгоритмы, так как они позволяют легко разбить сложные задачи на более простые. Дополнительные сведения о группах задач см. в разделе [параллелизм задач](../../parallel/concrt/task-parallelism-concurrency-runtime.md). Дополнительные сведения о параллельных алгоритмах см. в разделе [параллельные алгоритмы](../../parallel/concrt/parallel-algorithms.md).  
  
 Для создания упрощенной задачи вызовите [Concurrency::ScheduleGroup:: ScheduleTask](reference/schedulegroup-class.md#scheduletask), [Concurrency::CurrentScheduler:: ScheduleTask](reference/currentscheduler-class.md#scheduletask), или [Concurrency::Scheduler:: ScheduleTask ](reference/scheduler-class.md#scheduletask) метод. Чтобы дождаться завершения упрощенной задачи, необходимо дождаться родительского планировщика завершать работу, или использовать механизм синхронизации, такие как [concurrency::event](../../parallel/concrt/reference/event-class.md) объекта.  
  
## <a name="example"></a>Пример  
 Пример, демонстрирующий, как адаптировать имеющийся код для использования упрощенных задач см. в разделе [Пошаговое руководство: адаптации существующего кода для использования упрощенных задач](../../parallel/concrt/walkthrough-adapting-existing-code-to-use-lightweight-tasks.md).  
  
## <a name="see-also"></a>См. также  
 [Планировщик задач](../../parallel/concrt/task-scheduler-concurrency-runtime.md)   
 [Пошаговое руководство. Адаптация существующего кода для использования упрощенных задач](../../parallel/concrt/walkthrough-adapting-existing-code-to-use-lightweight-tasks.md)

