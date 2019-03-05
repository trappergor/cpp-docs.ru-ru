---
title: Пошаговое руководство. Использование класса join для предотвращения взаимоблокировки
ms.date: 11/19/2018
helpviewer_keywords:
- preventing deadlock with joins [Concurrency Runtime]
- deadlock, preventing [Concurrency Runtime]
- non-greedy joins, example
- join class, example
ms.assetid: d791f697-bb93-463e-84bd-5df1651b7446
ms.openlocfilehash: 2f9e0f50866ed0635fbaa4b700dbf522f09458d9
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/04/2019
ms.locfileid: "57303057"
---
# <a name="walkthrough-using-join-to-prevent-deadlock"></a>Пошаговое руководство. Использование класса join для предотвращения взаимоблокировки

В этом разделе будет примере проблемы обедающих философов показано использование [concurrency::join](../../parallel/concrt/reference/join-class.md) класс для недопущения взаимоблокировок в приложении. В приложении программного обеспечения *взаимоблокировка* возникает, когда два или несколько процессов используют ресурс и одновременно ожидают, пока другой процесс не освободит какой-либо из ресурсов.

Проблема обедающих философов является конкретным примером общего ряда проблем, которые могут возникнуть при набор ресурсов является общим для нескольких параллельных процессов.

## <a name="prerequisites"></a>Предварительные требования

Прежде чем приступать к этому руководству, ознакомьтесь со следующими разделами:

- [Асинхронные агенты](../../parallel/concrt/asynchronous-agents.md)

- [Пошаговое руководство: Создание приложения на основе агента](../../parallel/concrt/walkthrough-creating-an-agent-based-application.md)

- [Асинхронные блоки сообщений](../../parallel/concrt/asynchronous-message-blocks.md)

- [Функции передачи сообщений](../../parallel/concrt/message-passing-functions.md)

- [Структуры данных синхронизации](../../parallel/concrt/synchronization-data-structures.md)

##  <a name="top"></a> Разделы

Это пошаговое руководство содержит следующие разделы:

