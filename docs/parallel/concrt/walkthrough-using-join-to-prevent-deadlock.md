---
title: Пошаговое руководство. Использование класса join для предотвращения взаимоблокировки
ms.date: 04/25/2019
helpviewer_keywords:
- preventing deadlock with joins [Concurrency Runtime]
- deadlock, preventing [Concurrency Runtime]
- non-greedy joins, example
- join class, example
ms.assetid: d791f697-bb93-463e-84bd-5df1651b7446
ms.openlocfilehash: 4df83e944552fd6c0d2482efa72883d87cd45f8c
ms.sourcegitcommit: a8ef52ff4a4944a1a257bdaba1a3331607fb8d0f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/11/2020
ms.locfileid: "77140652"
---
# <a name="walkthrough-using-join-to-prevent-deadlock"></a>Пошаговое руководство. Использование класса join для предотвращения взаимоблокировки

В этом разделе используется Проблема обедающих философов, чтобы продемонстрировать, как использовать класс [Concurrency:: Join](../../parallel/concrt/reference/join-class.md) для предотвращения взаимоблокировок в приложении. В приложении программного обеспечения *взаимоблокировка* возникает, когда два или несколько процессов используют ресурс и одновременно ожидают, пока другой процесс не освободит какой-либо из ресурсов.

Проблема обедающих философов — это конкретный пример общего набора проблем, которые могут возникнуть, когда набор ресурсов совместно используется несколькими параллельными процессами.

## <a name="prerequisites"></a>предварительные требования

Перед началом работы с этим пошаговым руководством ознакомьтесь со следующими разделами:

- [Асинхронные агенты](../../parallel/concrt/asynchronous-agents.md)

- [Пошаговое руководство. Создание приложения на основе агента](../../parallel/concrt/walkthrough-creating-an-agent-based-application.md)

- [Асинхронные блоки сообщений](../../parallel/concrt/asynchronous-message-blocks.md)

- [Функции передачи сообщений](../../parallel/concrt/message-passing-functions.md)

- [Структуры данных синхронизации](../../parallel/concrt/synchronization-data-structures.md)

## <a name="top"></a> Разделы

Это пошаговое руководство содержит следующие разделы:

