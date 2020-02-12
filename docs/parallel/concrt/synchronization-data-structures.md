---
title: Структуры данных синхронизации
ms.date: 11/04/2016
helpviewer_keywords:
- synchronization data structures
ms.assetid: d612757d-e4b7-4019-a627-f853af085b8b
ms.openlocfilehash: 85dec6b003330a3560ae1dcc5c41b5e6d49f765e
ms.sourcegitcommit: a8ef52ff4a4944a1a257bdaba1a3331607fb8d0f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/11/2020
ms.locfileid: "77142796"
---
# <a name="synchronization-data-structures"></a>Структуры данных синхронизации

Среда выполнения с параллелизмом предоставляет несколько структур данных, которые позволяют синхронизировать доступ к общим данным из нескольких потоков. Эти структуры данных полезны при нечастом изменении общих данных. Объект синхронизации, например критический раздел, заставляет другие потоки ожидать, пока общий ресурс не станет доступным. Таким образом, если вы используете такой объект для синхронизации доступа к часто используемым данным, можно потерять масштабируемость в приложении. [Библиотека Parallel Patterns (PPL)](../../parallel/concrt/parallel-patterns-library-ppl.md) предоставляет класс [Concurrency:: combinable](../../parallel/concrt/reference/combinable-class.md) , который позволяет совместно использовать ресурс в нескольких потоках или задачах без необходимости синхронизации. Дополнительные сведения о классе `combinable` см. в разделе [Parallel Containers and Objects](../../parallel/concrt/parallel-containers-and-objects.md).

## <a name="top"></a> Разделы

В этом разделе подробно описаны следующие типы асинхронных блоков сообщений:

