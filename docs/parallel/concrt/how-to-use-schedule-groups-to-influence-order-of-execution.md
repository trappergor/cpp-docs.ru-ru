---
title: 'Как: использование групп планирования для определения порядка выполнения | Документы Microsoft'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- schedule groups, using [Concurrency Runtime]
- using schedule groups [Concurrency Runtime]
ms.assetid: 73124194-fc3a-491e-a23f-fbd7b5a4455c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c41617f562a0abefdecf74d52e7a886ad6326f9e
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2018
---
# <a name="how-to-use-schedule-groups-to-influence-order-of-execution"></a>Практическое руководство. Использование групп планирования для определения порядка выполнения
В среде выполнения с параллелизмом порядок, в котором запланированные задачи является недетерминированным. Тем не менее можно использовать политики планирования для определения порядка, в которой запускаются задачи. В этом разделе демонстрируется использование групп расписаний вместе с [concurrency::SchedulingProtocol](reference/concurrency-namespace-enums.md#policyelementkey) политики планировщика для определения порядка, в которой запускаются задачи.  

  
 В этом примере запускается с разными политиками планирования набор задач, два раза. Обе политики ограничивают максимальное число ресурсов обработки двумя. Первом выполнении используется `EnhanceScheduleGroupLocality` политики, используемого по умолчанию, а при втором `EnhanceForwardProgress` политики. В разделе `EnhanceScheduleGroupLocality` политики, планировщик выполняет все задачи в одной группе расписаний до завершения или переданы все задачи. В разделе `EnhanceForwardProgress` политики, планировщик переходит к следующей группе расписаний в циклического перебора после завершения каждой задачи, или передачи.  
  
 Если каждая группа расписаний содержит связанные задачи `EnhanceScheduleGroupLocality` политики обычно позволяет повысить производительность, так как расположение кэша сохраняется между задачами. `EnhanceForwardProgress` Политика позволяет задачам продвигаться вперед и полезно, если необходимо равноправное планирование в разных группах расписаний.  
  
## <a name="example"></a>Пример  
 В этом примере определяется `work_yield_agent` класс, который является производным от [concurrency::agent](../../parallel/concrt/reference/agent-class.md). `work_yield_agent` Класс выполняет блок работы, возвращает текущий контекст, а затем выполняет еще один блок работы. Агент использует [concurrency::wait](reference/concurrency-namespace-functions.md#wait) функции для совместной передачи текущего контекста, чтобы обеспечить возможность выполнения других контекстов.  
  
 В этом примере создаются четыре `work_yield_agent` объектов. Чтобы показать, как задавать политики планировщика для определения порядка, в которой агенты запускаются, в примере производится связывание первых двух агентов с одной группой расписаний и два агента с другой. В этом примере [Concurrency::CurrentScheduler:: createschedulegroup](reference/currentscheduler-class.md#createschedulegroup) метод для создания [concurrency::ScheduleGroup](../../parallel/concrt/reference/schedulegroup-class.md) объектов. В примере запускаются все четыре агента два раза, каждый раз с разными политиками планирования.  
  
 [!code-cpp[concrt-scheduling-protocol#1](../../parallel/concrt/codesnippet/cpp/how-to-use-schedule-groups-to-influence-order-of-execution_1.cpp)]  
  
 В этом примере формируются следующие данные:  
  
```Output  
Using EnhanceScheduleGroupLocality...  
group 0,
    task 0: first loop...  
group 0,
    task 1: first loop...  
group 0,
    task 0: waiting...  
group 1,
    task 0: first loop...  
group 0,
    task 1: waiting...  
group 1,
    task 1: first loop...  
group 1,
    task 0: waiting...  
group 0,
    task 0: second loop...  
group 1,
    task 1: waiting...  
group 0,
    task 1: second loop...  
group 0,
    task 0: finished...  
group 1,
    task 0: second loop...  
group 0,
    task 1: finished...  
group 1,
    task 1: second loop...  
group 1,
    task 0: finished...  
group 1,
    task 1: finished...  
 
Using EnhanceForwardProgress...  
group 0,
    task 0: first loop...  
group 1,
    task 0: first loop...  
group 0,
    task 0: waiting...  
group 0,
    task 1: first loop...  
group 1,
    task 0: waiting...  
group 1,
    task 1: first loop...  
group 0,
    task 1: waiting...  
group 0,
    task 0: second loop...  
group 1,
    task 1: waiting...  
group 1,
    task 0: second loop...  
group 0,
    task 0: finished...  
group 0,
    task 1: second loop...  
group 1,
    task 0: finished...  
group 1,
    task 1: second loop...  
group 0,
    task 1: finished...  
group 1,
    task 1: finished...  
```  
  
 Обе политики создают одну и ту же последовательность событий. Однако политика, которая использует `EnhanceScheduleGroupLocality` запускает оба агента первой группы планирования перед началом агенты, которые являются частью второй группы. Политика, использующая `EnhanceForwardProgress` запускает один агент из первой группы, затем запускает первый агент во второй группе.  
  
## <a name="compiling-the-code"></a>Компиляция кода  
 Скопируйте код примера и вставьте его в проект Visual Studio или вставить его в файл с именем `scheduling-protocol.cpp` , а затем запустите следующую команду в окне командной строки Visual Studio.  
  
 **Планирование CL.exe/EHsc-protocol.cpp**  
  
## <a name="see-also"></a>См. также  
 [Группы расписаний](../../parallel/concrt/schedule-groups.md)   
 [Асинхронные агенты](../../parallel/concrt/asynchronous-agents.md)

