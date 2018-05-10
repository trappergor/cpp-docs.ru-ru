---
title: Сравнение структур данных синхронизации с интерфейсом Windows API | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- synchronization data structures, compared to Windows API
- event class, example
ms.assetid: 8b0b1a3a-ef80-408c-91fa-93e6af920b4e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 2d1470911b13243a7c8b3befc627801368e89f04
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2018
---
# <a name="comparing-synchronization-data-structures-to-the-windows-api"></a>Сравнение структур данных синхронизации с интерфейсом Windows API
В этом разделе сравнивается поведение структур данных синхронизации, предоставляемые средой выполнения с параллелизмом средой Windows API.  
  
 Структуры данных синхронизации, предоставляемые средой выполнения с параллелизмом *потоковая модель совместной*. В модели совместных потоков примитивы синхронизации явно передают ресурсы для других потоков обработки. Это отличается от *preemptive потоковая модель*, где ресурсы обработки переносятся на другие потоки управления планировщиком или операционной системы.  
  
## <a name="criticalsection"></a>critical_section  
 [Concurrency::critical_section](../../parallel/concrt/reference/critical-section-class.md) похож Windows `CRITICAL_SECTION` структуры, так как он может использоваться только потоками одного процесса. Дополнительные сведения о критических секциях в интерфейсе Windows API см. в разделе [важных объектов раздела](http://msdn.microsoft.com/library/windows/desktop/ms682530).  
  
## <a name="readerwriterlock"></a>reader_writer_lock  
 [Concurrency::reader_writer_lock](../../parallel/concrt/reference/reader-writer-lock-class.md) похож блокировки потоков чтения/записи (SRW) Windows. В следующей таблице описаны сходства и различия.  
  
|Функция|`reader_writer_lock`|Блокировка SRW|  
|-------------|--------------------------|--------------|  
|Повторные|Да|Да|  
|Можно повысить уровень чтения в средство записи (поддержка обновлений)|Нет|Нет|  
|Можно понизить уровень модуль записи для чтения (поддержка понижения уровня)|Нет|Нет|  
|Блокировка предпочтения записи|Да|Нет|  
|Доступ по принципу FIFO для средств записи|Да|Нет|  
  
 Дополнительные сведения о блокировках SRW см. в разделе [тонкий модулей чтения/записи блокировках](http://msdn.microsoft.com/library/windows/desktop/aa904937) в Platform SDK.  
  
## <a name="event"></a>событие  
 [Concurrency::event](../../parallel/concrt/reference/event-class.md) класс напоминает неименованное событие ручного сброса Windows. Однако `event` объекта функционирует параллельно, а событие Windows вытеснения. Дополнительные сведения о событиях Windows см. в разделе [объектов событий](http://msdn.microsoft.com/library/windows/desktop/ms682655).  
  
## <a name="example"></a>Пример  
  
### <a name="description"></a>Описание  
 Чтобы лучше понять разницу между `event` класса и события Windows, рассмотрим следующий пример. В этом примере включается планировщика для создания двух одновременных задач, а затем вызывает две аналогичные функции, использующие `event` класс и событие ручного сброса Windows. Каждая функция сначала создает несколько задач, которые ожидают выполнения общего события в сигнальное. Каждая функция затем выдает выполняемым задачам и сигнализирует событие. Каждая функция ожидает отслеживаемого события.  
  
### <a name="code"></a>Код  
 [!code-cpp[concrt-event-comparison#1](../../parallel/concrt/codesnippet/cpp/comparing-synchronization-data-structures-to-the-windows-api_1.cpp)]  
  
### <a name="comments"></a>Комментарии  
 В этом примере получается следующий результат:  
  
```Output  
Cooperative event:  
    Context 0: waiting on an event.  
    Context 1: waiting on an event.  
    Context 2: waiting on an event.  
    Context 3: waiting on an event.  
    Context 4: waiting on an event.  
    Setting the event.  
    Context 5: received the event.  
    Context 6: received the event.  
    Context 7: received the event.  
    Context 8: received the event.  
    Context 9: received the event.  
Windows event:  
    Context 10: waiting on an event.  
    Context 11: waiting on an event.  
    Setting the event.  
    Context 12: received the event.  
    Context 14: waiting on an event.  
    Context 15: received the event.  
    Context 16: waiting on an event.  
    Context 17: received the event.  
    Context 18: waiting on an event.  
    Context 19: received the event.  
    Context 13: received the event.  
```  
  
 Поскольку `event` класс функционирует параллельно, планировщик может перераспределить ресурсы обработки к другому контексту, если событие ожидает перехода в сигнальное состояние. Таким образом, выполнить дополнительные работу версией, которая использует `event` класса. В версии, использующей события Windows каждая ожидающая задача до запуска следующей задачи необходимо ввести сигнальное состояние.  
  
 Дополнительные сведения о задачах см. в разделе [параллелизм задач](../../parallel/concrt/task-parallelism-concurrency-runtime.md).  
  
## <a name="see-also"></a>См. также  
 [Структуры данных синхронизации](../../parallel/concrt/synchronization-data-structures.md)
