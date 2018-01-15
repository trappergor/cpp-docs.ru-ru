---
title: "Упрощенные задачи | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: lightweight tasks
ms.assetid: b6dcfc7a-9fa9-4144-96a6-2845ea272017
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 010f5fd443271bec1d28b6760f0c17f4e17d803b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
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