- [Проблема обедающих философов](#problem)

- [Упрощенная реализация](#deadlock)

- [Использование класса join для предотвращения взаимоблокировки](#solution)

##  <a name="problem"></a> Проблема обедающих философов

Проблема обедающих философов показано, как взаимоблокировка происходит в приложении. В эту проблему пять философов сидят за круглым столом. Каждый философ переключается между мышления и еды. Каждый философ должны совместно использовать палочка с соседом слева, а другой — с соседом справа. Ниже показан этот макет.

![Проблема обедающих философов](../../parallel/concrt/media/dining_philosophersproblem.png "примере проблемы обедающих философов")

Для еды каждому философу нужно две палочки. Если каждый философ содержит только один палочка и ожидает еще один, затем не сможет поесть и все незадействованным.

[[В начало](#top)]

##  <a name="deadlock"></a> Упрощенная реализация

В следующем примере упрощенная реализация проблемы обедающих философов. `philosopher` Класс, который является производным от [concurrency::agent](../../parallel/concrt/reference/agent-class.md), позволяет каждому философу действовать независимо друг от друга. В примере используется общий массив [concurrency::critical_section](../../parallel/concrt/reference/critical-section-class.md) объектов для предоставления каждому `philosopher` объекта монопольный доступ к паре китайских палочек.

Для связи реализации с иллюстрацией `philosopher` класс представляет один философ. `int` Переменная представляет каждый палочка. `critical_section` Объектов служат в качестве владельцев, для которых палочек. `run` Метод имитирует жизненного цикла Карл. `think` Метод имитирует процесс мышления и `eat` метод имитирует процесс еды.

Объект `philosopher` блокирует оба `critical_section` объектов, чтобы смоделировать удаление палочек из держателей до вызывает `eat` метод. После вызова `eat`, `philosopher` объект возвращается палочки держателей, установив `critical_section` объектов обратно в состояние разблокирован.

`pickup_chopsticks` Метод показывает, где может произойти взаимоблокировка. Если каждый `philosopher` объект получает доступ к ее блокировок, после чего нет `philosopher` объекта можно продолжить, так как другая блокировка управляется другим `philosopher` объекта.

## <a name="example"></a>Пример

### <a name="description"></a>Описание

### <a name="code"></a>Код

[!code-cpp[concrt-philosophers-deadlock#1](../../parallel/concrt/codesnippet/cpp/walkthrough-using-join-to-prevent-deadlock_1.cpp)]

## <a name="compiling-the-code"></a>Компиляция кода

Скопируйте код примера и вставьте его в проект Visual Studio или вставьте его в файл с именем `philosophers-deadlock.cpp` и выполните следующую команду в окне командной строки Visual Studio.

**/ EHsc CL.exe philosophers-deadlock.cpp**

[[В начало](#top)]

##  <a name="solution"></a> Использование класса join для предотвращения взаимоблокировки

В этом разделе показано, как использовать буферы сообщений и функции передачи сообщений для снижения вероятности возникновения взаимоблокировки.

Чтобы связать этот пример с предыдущим, `philosopher` класс заменяет каждый `critical_section` объекта с помощью [concurrency::unbounded_buffer](reference/unbounded-buffer-class.md) объекта и `join` объекта. `join` Объект выступает в качестве арбитра, предоставляющего палочки философу.

В этом примере используется `unbounded_buffer` класса, так как когда целевой объект получает сообщение от `unbounded_buffer` объекта, сообщение удаляется из очереди сообщений. Это позволяет `unbounded_buffer` объект, который содержит сообщение, чтобы указать, что палочка доступна. `unbounded_buffer` Объект, содержащий сообщение не указывает, что палочка используется.

В этом примере используется нежадный `join` объекта, поскольку нежадное объединение дает каждого `philosopher` объект доступ к обеих палочек только тогда, когда оба `unbounded_buffer` объекты содержат сообщение. Жадное объединение не могли бы помешать взаимоблокировки, так как жадное объединение принимает сообщения, как только они станут доступными. Взаимоблокировка может произойти, если все жадные `join` объекты получают одно из сообщений, но бесконечное ожидание для других станут доступны.

Дополнительные сведения о жадный и нежадный соединения и различия между разными типами буферов сообщений, см. в разделе [асинхронные блоки сообщений](../../parallel/concrt/asynchronous-message-blocks.md).

#### <a name="to-prevent-deadlock-in-this-example"></a>Для недопущения взаимоблокировок в этом примере

1. Удалите следующий код из примера.

[!code-cpp[concrt-philosophers-deadlock#2](../../parallel/concrt/codesnippet/cpp/walkthrough-using-join-to-prevent-deadlock_2.cpp)]

1. Измените тип `_left` и `_right` данные-члены `philosopher` класс `unbounded_buffer`.

[!code-cpp[concrt-philosophers-join#2](../../parallel/concrt/codesnippet/cpp/walkthrough-using-join-to-prevent-deadlock_3.cpp)]

1. Изменить `philosopher` конструктор, чтобы воспользоваться `unbounded_buffer` объектов в качестве параметров.

[!code-cpp[concrt-philosophers-join#3](../../parallel/concrt/codesnippet/cpp/walkthrough-using-join-to-prevent-deadlock_4.cpp)]

1. Изменить `pickup_chopsticks` метод использовать нежадный `join` объект для получения сообщений из буферов сообщений для обеих палочек.

[!code-cpp[concrt-philosophers-join#4](../../parallel/concrt/codesnippet/cpp/walkthrough-using-join-to-prevent-deadlock_5.cpp)]

1. Изменить `putdown_chopsticks` метод для предоставления доступа к палочки путем отправки сообщения в буферы сообщений для обеих палочек.

[!code-cpp[concrt-philosophers-join#5](../../parallel/concrt/codesnippet/cpp/walkthrough-using-join-to-prevent-deadlock_6.cpp)]

1. Изменить `run` метод для хранения результатов `pickup_chopsticks` метод и передавать эти результаты `putdown_chopsticks` метод.

[!code-cpp[concrt-philosophers-join#6](../../parallel/concrt/codesnippet/cpp/walkthrough-using-join-to-prevent-deadlock_7.cpp)]

1. Измените объявление `chopsticks` переменных в `wmain` функции должен быть массивом из `unbounded_buffer` объектов, что каждый из которых содержит одно сообщение.

[!code-cpp[concrt-philosophers-join#7](../../parallel/concrt/codesnippet/cpp/walkthrough-using-join-to-prevent-deadlock_8.cpp)]

## <a name="example"></a>Пример

### <a name="description"></a>Описание:

Ниже приведен полный пример, использующий нежадном `join` объектов, чтобы исключить риск взаимоблокировки.

### <a name="code"></a>Код

[!code-cpp[concrt-philosophers-join#1](../../parallel/concrt/codesnippet/cpp/walkthrough-using-join-to-prevent-deadlock_9.cpp)]

### <a name="comments"></a>Комментарии

В этом примере формируются следующие данные:

```Output
aristotle ate 50 times.
descartes ate 50 times.
hobbes ate 50 times.
socrates ate 50 times.
plato ate 50 times.
```

## <a name="compiling-the-code"></a>Компиляция кода

Скопируйте код примера и вставьте его в проект Visual Studio или вставьте его в файл с именем `philosophers-join.cpp` и выполните следующую команду в окне командной строки Visual Studio.

**/ EHsc CL.exe philosophers-join.cpp**

[[В начало](#top)]

## <a name="see-also"></a>См. также

[Пошаговые руководства по среде выполнения с параллелизмом](../../parallel/concrt/concurrency-runtime-walkthroughs.md)<br/>
[Библиотека асинхронных агентов](../../parallel/concrt/asynchronous-agents-library.md)<br/>
[Асинхронные агенты](../../parallel/concrt/asynchronous-agents.md)<br/>
[Асинхронные блоки сообщений](../../parallel/concrt/asynchronous-message-blocks.md)<br/>
[Функции передачи сообщений](../../parallel/concrt/message-passing-functions.md)<br/>
[Структуры данных синхронизации](../../parallel/concrt/synchronization-data-structures.md)
