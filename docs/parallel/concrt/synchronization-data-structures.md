---
title: Структуры данных синхронизации
ms.date: 11/04/2016
helpviewer_keywords:
- synchronization data structures
ms.assetid: d612757d-e4b7-4019-a627-f853af085b8b
ms.openlocfilehash: 8c91de87bb5d579916743051d06c15f6df6921bf
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50495931"
---
# <a name="synchronization-data-structures"></a>Структуры данных синхронизации

Среда выполнения с параллелизмом предоставляет несколько структур данных, которые позволяют синхронизировать доступ к общим данным из нескольких потоков. Эти структуры данных полезны в тех случаях, когда общей редко изменяемых данных. Объект синхронизации, например, критическую секцию, приводит к ждать освобождения общий ресурс других потоков. Таким образом Если такой объект используется для синхронизации доступа к данным, которые часто используются, вы можете потерять масштабируемости в приложении. [Библиотеки параллельных шаблонов (PPL)](../../parallel/concrt/parallel-patterns-library-ppl.md) предоставляет [concurrency::combinable](../../parallel/concrt/reference/combinable-class.md) класс, который дает возможность совместного использования ресурсов среди нескольких потоков или задач без необходимости синхронизации. Дополнительные сведения о `combinable` , представлена в разделе [параллельные контейнеры и объекты](../../parallel/concrt/parallel-containers-and-objects.md).

##  <a name="top"></a> Разделы

В этом разделе описываются следующие типы блока асинхронное сообщение подробно:

