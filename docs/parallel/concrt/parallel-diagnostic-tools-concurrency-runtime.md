---
title: "Средства диагностики параллельного выполнения (среда выполнения с параллелизмом) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Средства диагностики параллельного выполнения [среда выполнения с параллелизмом]"
ms.assetid: b1a3f1d2-f5df-4f29-852e-906b3d8341fc
caps.latest.revision: 15
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 14
---
# Средства диагностики параллельного выполнения (среда выполнения с параллелизмом)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

[!INCLUDE[vsprvs](../../assembler/masm/includes/vsprvs_md.md)] обеспечивает расширенную поддержку отладки и профилирования многопоточных приложений.  
  
## Отладка  
 Отладчик Visual Studio включает окно **Параллельные стеки**, окно **Параллельные задачи** и окно **Контроль параллельных данных**.  Дополнительные сведения см. в разделах [Пошаговое руководство. Отладка параллельного приложения](../Topic/Walkthrough:%20Debugging%20a%20Parallel%20Application.md) и [Практическое руководство. Использование окна параллельных контрольных значений](../Topic/How%20to:%20Use%20the%20Parallel%20Watch%20Window.md).  
  
## Профилирование  
 Средства профилирования предоставляют три представления данных, отображающих графическую, табличную и числовую информацию о том, как многопоточное приложение взаимодействует с самим собой и с другими программами.  Представления позволяют быстро определить необходимые области и перейти из точек на графических изображениях к стекам вызовов, местам вызовов и исходному коду.  Для получения дополнительной информации см. [Визуализатор параллелизма](../Topic/Concurrency%20Visualizer.md).  
  
## Трассировка событий  
 Среда выполнения с параллелизмом использует [Трассировку событий Windows](http://msdn.microsoft.com/library/windows/desktop/bb968803) \(ETW\), чтобы уведомлять средства инструментирования, например профилировщики, о различных событиях.  К этим событиям может относится активация или отключение планировщика, запуск, окончание, блокировка, разблокировка или передача контекста, а также запуск и окончание параллельного алгоритма.  
  
 Эту функцию используют такие средства, как [Визуализатор параллелизма](../Topic/Concurrency%20Visualizer.md); обычно не требуется работать с этими событиями непосредственно.  Однако эти события полезны при разработке пользовательского профилировщика или при использовании таких средств трассировки событий, как [Xperf](http://go.microsoft.com/fwlink/?LinkID=160628).  
  
 Среда выполнения с параллелизмом создает эти события только при включенной трассировке.  Чтобы включить трассировку событий, следует вызвать функцию [concurrency::EnableTracing](../Topic/EnableTracing%20Function.md), а чтобы выключить — функцию [concurrency::DisableTracing](../Topic/DisableTracing%20Function.md).  
  
 В следующей таблице перечислены события, которые создает среда выполнения при включенной трассировке.  
  
|Событие|Описание|Значение|  
|-------------|--------------|--------------|  
|[concurrency::ConcRT\_ProviderGuid](../Topic/ConcRT_ProviderGuid%20Constant.md)|Идентификатор поставщика ETW для среды выполнения с параллелизмом.|`f7b697a3-4db5-4d3b-be71-c4d284e6592f`|  
|[concurrency::ContextEventGuid](../Topic/ContextEventGuid%20Constant.md)|Отмечает события, связанные с контекстами.|`5727a00f-50be-4519-8256-f7699871fecb`|  
|[concurrency::PPLParallelForEventGuid](../Topic/PPLParallelForEventGuid%20Constant.md)|Отмечает входы и выходы вызовов алгоритма [concurrency::parallel\_for](../Topic/parallel_for%20Function.md).|`31c8da6b-6165-4042-8b92-949e315f4d84`|  
|[concurrency::PPLParallelForeachEventGuid](../Topic/PPLParallelForeachEventGuid%20Constant.md)|Отмечает входы и выходы вызовов алгоритма [concurrency::parallel\_for\_each](../Topic/parallel_for_each%20Function.md).|`5cb7d785-9d66-465d-bae1-4611061b5434`|  
|[concurrency::PPLParallelInvokeEventGuid](../Topic/PPLParallelInvokeEventGuid%20Constant.md)|Отмечает входы и выходы вызовов алгоритма [concurrency::parallel\_invoke](../Topic/parallel_invoke%20Function.md).|`d1b5b133-ec3d-49f4-98a3-464d1a9e4682`|  
|[concurrency::SchedulerEventGuid](../Topic/SchedulerEventGuid%20Constant.md)|Отмечает события, связанные с [планировщиком заданий](../../parallel/concrt/task-scheduler-concurrency-runtime.md).|`e2091f8a-1e0a-4731-84a2-0dd57c8a5261`|  
|[concurrency::VirtualProcessorEventGuid](../Topic/VirtualProcessorEventGuid%20Constant.md)|Отмечает события, связанные с виртуальными процессорами.|`2f27805f-1676-4ecc-96fa-7eb09d44302f`|  
  
 Среда выполнения с параллелизмом определяет, но на настоящий момент не создает следующие события.  Среда выполнения резервирует эти события для использования в будущем.  
  
-   [concurrency::ConcRTEventGuid](../Topic/ConcRTEventGuid%20Constant.md)  
  
-   [concurrency::ScheduleGroupEventGuid](../Topic/SchedulerEventGuid%20Constant.md)  
  
-   [concurrency::ChoreEventGuid](../Topic/ChoreEventGuid%20Constant.md)  
  
-   [concurrency::LockEventGuid](../Topic/LockEventGuid%20Constant.md)  
  
-   [concurrency::ResourceManagerEventGuid](../Topic/ResourceManagerEventGuid%20Constant.md)  
  
 Перечисление [concurrency::ConcRT\_EventType](../Topic/ConcRT_EventType%20Enumeration.md) указывает возможные операции, отслеживаемые событием.  Например, при входе алгоритма `parallel_for` среда выполнения создает событие `PPLParallelForEventGuid` и предоставляет в качестве операции `CONCRT_EVENT_START`.  Перед выполнением алгоритмом `parallel_for` возврата среда выполнения еще раз создает событие `PPLParallelForEventGuid` и предоставляет в качестве операции `CONCRT_EVENT_END`.  
  
 В следующем примере показано, как включить трассировку вызова `parallel_for`.  Среда выполнения не трассирует первый вызов `parallel_for`, потому что трассировка не включена.  Вызов `EnableTracing` позволяет среде выполнения трассировать второй вызов `parallel_for`.  
  
 [!code-cpp[concrt-etw#1](../../parallel/concrt/codesnippet/CPP/parallel-diagnostic-tools-concurrency-runtime_1.cpp)]  
  
 Среда выполнения трассирует, сколько раз производятся вызовы к `EnableTracing` и `DisableTracing`.  Если вызвать `EnableTracing` несколько раз, чтобы отключить трассировку, необходимо столько же раз вызвать `DisableTracing`.  
  
## См. также  
 [Среда выполнения с параллелизмом](../../parallel/concrt/concurrency-runtime.md)