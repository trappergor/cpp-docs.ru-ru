---
title: Сравнение структур данных синхронизации с интерфейсом Windows API
ms.date: 11/04/2016
helpviewer_keywords:
- synchronization data structures, compared to Windows API
- event class, example
ms.assetid: 8b0b1a3a-ef80-408c-91fa-93e6af920b4e
ms.openlocfilehash: 4fa0d3fbf3457bfafab731275584d206206161dd
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62414039"
---
# <a name="comparing-synchronization-data-structures-to-the-windows-api"></a>Сравнение структур данных синхронизации с интерфейсом Windows API

В этом разделе сравнивается поведение структуры данных синхронизации, предоставляемые средой выполнения с параллелизмом для таких Windows API.

Структуры данных синхронизации, предоставляемые средой выполнения с параллелизмом *потоковая модель совместной*. В модели совместных потоков примитивы синхронизации явно передают ресурсы для других потоков обработки. Это отличается от *preemptive потоковая модель*, в которой ресурсы для обработки передаются другим потокам управления планировщиком или операционной системы.

## <a name="criticalsection"></a>critical_section

[Concurrency::critical_section](../../parallel/concrt/reference/critical-section-class.md) класс похож на Windows `CRITICAL_SECTION` структуры, так как он может использоваться только с потоки одного процесса. Дополнительные сведения о критических секциях в Windows API, см. в разделе [Critical Section Objects](/windows/desktop/Sync/critical-section-objects).

## <a name="readerwriterlock"></a>reader_writer_lock

[Concurrency::reader_writer_lock](../../parallel/concrt/reference/reader-writer-lock-class.md) класс похож на блокировки потоков чтения/записи (SRW) Windows. В следующей таблице описаны сходства и различия.

|Функция|`reader_writer_lock`|Блокировка SRW|
|-------------|--------------------------|--------------|
|Повторные|Да|Да|
|Можно повысить уровень чтения в средство записи (поддержка обновлений)|Нет|Нет|
|Понизить роль модуль записи для модуля чтения (поддержка понижения уровня)|Нет|Нет|
|Блокировка предпочтения записи|Да|Нет|
|Доступ по принципу FIFO для записи|Да|Нет|

Дополнительные сведения о блокировки SRW, см. в разделе [блокировки тонкий потоков чтения/записи (SRW)](https://msdn.microsoft.com/library/windows/desktop/aa904937) в Platform SDK.

## <a name="event"></a>событие

[Concurrency::event](../../parallel/concrt/reference/event-class.md) класс похож на безымянный событие ручного сброса Windows. Тем не менее `event` объект функционирует параллельно, а событие Windows вытеснения. Дополнительные сведения о событиях Windows, см. в разделе [объекты событий](/windows/desktop/Sync/event-objects).

## <a name="example"></a>Пример

### <a name="description"></a>Описание

Чтобы лучше понять разницу между `event` класс и события Windows, рассмотрим следующий пример. В этом примере позволяет создать не более двух одновременных задач, а затем вызывает две аналогичные функции, использующие планировщику `event` класс и событие ручного сброса Windows. Каждая функция сначала создает несколько задач, которые ожидают общего события в сигнальное. Каждая функция затем направляет выполняющихся задач и сигнализирует событие. Каждая функция ожидает отслеживаемого события.

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

Так как `event` совместно поведение класса, планировщик можно перераспределить ресурсы обработки контекста, когда событие ожидает перехода в сигнальное состояние. Таким образом, больше работы достигается путем версии, использующей `event` класса. Версии, которая использует события Windows каждая ожидающая задача нужно ввести в сигнальном состоянии до запуска следующей задачи.

Дополнительные сведения о задачах см. в разделе [параллелизм задач](../../parallel/concrt/task-parallelism-concurrency-runtime.md).

## <a name="see-also"></a>См. также

[Структуры данных синхронизации](../../parallel/concrt/synchronization-data-structures.md)