- [critical_section](#critical_section)

- [reader_writer_lock](#reader_writer_lock)

- [scoped_lock и scoped_lock_read](#scoped_lock)

- [event](#event)

##  <a name="critical_section"></a> critical_section

[Concurrency::critical_section](../../parallel/concrt/reference/critical-section-class.md) класс представляет объект совместного взаимного исключения, который уступает другим задачам, а не вытесняет их. Критические разделы полезны в тех случаях, когда несколько потоков требуется монопольный доступ чтение и запись к общим данным.

`critical_section` Класс допускает повторные входы. [Concurrency::critical_section:: lock](reference/critical-section-class.md#lock) метод вызывает исключение типа [concurrency::improper_lock](../../parallel/concrt/reference/improper-lock-class.md) при вызове потоком, который уже является владельцем блокировки.

### <a name="methods-and-features"></a>Методы и функции

В следующей таблице показаны важные методы, которые определяются `critical_section` класса.

|Метод|Описание|
|------------|-----------------|
|[lock](reference/critical-section-class.md#lock)|Получает критическую секцию. Вызывающий контекст блокируется, пока не получит блокировку.|
|[try_lock](reference/critical-section-class.md#try_lock)|Пытается получить критический раздел, но не приводит к блокировке.|
|[unlock](reference/critical-section-class.md#unlock)|Освобождает критический раздел.|

[[В начало](#top)]

##  <a name="reader_writer_lock"></a> reader_writer_lock

[Concurrency::reader_writer_lock](../../parallel/concrt/reference/reader-writer-lock-class.md) класс предоставляет операции с потоками чтения и записи к общим данным. Используйте блокировки потоков чтения/записи, когда несколько потоков, требуют параллельный доступ для чтения к общему ресурсу, но редко писать для этого общего ресурса. Этот класс предоставляет доступ на запись только один поток на объект в любое время.

`reader_writer_lock` Класс может выполнять лучше, чем `critical_section` класса, так как `critical_section` получает эксклюзивный доступ к общему ресурсу, который не позволяет одновременный доступ для чтения.

Как и `critical_section` класса `reader_writer_lock` представляет объект совместного взаимного исключения, который уступает другим задачам, а не вытесняет их.

Когда поток, который необходимо написать в общий ресурс получает блокировку потоков чтения/записи, другие потоки, которые также необходимо получить доступ к ресурсу заблокированных до записи снимает блокировку. `reader_writer_lock` Класс является примером *предпочтения записи* блокировки, которая имеет разблокирует потоки, ожидающие записи, прежде чем он разблокирует ожидающим потокам чтения.

Как и `critical_section` класса `reader_writer_lock` класс допускает повторные входы. [Concurrency::reader_writer_lock:: lock](reference/reader-writer-lock-class.md#lock) и [Concurrency::reader_writer_lock:: lock_read](reference/reader-writer-lock-class.md#lock_read) методы создают исключение типа `improper_lock` если они вызываются потоком, который уже является владельцем блокировка.

> [!NOTE]
>  Так как `reader_writer_lock` класс допускает повторные входы, невозможно повысить уровень блокировки только для чтения до блокировки потоков чтения/записи или понизить уровень блокировки потоков чтения/записи к блокировке только для чтения. Выполнение этих операций приводит к непредсказуемому поведению.

### <a name="methods-and-features"></a>Методы и функции

В следующей таблице показаны важные методы, которые определяются `reader_writer_lock` класса.

|Метод|Описание|
|------------|-----------------|
|[lock](reference/reader-writer-lock-class.md#lock)|Получает доступ на чтение и запись к блокировке.|
|[try_lock](reference/reader-writer-lock-class.md#try_lock)|Пытается получить доступ на чтение и запись к блокировке, но не приводит к блокировке.|
|[lock_read](reference/reader-writer-lock-class.md#lock_read)|Получает доступ только для чтения к блокировке.|
|[try_lock_read](reference/reader-writer-lock-class.md#try_lock_read)|Пытается получить доступ только для чтения к блокировке, но не приводит к блокировке.|
|[unlock](reference/reader-writer-lock-class.md#unlock)|Снимает блокировку.|

[[В начало](#top)]

##  <a name="scoped_lock"></a> scoped_lock и scoped_lock_read

`critical_section` И `reader_writer_lock` классы предоставляют вложенные вспомогательные классы, упрощающие способ работы с объектами взаимное исключение. Эти вспомогательные классы называются *блокировками с областью*.

`critical_section` Класс содержит [Concurrency::critical_section:: scoped_lock](reference/critical-section-class.md#critical_section__scoped_lock_class) класса. Конструктор получает доступ к заданной `critical_section` объекта; деструктор выпуски доступ к этому объекту. `reader_writer_lock` Класс содержит [Concurrency::reader_writer_lock:: scoped_lock](reference/reader-writer-lock-class.md#scoped_lock_class) класс, который напоминает `critical_section::scoped_lock`, за исключением того, что он управляет доступ на запись к предоставленному `reader_writer_lock` объекта. `reader_writer_lock` Класс также содержит [Concurrency::reader_writer_lock:: scoped_lock_read](reference/reader-writer-lock-class.md#scoped_lock_read_class) класса. Этот класс управляет доступом на чтение к предоставленному `reader_writer_lock` объекта.

Блокировки с областью имеют несколько преимуществ при работе с `critical_section` и `reader_writer_lock` объектов вручную. Как правило можно выделить блокировка с областью в стеке. Блокировка с областью высвобождает доступ к своему объекту взаимного исключения автоматически при уничтожении; Таким образом вам не требуется разблокировать вручную базовый объект. Это полезно, если функция содержит несколько `return` инструкций. Блокировки с областью также помогает писать безопасный в отношении исключений код. Когда `throw` инструкция вызывает стека вызова деструктора для всех активных блокировок с областью, и поэтому всегда правильно освобождается объект взаимного исключения.

> [!NOTE]
>  При использовании `critical_section::scoped_lock`, `reader_writer_lock::scoped_lock`, и `reader_writer_lock::scoped_lock_read` классы, вручную не освободить доступ к базовому объекту взаимного исключения. Среда выполнения может перейти в недопустимом состоянии.

##  <a name="event"></a> Событие

[Concurrency::event](../../parallel/concrt/reference/event-class.md) класс представляет объект синхронизации, состояние которого может выполняться или отсутствия сигнала. В отличие от объектов синхронизации, таких как критические секции, цель которого — защита доступа к общим данным, события синхронизации хода выполнения.

`event` Класс может быть полезен, когда одна задача завершила работу для другой задачи. Например одна задача может сигнализировать другой задаче о завершении чтения данных из сетевого подключения или из файла.

### <a name="methods-and-features"></a>Методы и функции

В следующей таблице показаны несколько важных методов, определяемых `event` класса.

|Метод|Описание|
|------------|-----------------|
|[wait](reference/event-class.md#wait)|Ожидает события в сигнальное.|
|[set](reference/event-class.md#set)|Задает события в сигнальное состояние.|
|[reset](reference/event-class.md#reset)|Задает несигнальное состояние события.|
|[wait_for_multiple](reference/event-class.md#wait_for_multiple)|Ожидает в течение нескольких события в сигнальное.|

### <a name="example"></a>Пример

Пример, показывающий, как использовать `event` , представлена в разделе [Сравнение структур данных синхронизации с Windows API](../../parallel/concrt/comparing-synchronization-data-structures-to-the-windows-api.md).

[[В начало](#top)]

## <a name="related-sections"></a>Связанные разделы

[Сравнение структур данных синхронизации с интерфейсом Windows API](../../parallel/concrt/comparing-synchronization-data-structures-to-the-windows-api.md)<br/>
Сравнивается поведение структур данных синхронизации с образы, предоставляемые Windows API.

[Среда выполнения с параллелизмом](../../parallel/concrt/concurrency-runtime.md)<br/>
Описывает среду выполнения с параллелизмом, которая упрощает процесс параллельного программирования и содержит ссылки на соответствующие разделы.

