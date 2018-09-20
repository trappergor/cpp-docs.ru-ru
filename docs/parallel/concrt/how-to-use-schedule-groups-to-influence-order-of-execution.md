---
title: 'Практическое: использование групп планирования для определения порядка выполнения | Документация Майкрософт'
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
ms.openlocfilehash: 55417f1d72d6bd3e111a89f4b28f783543101b6e
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46415880"
---
# <a name="how-to-use-schedule-groups-to-influence-order-of-execution"></a>Практическое руководство. Использование групп планирования для определения порядка выполнения

В среде выполнения с параллелизмом порядок, в котором задачи запланированы является недетерминированным. Тем не менее можно использовать политики планирования для определения порядка, в которой запускаются задачи. В этом разделе показано, как использование групп планирования вместе с [concurrency::SchedulingProtocol](reference/concurrency-namespace-enums.md#policyelementkey) политики планировщика для определения порядка, в которой запускаются задачи.

В этом примере запускается набор задач два раза с разными политиками планирования. Обе политики ограничить максимальное количество вычислительных ресурсов до двух. Первый выполнения использует `EnhanceScheduleGroupLocality` политики, который используется по умолчанию, а при втором `EnhanceForwardProgress` политики. В разделе `EnhanceScheduleGroupLocality` политики, планировщик выполняет все задачи в одной группе расписаний пока не завершены или переданы каждой задачи. В разделе `EnhanceForwardProgress` политики, планировщик переходит к следующей группе расписаний по принципу циклического после завершения каждой задачи, или передачи.

При каждой группе расписаний содержит связанные задачи `EnhanceScheduleGroupLocality` политики обычно позволяет повысить производительность, так как расположение кэша сохраняется между задачами. `EnhanceForwardProgress` Политика включает задачи, чтобы продолжать работу и полезно, если необходимо планирование распределение ресурсов между группами расписания.

## <a name="example"></a>Пример

В этом примере определяется `work_yield_agent` класс, который является производным от [concurrency::agent](../../parallel/concrt/reference/agent-class.md). `work_yield_agent` Класс выполняет единицу работы, возвращает текущий контекст и затем выполняет еще одну единицу работы. Агент использует [concurrency::wait](reference/concurrency-namespace-functions.md#wait) функцию для совместной передачи текущего контекста, чтобы обеспечить возможность выполнения других контекстах.

В этом примере создается четыре `work_yield_agent` объектов. Чтобы проиллюстрировать, как настроить политики планировщика для определения порядка, в которой агенты запускаются, в примере производится связывание первых двух агентов с одной группой расписаний и два агента с другой. В примере используется [Concurrency::CurrentScheduler:: createschedulegroup](reference/currentscheduler-class.md#createschedulegroup) метод для создания [concurrency::ScheduleGroup](../../parallel/concrt/reference/schedulegroup-class.md) объектов. В этом примере запускается все четыре агенты два раза, каждый раз с разными политиками планирования.

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

Обе политики создавать такая же последовательность событий. Однако политика, которая использует `EnhanceScheduleGroupLocality` запускает оба агента, которые являются частью первой группы планирования, прежде чем начнется агенты, которые являются частью второй группы. Политика, использующая `EnhanceForwardProgress` запускает один агент из первой группы, затем запускает первый агент во второй группе.

## <a name="compiling-the-code"></a>Компиляция кода

Скопируйте код примера и вставьте его в проект Visual Studio или вставьте его в файл с именем `scheduling-protocol.cpp` и выполните следующую команду в окне командной строки Visual Studio.

**Планирование/EHsc CL.exe-protocol.cpp**

## <a name="see-also"></a>См. также

[Группы планирования](../../parallel/concrt/schedule-groups.md)<br/>
[Асинхронные агенты](../../parallel/concrt/asynchronous-agents.md)

