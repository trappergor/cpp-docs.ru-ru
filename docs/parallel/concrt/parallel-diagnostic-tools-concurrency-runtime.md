---
title: Параллельные средства диагностики (среда выполнения с параллелизмом) | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- Parallel Diagnostic Tools [Concurrency Runtime]
ms.assetid: b1a3f1d2-f5df-4f29-852e-906b3d8341fc
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 1cd3ce4c86332719e299c11fee3ffbee8b41c14f
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2018
ms.locfileid: "33693111"
---
# <a name="parallel-diagnostic-tools-concurrency-runtime"></a>Средства диагностики параллельного выполнения (среда выполнения с параллелизмом)
[!INCLUDE[vsprvs](../../assembler/masm/includes/vsprvs_md.md)] предоставляет расширенную поддержку отладки и профилирования многопоточных приложений.  
  
## <a name="debugging"></a>Отладка  
 Отладчик Visual Studio включает в себя **Параллельные стеки** окне **параллельные задачи** окна, и **контроль параллельных данных** окна. Дополнительные сведения см. в разделе [Пошаговое руководство: отладка параллельного приложения](/visualstudio/debugger/walkthrough-debugging-a-parallel-application) и [как: использование окна параллельных контрольных значений](/visualstudio/debugger/how-to-use-the-parallel-watch-window).  
  
## <a name="profiling"></a>Профилирование  
 Средства профилирования предоставляют три представления данных, отображающие графическую, табличную и числовую информацию о том, как многопоточное приложение взаимодействует с самим собой и с другими программами. Представления позволяют быстро определить проблемные области и перейти из точек на графических изображениях к стекам вызовов, местам вызовов и исходного кода. Дополнительные сведения см. в разделе [Визуализатор параллелизма](/visualstudio/profiling/concurrency-visualizer).  
  
## <a name="event-tracing"></a>Трассировка событий  
 Среда выполнения с параллелизмом использует [трассировки событий Windows](http://msdn.microsoft.com/library/windows/desktop/bb968803) (ETW), чтобы уведомлять средства инструментирования, такие как профилировщики, при возникновении различных событий. К этим событиям относятся при активации или деактивации планировщика, при контекста начинается, завершается, блокирует, разблокирует или дает и когда параллельный алгоритм начинается или заканчивается.  
  
 Такие средства, как [визуализатор параллелизма](/visualstudio/profiling/concurrency-visualizer) с помощью этой функции; таким образом, обычно не нужно напрямую работать с этими событиями. Однако эти события полезны при разработке пользовательского профилировщика или при использовании средства трассировки событий, таких как [Xperf](http://go.microsoft.com/fwlink/p/?linkid=160628).  
  
 Среда выполнения с параллелизмом создает эти события только в том случае, если трассировка включена. Вызовите [concurrency::EnableTracing](reference/concurrency-namespace-functions.md#enabletracing) функции, чтобы включить трассировку событий и [concurrency::DisableTracing](reference/concurrency-namespace-functions.md#disabletracing) функцию отключения трассировки.  
  
 В следующей таблице описаны события, которые среда выполнения вызывает при включенной трассировке событий:  
  
|событие|Описание|Значение|  
|-----------|-----------------|-----------|  

|[Concurrency::ConcRT_ProviderGuid](reference/concurrency-namespace-constants1.md#concrt_providerguid)| Идентификатор поставщика ETW для среды выполнения с параллелизмом. |`f7b697a3-4db5-4d3b-be71-c4d284e6592f`|  
|[Concurrency::ContextEventGuid](reference/concurrency-namespace-constants1.md#contexteventguid)| Отмечает события, связанные с контекстами. |`5727a00f-50be-4519-8256-f7699871fecb`|  
|[Concurrency::PPLParallelForEventGuid](reference/concurrency-namespace-constants1.md#pplparallelforeventguid)| Отмечает входы и выходы вызовов [concurrency::parallel_for](reference/concurrency-namespace-functions.md#parallel_for) алгоритма. |`31c8da6b-6165-4042-8b92-949e315f4d84`|  
|[Concurrency::PPLParallelForeachEventGuid](reference/concurrency-namespace-constants1.md#pplparallelforeacheventguid)| Отмечает входы и выходы вызовов [concurrency::parallel_for_each](reference/concurrency-namespace-functions.md#parallel_for_each) алгоритма. |`5cb7d785-9d66-465d-bae1-4611061b5434`|  
|[Concurrency::PPLParallelInvokeEventGuid](reference/concurrency-namespace-constants1.md#pplparallelinvokeeventguid)| Отмечает входы и выходы вызовов [concurrency::parallel_invoke](reference/concurrency-namespace-functions.md#parallel_invoke) алгоритма. |`d1b5b133-ec3d-49f4-98a3-464d1a9e4682`|  
|[Concurrency::SchedulerEventGuid](reference/concurrency-namespace-constants1.md#schedulereventguid)| Отмечает события, связанные с [планировщик](../../parallel/concrt/task-scheduler-concurrency-runtime.md). |`e2091f8a-1e0a-4731-84a2-0dd57c8a5261`|  
|[Concurrency::VirtualProcessorEventGuid](reference/concurrency-namespace-constants1.md#virtualprocessoreventguid)| Отмечает события, которые связаны с виртуальными процессорами. |`2f27805f-1676-4ecc-96fa-7eb09d44302f`|  
  
 Среда выполнения с параллелизмом определяет, но не вызывает в настоящее время, следующие события. Среда выполнения резервирует эти события для использования в будущем:  
  
-   [Concurrency::ConcRTEventGuid](reference/concurrency-namespace-constants1.md#concrteventguid)  
  
-   [Concurrency::ScheduleGroupEventGuid](reference/concurrency-namespace-constants1.md#schedulereventguid)  
  
-   [Concurrency::ChoreEventGuid](reference/concurrency-namespace-constants1.md#choreeventguid)  
  
-   [Concurrency::LockEventGuid](reference/concurrency-namespace-constants1.md#lockeventguid)  
  
-   [Concurrency::ResourceManagerEventGuid](reference/concurrency-namespace-constants1.md#resourcemanagereventguid)  
  
 [Concurrency::ConcRT_EventType](reference/concurrency-namespace-enums.md#concrt_eventtype) перечисления указывает возможные операции, которые отслеживает события. Например, при входе `parallel_for` алгоритма, среда выполнения вызывает `PPLParallelForEventGuid` событий и предоставляет `CONCRT_EVENT_START` используется в операции. Прежде чем `parallel_for` Возвращает алгоритм, среда выполнения снова вызывает `PPLParallelForEventGuid` событий и предоставляет `CONCRT_EVENT_END` используется в операции.  
  
 Следующий пример показывает, как включить трассировку для вызова `parallel_for`. Среда выполнения не трассирует первый вызов `parallel_for` , так как трассировка не включена. Вызов `EnableTracing` позволяет среде выполнения трассировать второй вызов `parallel_for`.  
  
 [!code-cpp[concrt-etw#1](../../parallel/concrt/codesnippet/cpp/parallel-diagnostic-tools-concurrency-runtime_1.cpp)]  
  
 Среда выполнения отслеживает количество раз, которые можно вызвать `EnableTracing` и `DisableTracing`. Таким образом при вызове метода `EnableTracing` несколько раз, необходимо вызвать метод `DisableTracing` одинаковое количество раз, чтобы отключить трассировку.  
  
## <a name="see-also"></a>См. также  
 [Среда выполнения с параллелизмом](../../parallel/concrt/concurrency-runtime.md)

