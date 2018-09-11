---
title: Средства диагностики (среда выполнения с параллелизмом) параллельного | Документация Майкрософт
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
ms.openlocfilehash: 6243bd4167ec640553a6cb55d7d6f67319315e19
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/29/2018
ms.locfileid: "43217350"
---
# <a name="parallel-diagnostic-tools-concurrency-runtime"></a>Средства диагностики параллельного выполнения (среда выполнения с параллелизмом)
Visual Studio предоставляет расширенную поддержку отладки и профилирования многопоточных приложений.  
  
## <a name="debugging"></a>Отладка  
 Отладчик Visual Studio включает в себя **Параллельные стеки** окне **параллельных задач** окно, и **контроль параллельных данных** окна. Дополнительные сведения см. в разделе [Пошаговое руководство: отладка параллельного приложения](/visualstudio/debugger/walkthrough-debugging-a-parallel-application) и [как: использовать окно параллельных контрольных значений](/visualstudio/debugger/how-to-use-the-parallel-watch-window).  
  
## <a name="profiling"></a>Профилирование  
 Средства профилирования предоставляют три представления данных, отображающие графическую, табличную и числовую информацию о том, как многопоточное приложение взаимодействует с самим собой и с другими программами. Представления позволяют быстро определить проблемные области и перейти из точек на графических изображениях к стекам вызовов, вызовите сайтов и исходный код. Дополнительные сведения см. в разделе [Визуализатор параллелизма](/visualstudio/profiling/concurrency-visualizer).  
  
## <a name="event-tracing"></a>Трассировка событий  
 Среда выполнения с параллелизмом использует [трассировки событий для Windows](/windows/desktop/ETW/event-tracing-portal) (ETW), чтобы уведомлять средства инструментирования, такие как средства профилирования, при возникновении различных событий. Эти события: при активации или отключении планировщика, контекст начинается, завершается, блокирует, разблокирует или возвращает, или когда параллельный алгоритм начинается или заканчивается.  
  
 Средства, такие как [визуализатор параллелизма](/visualstudio/profiling/concurrency-visualizer) с помощью этой функции; таким образом, вы обычно нет необходимости работать непосредственно с этими событиями. Тем не менее, эти события полезны при разработке пользовательского профилировщика или при использовании средств трассировки событий, таких как [Xperf](http://go.microsoft.com/fwlink/p/?linkid=160628).  
  
 Среда выполнения с параллелизмом создает эти события только в том случае, если трассировка включена. Вызовите [concurrency::EnableTracing](reference/concurrency-namespace-functions.md#enabletracing) функции, чтобы включить трассировку событий и [concurrency::DisableTracing](reference/concurrency-namespace-functions.md#disabletracing) функцию отключения трассировки.  
  
 В следующей таблице описаны события, которые среда выполнения вызывает при включенной трассировке события:  
  
|событие|Описание:|Значение|  
|-----------|-----------------|-----------|  

|[Concurrency::ConcRT_ProviderGuid](reference/concurrency-namespace-constants1.md#concrt_providerguid)| Идентификатор поставщика трассировки событий Windows для среды выполнения с параллелизмом. |`f7b697a3-4db5-4d3b-be71-c4d284e6592f`|  
|[Concurrency::ContextEventGuid](reference/concurrency-namespace-constants1.md#contexteventguid)| Помечает события, относящиеся к контекстам. |`5727a00f-50be-4519-8256-f7699871fecb`|  
|[Concurrency::PPLParallelForEventGuid](reference/concurrency-namespace-constants1.md#pplparallelforeventguid)| Отмечает входы и выходы вызовов [concurrency::parallel_for](reference/concurrency-namespace-functions.md#parallel_for) алгоритма. |`31c8da6b-6165-4042-8b92-949e315f4d84`|  
|[Concurrency::PPLParallelForeachEventGuid](reference/concurrency-namespace-constants1.md#pplparallelforeacheventguid)| Отмечает входы и выходы вызовов [concurrency::parallel_for_each](reference/concurrency-namespace-functions.md#parallel_for_each) алгоритма. |`5cb7d785-9d66-465d-bae1-4611061b5434`|  
|[Concurrency::PPLParallelInvokeEventGuid](reference/concurrency-namespace-constants1.md#pplparallelinvokeeventguid)| Отмечает входы и выходы вызовов [concurrency::parallel_invoke](reference/concurrency-namespace-functions.md#parallel_invoke) алгоритма. |`d1b5b133-ec3d-49f4-98a3-464d1a9e4682`|  
|[Concurrency::SchedulerEventGuid](reference/concurrency-namespace-constants1.md#schedulereventguid)| Помечает события, относящиеся к [планировщик](../../parallel/concrt/task-scheduler-concurrency-runtime.md). |`e2091f8a-1e0a-4731-84a2-0dd57c8a5261`|  
|[Concurrency::VirtualProcessorEventGuid](reference/concurrency-namespace-constants1.md#virtualprocessoreventguid)| Помечает событий, связанных с виртуальными процессорами. |`2f27805f-1676-4ecc-96fa-7eb09d44302f`|  
  
 Среда выполнения с параллелизмом определяет, но не вызывает сейчас, следующие события. Среда выполнения резервирует эти события для использования в будущем:  
  
-   [Concurrency::ConcRTEventGuid](reference/concurrency-namespace-constants1.md#concrteventguid)  
  
-   [Concurrency::ScheduleGroupEventGuid](reference/concurrency-namespace-constants1.md#schedulereventguid)  
  
-   [Concurrency::ChoreEventGuid](reference/concurrency-namespace-constants1.md#choreeventguid)  
  
-   [Concurrency::LockEventGuid](reference/concurrency-namespace-constants1.md#lockeventguid)  
  
-   [Concurrency::ResourceManagerEventGuid](reference/concurrency-namespace-constants1.md#resourcemanagereventguid)  
  
 [Concurrency::ConcRT_EventType](reference/concurrency-namespace-enums.md#concrt_eventtype) перечисление указывает возможные операции, трассируемые событием. Например, при входе `parallel_for` алгоритм, то среда выполнения вызывает `PPLParallelForEventGuid` событий и предоставляет `CONCRT_EVENT_START` операции. Прежде чем `parallel_for` Возвращает алгоритм, то среда выполнения снова вызывает `PPLParallelForEventGuid` событий и предоставляет `CONCRT_EVENT_END` операции.  
  
 В следующем примере показано, как включить трассировку для вызова `parallel_for`. Среда выполнения не трассируется первый вызов `parallel_for` так, как трассировка не включена. Вызов `EnableTracing` позволяет среде выполнения для трассировки второй вызов `parallel_for`.  
  
 [!code-cpp[concrt-etw#1](../../parallel/concrt/codesnippet/cpp/parallel-diagnostic-tools-concurrency-runtime_1.cpp)]  
  
 Среда выполнения отслеживает количество раз, которые можно вызвать `EnableTracing` и `DisableTracing`. Таким образом при вызове метода `EnableTracing` несколько раз, необходимо вызвать `DisableTracing` такое же количество раз, чтобы отключить трассировку.  
  
## <a name="see-also"></a>См. также  
 [Среда выполнения с параллелизмом](../../parallel/concrt/concurrency-runtime.md)

