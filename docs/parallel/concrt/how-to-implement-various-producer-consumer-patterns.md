---
title: Практическое руководство. Реализация различных шаблонов "источник-приемник"
ms.date: 11/04/2016
helpviewer_keywords:
- producer-consumer patterns, implementing [Concurrency Runtime]
- implementing producer-consumer patterns [Concurrency Runtime]
ms.assetid: 75f2c7cc-5399-49ea-98eb-847fe6747169
ms.openlocfilehash: 1c543e2c80ff9edea417fe8c1254bf9aa5aa37fd
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50658293"
---
# <a name="how-to-implement-various-producer-consumer-patterns"></a>Практическое руководство. Реализация различных шаблонов "источник-приемник"

В этом разделе описывается, как для реализации шаблона производитель получатель в приложении. В этом шаблоне *производитель* отправляет сообщения в блок сообщений, а *потребитель* считывает сообщения из этого блока.

В этом разделе показано два сценария. В первом сценарии потребитель должен принять каждое сообщение, которое производитель отправляет. Во втором сценарии потребитель периодически опрашивает для данных и поэтому не нужно принять каждое сообщение.

В обоих примерах в этом разделе используйте агенты, блоки сообщений и функции передачи сообщений для передачи сообщений от производителя к потребителю. Использует агент производителя [concurrency::send](reference/concurrency-namespace-functions.md#send) функцию для записи сообщений в [concurrency::ITarget](../../parallel/concrt/reference/itarget-class.md) объекта. Использует агент потребителя [concurrency::receive](reference/concurrency-namespace-functions.md#receive) функция для чтения сообщений из [concurrency::ISource](../../parallel/concrt/reference/isource-class.md) объекта. Оба агента содержат контрольного значения для координации о завершении обработки.

Дополнительные сведения об асинхронных агентов, см. в разделе [асинхронных агентов](../../parallel/concrt/asynchronous-agents.md). Дополнительные сведения о блоки сообщений и функции передачи сообщений, см. в разделе [асинхронные блоки сообщений](../../parallel/concrt/asynchronous-message-blocks.md) и [функции передачи сообщений](../../parallel/concrt/message-passing-functions.md).

## <a name="example"></a>Пример

В этом примере агент производителя отправляет ряд чисел агент потребителя. Потребитель получает эти числа и вычисляет их среднее значение. Приложение записывает среднее значение в консоль.

В этом примере используется [concurrency::unbounded_buffer](reference/unbounded-buffer-class.md) объект для разрешения для очереди сообщений. `unbounded_buffer` Класс реализует `ITarget` и `ISource` , чтобы потребитель и производитель могут отправлять и получать сообщения из общего буфера. `send` И `receive` координируют задачу передачи данных от производителя к потребителю.

[!code-cpp[concrt-producer-consumer-average#1](../../parallel/concrt/codesnippet/cpp/how-to-implement-various-producer-consumer-patterns_1.cpp)]

В этом примере формируются следующие данные:

```Output
The average is 50.
```

## <a name="example"></a>Пример

В этом примере агент производителя отправляет ряд биржевых котировок агент потребителя. Агент потребителя периодически считывает текущих котировок и выводит его на консоль.

Этот пример похож на предыдущий, за исключением того, что она использует [concurrency::overwrite_buffer](../../parallel/concrt/reference/overwrite-buffer-class.md) для обеспечения совместного использования одного сообщения к получателю. Как показано в предыдущем примере `overwrite_buffer` класс реализует `ITarget` и `ISource` таким образом, чтобы потребитель и производитель могут действовать от буфер общих сообщений.

[!code-cpp[concrt-producer-consumer-quotes#1](../../parallel/concrt/codesnippet/cpp/how-to-implement-various-producer-consumer-patterns_2.cpp)]

В этом примере получается следующий результат.

```Output
Current quote is 24.44.
Current quote is 24.44.
Current quote is 24.65.
Current quote is 24.99.
Current quote is 23.76.
Current quote is 22.30.
Current quote is 25.89.
```

В отличие от с `unbounded_buffer` объекта, `receive` функция не удаляет сообщение из `overwrite_buffer` объекта. Если потребитель считывает данные из буфера сообщений более одного раза, прежде чем производитель перезапишет это сообщение, приемник получает то же сообщение каждый раз.

## <a name="compiling-the-code"></a>Компиляция кода

Скопируйте код примера и вставьте его в проект Visual Studio или вставьте его в файл с именем `producer-consumer.cpp` и выполните следующую команду в окне командной строки Visual Studio.

**производитель/EHsc CL.exe-consumer.cpp**

## <a name="see-also"></a>См. также

[Библиотека асинхронных агентов](../../parallel/concrt/asynchronous-agents-library.md)<br/>
[Асинхронные агенты](../../parallel/concrt/asynchronous-agents.md)<br/>
[Асинхронные блоки сообщений](../../parallel/concrt/asynchronous-message-blocks.md)<br/>
[Функции передачи сообщений](../../parallel/concrt/message-passing-functions.md)