- [Проблема обедающих философов](#problem)

- [Упрощенная реализация](#deadlock)

- [Использование Join для предотвращения взаимоблокировок](#solution)

## <a name="problem"></a>Проблема обедающих философов

Проблема с философами обеда показывает, как происходит взаимоблокировка в приложении. В этой проблеме пять философов располагаются в круглой таблице. Каждый философ является альтернативным для мышления и съесть. Каждый философ должен поделиться палочкой с соседом слева и другой палочкой, расположенной справа от соседнего. На следующем рисунке показан этот макет.

![Проблема обедающих философов](../../parallel/concrt/media/dining_philosophersproblem.png "Проблема обедающих философов")

Для EAT, философ должен содержать две палочки. Если у каждого философа есть только одна палочка, ожидающая другой, то ни один из философов не может получить и не дожидаться.

[[В начало](#top)]

## <a name="deadlock"></a>Упрощенная реализация

В следующем примере показана упрощенная реализация проблемы обедающих философов. Класс `philosopher`, производный от [Concurrency:: Agent](../../parallel/concrt/reference/agent-class.md), позволяет каждому философу работать независимо. В примере используется общий массив объектов [Concurrency:: critical_section](../../parallel/concrt/reference/critical-section-class.md) , чтобы предоставить каждому `philosopher` объекту эксклюзивный доступ к паре палочк.

Чтобы связать реализацию с иллюстрацией, класс `philosopher` представляет одного философа. Переменная `int` представляет каждую палочку. `critical_section` объекты служат в качестве владельцев, на которых накрываются палочки. Метод `run` имитирует жизнь философа. Метод `think` имитирует процесс мышления, а метод `eat` имитирует действие съесть.

Объект `philosopher` блокирует как `critical_section` объекты, чтобы имитировать удаление палочк из владельцев перед вызовом метода `eat`. После вызова `eat`объект `philosopher` возвращает палочки владельцам, устанавливая объекты `critical_section` обратно в незаблокированное состояние.

Метод `pickup_chopsticks` показывает, где может возникнуть взаимоблокировка. Если каждый объект `philosopher` получает доступ к одной из блокировок, то `philosopher` объект не может продолжить работу, так как другая блокировка управляется другим объектом `philosopher`.

### <a name="example"></a>Пример

[!code-cpp[concrt-philosophers-deadlock#1](../../parallel/concrt/codesnippet/cpp/walkthrough-using-join-to-prevent-deadlock_1.cpp)]

### <a name="compiling-the-code"></a>Компиляция кода

Скопируйте пример кода и вставьте его в проект Visual Studio или вставьте в файл с именем `philosophers-deadlock.cpp`, а затем выполните следующую команду в окне командной строки Visual Studio.

> **CL. exe/EHsc философерс-деадлокк. cpp**

[[В начало](#top)]

## <a name="solution"></a>Использование Join для предотвращения взаимоблокировок

В этом разделе показано, как использовать буферы сообщений и функции передачи сообщений для устранения вероятности взаимоблокировки.

Чтобы связать этот пример с предыдущим, класс `philosopher` заменяет каждый объект `critical_section` с помощью объекта [Concurrency:: unbounded_buffer](reference/unbounded-buffer-class.md) и объекта `join`. Объект `join` выступает в качестве арбитра, предоставляющего палочки философу.

В этом примере используется класс `unbounded_buffer`, так как когда целевой объект получает сообщение от объекта `unbounded_buffer`, сообщение удаляется из очереди сообщений. Это позволяет объекту `unbounded_buffer`, содержащему сообщение, чтобы указать, что палочка доступна. Объект `unbounded_buffer`, не содержащий ни одного сообщения, указывает, что используется палочка.

В этом примере используется нежадный `join` объект, так как нежадное соединение дает каждому `philosopher` объекту доступ к обеим палочкам только в том случае, если оба объекта `unbounded_buffer` содержат сообщение. Жадное соединение не помешает взаимоблокировке, так как жадное соединение принимает сообщения, как только они становятся доступными. Взаимоблокировка может быть вызвана тем, что все жадные `join` объекты получают одно из сообщений, но ожидают бесконечное ожидание, чтобы оно стало доступным.

Дополнительные сведения о жадных и нежадных объединениях, а также различиях между различными типами буферов сообщений см. в разделе [асинхронные блоки сообщений](../../parallel/concrt/asynchronous-message-blocks.md).

### <a name="to-prevent-deadlock-in-this-example"></a>Предотвращение взаимоблокировок в этом примере

1. Удалите из примера следующий код.

[!code-cpp[concrt-philosophers-deadlock#2](../../parallel/concrt/codesnippet/cpp/walkthrough-using-join-to-prevent-deadlock_2.cpp)]

1. Измените тип `_left` и `_right` элементов данных класса `philosopher` в `unbounded_buffer`.

[!code-cpp[concrt-philosophers-join#2](../../parallel/concrt/codesnippet/cpp/walkthrough-using-join-to-prevent-deadlock_3.cpp)]

1. Измените конструктор `philosopher`, чтобы в качестве параметров были `unbounded_buffer` объекты.

[!code-cpp[concrt-philosophers-join#3](../../parallel/concrt/codesnippet/cpp/walkthrough-using-join-to-prevent-deadlock_4.cpp)]

1. Измените метод `pickup_chopsticks`, чтобы использовать нежадный `join` объект для получения сообщений из буферов сообщений для обеих палочк.

[!code-cpp[concrt-philosophers-join#4](../../parallel/concrt/codesnippet/cpp/walkthrough-using-join-to-prevent-deadlock_5.cpp)]

1. Измените метод `putdown_chopsticks`, чтобы освободить доступ к палочкам, отправив сообщение в буферы сообщений для обеих палочк.

[!code-cpp[concrt-philosophers-join#5](../../parallel/concrt/codesnippet/cpp/walkthrough-using-join-to-prevent-deadlock_6.cpp)]

1. Измените метод `run` для хранения результатов метода `pickup_chopsticks` и передачи этих результатов методу `putdown_chopsticks`.

[!code-cpp[concrt-philosophers-join#6](../../parallel/concrt/codesnippet/cpp/walkthrough-using-join-to-prevent-deadlock_7.cpp)]

1. Измените объявление переменной `chopsticks` в функции `wmain`, чтобы она была массивом объектов `unbounded_buffer`, содержащих одно сообщение.

[!code-cpp[concrt-philosophers-join#7](../../parallel/concrt/codesnippet/cpp/walkthrough-using-join-to-prevent-deadlock_8.cpp)]

### <a name="description"></a>Description

Ниже показан готовый пример, использующий нежадные `join` объекты для устранения риска взаимоблокировки.

### <a name="example"></a>Пример

[!code-cpp[concrt-philosophers-join#1](../../parallel/concrt/codesnippet/cpp/walkthrough-using-join-to-prevent-deadlock_9.cpp)]

В этом примере формируются следующие данные:

```Output
aristotle ate 50 times.
descartes ate 50 times.
hobbes ate 50 times.
socrates ate 50 times.
plato ate 50 times.
```

### <a name="compiling-the-code"></a>Компиляция кода

Скопируйте пример кода и вставьте его в проект Visual Studio или вставьте в файл с именем `philosophers-join.cpp`, а затем выполните следующую команду в окне командной строки Visual Studio.

> **CL. exe/EHsc философерс-Жоин. cpp**

[[В начало](#top)]

## <a name="see-also"></a>См. также раздел

[Пошаговые руководства по среде выполнения с параллелизмом](../../parallel/concrt/concurrency-runtime-walkthroughs.md)<br/>
[Библиотека асинхронных агентов](../../parallel/concrt/asynchronous-agents-library.md)<br/>
[Асинхронные агенты](../../parallel/concrt/asynchronous-agents.md)<br/>
[Асинхронные блоки сообщений](../../parallel/concrt/asynchronous-message-blocks.md)<br/>
[Функции передачи сообщений](../../parallel/concrt/message-passing-functions.md)<br/>
[Структуры данных синхронизации](../../parallel/concrt/synchronization-data-structures.md)