- [critical_section](#critical_section)

- [reader_writer_lock](#reader_writer_lock)

- [scoped_lock и scoped_lock_read](#scoped_lock)

- [event](#event)

## <a name="critical_section"></a>critical_section

Класс [Concurrency:: critical_section](../../parallel/concrt/reference/critical-section-class.md) представляет объект совместного взаимного исключения, который передает другие задачи вместо того, чтобы прерывать их. Критические разделы полезны, когда нескольким потокам требуется эксклюзивный доступ на чтение и запись к общим данным.

Класс `critical_section` не может быть недопустимым. Метод [Concurrency:: critical_section:: Lock](reference/critical-section-class.md#lock) вызывает исключение типа [concurrency:: improper_lock](../../parallel/concrt/reference/improper-lock-class.md) , если оно вызывается потоком, который уже владеет блокировкой.

### <a name="methods-and-features"></a>Методы и функции

В следующей таблице показаны важные методы, определяемые классом `critical_section`.

|Метод|Description|
|------------|-----------------|
|[lock](reference/critical-section-class.md#lock)|Получает критическую секцию. Контекст вызова блокируется до получения блокировки.|
|[try_lock](reference/critical-section-class.md#try_lock)|Пытается получить критическую секцию, но не блокируется.|
|[unlock](reference/critical-section-class.md#unlock)|Освобождает критическую секцию.|

[[В начало](#top)]

## <a name="reader_writer_lock"></a>reader_writer_lock

Класс [Concurrency:: reader_writer_lock](../../parallel/concrt/reference/reader-writer-lock-class.md) предоставляет потокобезопасные операции чтения и записи для общих данных. Используйте блокировки потоков чтения/записи, когда нескольким потокам требуется одновременный доступ на чтение к общему ресурсу, но редко осуществляется запись в этот общий ресурс. Этот класс предоставляет только одному потоку доступ на запись к объекту в любое время.

Класс `reader_writer_lock` может работать лучше, чем класс `critical_section`, так как объект `critical_section` получает монопольный доступ к общему ресурсу, что предотвращает одновременный доступ на чтение.

Как и класс `critical_section`, класс `reader_writer_lock` представляет собой объект совместного взаимного исключения, который передает другие задачи вместо того, чтобы прерывать их.

Когда поток, который должен выполнить запись в общий ресурс, получает блокировку потоков чтения/записи, другие потоки, которые также должны обращаться к ресурсу, блокируются до тех пор, пока модуль записи не освободит блокировку. Класс `reader_writer_lock` является примером блокировки *записи* , которая является блокировкой, которая разблокирует ожидающие модули записи перед разблокированием ожидающих потоков чтения.

Как и класс `critical_section`, класс `reader_writer_lock` не допускает повторного входа. Методы [Concurrency:: reader_writer_lock:: Lock](reference/reader-writer-lock-class.md#lock) и [concurrency:: reader_writer_lock:: lock_read](reference/reader-writer-lock-class.md#lock_read) создают исключение типа `improper_lock`, если они вызываются потоком, который уже владеет блокировкой.

> [!NOTE]
> Поскольку класс `reader_writer_lock` не является недопустимым, вы не можете обновить блокировку только для чтения до блокировки потоков чтения/записи или понизить блокировку чтения/записи до блокировки только для чтения. Выполнение любой из этих операций приводит к неопределенному поведению.

### <a name="methods-and-features"></a>Методы и функции

В следующей таблице показаны важные методы, определяемые классом `reader_writer_lock`.

|Метод|Description|
|------------|-----------------|
|[lock](reference/reader-writer-lock-class.md#lock)|Получает доступ на чтение и запись к блокировке.|
|[try_lock](reference/reader-writer-lock-class.md#try_lock)|Пытается получить доступ на чтение и запись к блокировке, но не блокируется.|
|[lock_read](reference/reader-writer-lock-class.md#lock_read)|Получает доступ к блокировке только для чтения.|
|[try_lock_read](reference/reader-writer-lock-class.md#try_lock_read)|Пытается получить доступ к блокировке только для чтения, но не блокируется.|
|[unlock](reference/reader-writer-lock-class.md#unlock)|Снимает блокировку.|

[[В начало](#top)]

## <a name="scoped_lock"></a>scoped_lock и scoped_lock_read

Классы `critical_section` и `reader_writer_lock` предоставляют вложенные вспомогательные классы, которые упрощают работу с взаимоисключающими объектами. Эти вспомогательные классы известны как *блокировки с областью действия*.

Класс `critical_section` содержит класс [Concurrency:: critical_section:: scoped_lock](reference/critical-section-class.md#critical_section__scoped_lock_class) . Конструктор получает доступ к предоставленному объекту `critical_section`; Деструктор освобождает доступ к этому объекту. Класс `reader_writer_lock` содержит класс [Concurrency:: reader_writer_lock:: scoped_lock](reference/reader-writer-lock-class.md#scoped_lock_class) , который напоминает `critical_section::scoped_lock`, за исключением того, что он управляет доступом на запись к предоставленному объекту `reader_writer_lock`. Класс `reader_writer_lock` также содержит класс [Concurrency:: reader_writer_lock:: scoped_lock_read](reference/reader-writer-lock-class.md#scoped_lock_read_class) . Этот класс управляет доступом на чтение к предоставленному объекту `reader_writer_lock`.

Блокировки с заданной областью предоставляют несколько преимуществ при работе с `critical_section` и `reader_writer_lock` объектами вручную. Как правило, в стеке выделяется блокировка с заданной областью. Блокировка с заданной областью освобождает доступ к объекту взаимного исключения автоматически при его уничтожении. Таким образом, базовый объект не разблокируется вручную. Это полезно, если функция содержит несколько `return` инструкций. Блокировки с заданной областью также могут помочь при написании кода, безопасного с помощью исключений. Если инструкция `throw` вызывает очистку стека, вызывается деструктор любой блокировки активной области, и поэтому объект взаимоисключения всегда освобождается правильно.

> [!NOTE]
> При использовании классов `critical_section::scoped_lock`, `reader_writer_lock::scoped_lock`и `reader_writer_lock::scoped_lock_read` не следует вручную освобождать доступ к базовому взаимоисключающему объекту. В результате среда выполнения может находиться в недопустимом состоянии.

## <a name="event"></a>журнале

Класс [Concurrency:: Event](../../parallel/concrt/reference/event-class.md) представляет объект синхронизации, состояние которого может быть сигнальным или несигнальным. В отличие от объектов синхронизации, таких как критические разделы, цель которых заключается в защите доступа к общим данным, события синхронизируют поток выполнения.

Класс `event` полезен, когда одна задача завершила работу для другой задачи. Например, одна задача может сообщить другой задаче о том, что она читает данные из сетевого подключения или из файла.

### <a name="methods-and-features"></a>Методы и функции

В следующей таблице показаны некоторые важные методы, определяемые классом `event`.

|Метод|Description|
|------------|-----------------|
|[ожидания](reference/event-class.md#wait)|Ожидает сигнала события.|
|[set](reference/event-class.md#set)|Устанавливает событие в сигнальное состояние.|
|[reset](reference/event-class.md#reset)|Устанавливает событие в несигнальное состояние.|
|[wait_for_multiple](reference/event-class.md#wait_for_multiple)|Ожидает получения сигнала для нескольких событий.|

### <a name="example"></a>Пример

Пример, демонстрирующий использование класса `event`, см. в разделе [Сравнение структур данных синхронизации с API Windows](../../parallel/concrt/comparing-synchronization-data-structures-to-the-windows-api.md).

[[В начало](#top)]

## <a name="related-sections"></a>См. также

[Сравнение структур данных синхронизации с интерфейсом Windows API](../../parallel/concrt/comparing-synchronization-data-structures-to-the-windows-api.md)<br/>
Сравнивает поведение структур данных синхронизации с теми, которые предоставляются API-интерфейсом Windows.

[Среда выполнения с параллелизмом](../../parallel/concrt/concurrency-runtime.md)<br/>
Описывает среду выполнения с параллелизмом, которая упрощает процесс параллельного программирования и содержит ссылки на соответствующие разделы.
