---
title: Практическое руководство. Реализация различных шаблонов "источник-приемник"
ms.date: 11/04/2016
helpviewer_keywords:
- producer-consumer patterns, implementing [Concurrency Runtime]
- implementing producer-consumer patterns [Concurrency Runtime]
ms.assetid: 75f2c7cc-5399-49ea-98eb-847fe6747169
ms.openlocfilehash: 70813adf6715a2bcaf4af7370ce43d99c44263bd
ms.sourcegitcommit: 94893973211d0b254c8bcdcf0779997dcc136b0c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/28/2020
ms.locfileid: "91413779"
---
# <a name="how-to-implement-various-producer-consumer-patterns"></a>Практическое руководство. Реализация различных шаблонов "источник-приемник"

В этом разделе описывается реализация шаблона "производитель-получатель" в приложении. В этом шаблоне *производитель* отправляет сообщения в блок сообщений, а *потребитель* считывает сообщения из этого блока.

В этом разделе показано два сценария. В первом сценарии потребитель должен получить каждое сообщение, отправляемое производителем. Во втором сценарии потребитель периодически опрашивает данные и, следовательно, не должен принимать каждое сообщение.

В обоих примерах в этом разделе используются агенты, блоки сообщений и функции передачи сообщений для передачи сообщений от производителя к потребителю. Агент Producer использует функцию [Concurrency:: send](reference/concurrency-namespace-functions.md#send) для записи сообщений в объект [Concurrency:: ITarget](../../parallel/concrt/reference/itarget-class.md) . Агент потребителя использует функцию [Concurrency:: Receive](reference/concurrency-namespace-functions.md#receive) для чтения сообщений из объекта [Concurrency:: ISource](../../parallel/concrt/reference/isource-class.md) . Оба агента содержат значение Sentinel для координации завершения обработки.

Дополнительные сведения об асинхронных агентах см. в разделе [асинхронные агенты](../../parallel/concrt/asynchronous-agents.md). Дополнительные сведения о блоках сообщений и функциях передачи сообщений см. в разделе [асинхронные блоки сообщений](../../parallel/concrt/asynchronous-message-blocks.md) и [функции передачи сообщений](../../parallel/concrt/message-passing-functions.md).

## <a name="example-send-series-of-numbers-to-consumer-agent"></a>Пример: отправка серии номеров агенту потребителя

В этом примере агент-производитель отправляет в агент потребителя ряд чисел. Потребитель получает каждое из этих чисел и вычисляет среднее значение. Приложение записывает среднее значение в консоль.

В этом примере используется объект [Concurrency:: unbounded_buffer](reference/unbounded-buffer-class.md) , позволяющий производителю ставить сообщения в очередь. `unbounded_buffer`Класс реализует интерфейс `ITarget` и `ISource` , чтобы производитель и потребитель могли отправлять и получать сообщения в общий буфер и из него. `send`Функции и `receive` координируют задачу распространения данных от производителя к потребителю.

[!code-cpp[concrt-producer-consumer-average#1](../../parallel/concrt/codesnippet/cpp/how-to-implement-various-producer-consumer-patterns_1.cpp)]

В этом примере формируются следующие данные:

```Output
The average is 50.
```

## <a name="example-send-series-of-stock-quotes-to-consumer-agent"></a>Пример. Отправка ряда котировок акции в агент потребителей

В этом примере агент производителя отправляет в агент потребителя серию котировок акции. Агент получателя периодически считывает текущую квоту и выводит его на консоль.

Этот пример напоминает предыдущий, за исключением того, что он использует объект [Concurrency:: overwrite_buffer](../../parallel/concrt/reference/overwrite-buffer-class.md) , позволяющий производителю совместно использовать одно сообщение с потребителем. Как и в предыдущем примере, `overwrite_buffer` класс реализует интерфейс `ITarget` и `ISource` , чтобы производитель и потребитель могли работать с общим буфером сообщений.

[!code-cpp[concrt-producer-consumer-quotes#1](../../parallel/concrt/codesnippet/cpp/how-to-implement-various-producer-consumer-patterns_2.cpp)]

В этом примере выводится следующий пример выходных данных.

```Output
Current quote is 24.44.
Current quote is 24.44.
Current quote is 24.65.
Current quote is 24.99.
Current quote is 23.76.
Current quote is 22.30.
Current quote is 25.89.
```

В отличие от `unbounded_buffer` объекта, `receive` функция не удаляет сообщение из `overwrite_buffer` объекта. Если потребитель считывает данные из буфера сообщений более одного раза, прежде чем производитель перезапишет это сообщение, получатель получает одно и то же сообщение каждый раз.

## <a name="compiling-the-code"></a>Компиляция кода

Скопируйте пример кода и вставьте его в проект Visual Studio или вставьте в файл с именем, `producer-consumer.cpp` а затем выполните следующую команду в окне командной строки Visual Studio.

**cl.exe/EHsc продуцер-Консумер. cpp**

## <a name="see-also"></a>См. также раздел

[библиотеку асинхронных агентов](../../parallel/concrt/asynchronous-agents-library.md)<br/>
[Асинхронные агенты](../../parallel/concrt/asynchronous-agents.md)<br/>
[Асинхронные блоки сообщений](../../parallel/concrt/asynchronous-message-blocks.md)<br/>
[Функции передачи сообщений](../../parallel/concrt/message-passing-functions.md)
