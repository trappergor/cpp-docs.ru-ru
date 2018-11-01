---
title: Функции передачи сообщений
ms.date: 11/04/2016
helpviewer_keywords:
- message passing functions
ms.assetid: 42477c9e-a8a6-4dc4-a98e-93c6dc8c4dd0
ms.openlocfilehash: e258a73723e78090f61230555748e109c28cf01c
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50476028"
---
# <a name="message-passing-functions"></a>Функции передачи сообщений

Библиотека асинхронных агентов предоставляет несколько функций, которые позволяют передавать сообщения между компонентами.

Эти функции передачи сообщений используются с различными типами блоков сообщений. Дополнительные сведения о типах блоков сообщений, определенные средой выполнения с параллелизмом, см. в разделе [асинхронные блоки сообщений](../../parallel/concrt/asynchronous-message-blocks.md).

##  <a name="top"></a> Разделы

В этом разделе описаны следующие функции передачи сообщений.

- [Send и asend](#send)

- [Получение и try_receive](#receive)

- [Примеры](#examples)

##  <a name="send"></a> Send и asend

[Concurrency::send](reference/concurrency-namespace-functions.md#send) функция отправляет сообщение в указанный целевой объект синхронно и [concurrency::asend](reference/concurrency-namespace-functions.md#asend) функция отправляет сообщение в указанный целевой объект асинхронно. Как `send` и `asend` функций Подождите, пока целевой объект указывает, что он будет в конечном счете принять или отклонить сообщение.

`send` Функция ожидает целевой принятия или отклонения сообщения перед возвращением. `send` Возвращает **true** Если сообщение было доставлено и **false** в противном случае. Так как `send` функция работает синхронно, `send` функция ожидает целевой объект для получения сообщения перед возвращением.

И наоборот `asend` функция не ожидает целевой объект, чтобы принять или отклонить сообщение перед возвращением. Вместо этого `asend` возвращает **true** Если целевой объект принимает сообщение и в конечном счете примет его. В противном случае `asend` возвращает **false** чтобы указать, что целевой объект отклонил сообщение или отложить решение о принятии сообщения.

[[В начало](#top)]

##  <a name="receive"></a> Получение и try_receive

[Concurrency::receive](reference/concurrency-namespace-functions.md#receive) и [concurrency::try_receive](reference/concurrency-namespace-functions.md#try_receive) функции считывают данные из источника. `receive` Функция ожидает поступления данных станут доступны, тогда как `try_receive` функция немедленно возвращает.

Используйте `receive` функционировать, когда необходимо иметь данные, чтобы продолжить. Используйте `try_receive` работать, если не следует блокировать текущий контекст или у вас нет данных, чтобы продолжить.

[[В начало](#top)]

##  <a name="examples"></a> Примеры

Примеры использования `send` и `asend`, и `receive` функции, см. в следующих разделах:

- [Асинхронные блоки сообщений](../../parallel/concrt/asynchronous-message-blocks.md)

- [Практическое руководство. Реализация различных шаблонов "источник-приемник"](../../parallel/concrt/how-to-implement-various-producer-consumer-patterns.md)

- [Практическое руководство. Предоставление рабочих функций классам call и transformer](../../parallel/concrt/how-to-provide-work-functions-to-the-call-and-transformer-classes.md)

- [Практическое руководство. Использование преобразователя в конвейере данных](../../parallel/concrt/how-to-use-transformer-in-a-data-pipeline.md)

- [Практическое руководство. Выбор среди завершенных задач](../../parallel/concrt/how-to-select-among-completed-tasks.md)

- [Практическое руководство. Отправка сообщений через определенные интервалы](../../parallel/concrt/how-to-send-a-message-at-a-regular-interval.md)

- [Практическое руководство. Использование фильтра блоков сообщений](../../parallel/concrt/how-to-use-a-message-block-filter.md)

[[В начало](#top)]

## <a name="see-also"></a>См. также

[Библиотека асинхронных агентов](../../parallel/concrt/asynchronous-agents-library.md)<br/>
[Асинхронные блоки сообщений](../../parallel/concrt/asynchronous-message-blocks.md)<br/>
[Функция Send](reference/concurrency-namespace-functions.md#send)<br/>
[Функция asend](reference/concurrency-namespace-functions.md#asend)<br/>
[Функция Receive](reference/concurrency-namespace-functions.md#receive)<br/>
[Функция try_receive](reference/concurrency-namespace-functions.md#try_receive)

