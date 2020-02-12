---
title: Функции передачи сообщений
ms.date: 11/04/2016
helpviewer_keywords:
- message passing functions
ms.assetid: 42477c9e-a8a6-4dc4-a98e-93c6dc8c4dd0
ms.openlocfilehash: 4e1052a59f355c4ad5a7c6b57724268c24a209b4
ms.sourcegitcommit: a8ef52ff4a4944a1a257bdaba1a3331607fb8d0f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/11/2020
ms.locfileid: "77143296"
---
# <a name="message-passing-functions"></a>Функции передачи сообщений

Библиотека асинхронных агентов предоставляет несколько функций, которые позволяют передавать сообщения между компонентами.

Эти функции передачи сообщений используются с различными типами блоков сообщений. Дополнительные сведения о типах блоков сообщений, определяемых среда выполнения с параллелизмом, см. в разделе [асинхронные блоки сообщений](../../parallel/concrt/asynchronous-message-blocks.md).

## <a name="top"></a> Разделы

В этом разделе описаны следующие функции передачи сообщений:

- [Send и asend](#send)

- [получение и try_receive](#receive)

- [Примеры](#examples)

## <a name="send"></a>Send и asend

Функция [Concurrency:: send](reference/concurrency-namespace-functions.md#send) отправляет сообщение указанному целевому объекту синхронно, а функция [Concurrency:: asend](reference/concurrency-namespace-functions.md#asend) отправляет сообщение указанному целевому объекту асинхронно. Функции `send` и `asend` ожидают, пока целевой объект не обозначает, что в конечном итоге будет принимать или отклонять сообщение.

Функция `send` ожидает, пока целевой объект не примет или не отклонит сообщение перед возвратом. Функция `send` возвращает **значение true** , если сообщение было доставлено, и **false** в противном случае. Так как функция `send` работает синхронно, функция `send` ожидает получения сообщения целевым объектом перед возвратом.

И наоборот, функция `asend` не ждет, пока целевой объект не примет или не отклонит сообщение перед возвратом. Вместо этого функция `asend` возвращает **значение true** , если целевой объект принимает сообщение и в конечном итоге получит его. В противном случае `asend` возвращает **значение false** , указывающее, что целевой объект отклонил сообщение или отказался от принятия решения о том, следует ли принимать сообщение.

[[В начало](#top)]

## <a name="receive"></a>получение и try_receive

Функции [Concurrency:: Receive](reference/concurrency-namespace-functions.md#receive) и [concurrency:: try_receive](reference/concurrency-namespace-functions.md#try_receive) считывают данные из заданного источника. Функция `receive` ожидает, пока данные станут доступными, в то время как функция `try_receive` возвращает значение немедленно.

Используйте функцию `receive`, если необходимо, чтобы данные были продолжены. Используйте функцию `try_receive`, если не нужно блокировать текущий контекст или нет необходимости для продолжения работы с данными.

[[В начало](#top)]

## <a name="examples"></a> Примеры

Примеры использования функций `send` и `asend`, а также функции `receive` см. в следующих разделах:

- [Асинхронные блоки сообщений](../../parallel/concrt/asynchronous-message-blocks.md)

- [Практическое руководство. Реализация различных шаблонов "источник-приемник"](../../parallel/concrt/how-to-implement-various-producer-consumer-patterns.md)

- [Практическое руководство. Предоставление рабочих функций классам call и transformer](../../parallel/concrt/how-to-provide-work-functions-to-the-call-and-transformer-classes.md)

- [Практическое руководство. Использование преобразователя в конвейере данных](../../parallel/concrt/how-to-use-transformer-in-a-data-pipeline.md)

- [Практическое руководство. Выбор среди завершенных задач](../../parallel/concrt/how-to-select-among-completed-tasks.md)

- [Практическое руководство. Отправка сообщений через определенные интервалы](../../parallel/concrt/how-to-send-a-message-at-a-regular-interval.md)

- [Практическое руководство. Использование фильтра блоков сообщений](../../parallel/concrt/how-to-use-a-message-block-filter.md)

[[В начало](#top)]

## <a name="see-also"></a>См. также раздел

[Библиотека асинхронных агентов](../../parallel/concrt/asynchronous-agents-library.md)<br/>
[Асинхронные блоки сообщений](../../parallel/concrt/asynchronous-message-blocks.md)<br/>
[Функция send](reference/concurrency-namespace-functions.md#send)<br/>
[Функция asend](reference/concurrency-namespace-functions.md#asend)<br/>
[Функция Receive](reference/concurrency-namespace-functions.md#receive)<br/>
[Функция try_receive](reference/concurrency-namespace-functions.md#try_receive)
