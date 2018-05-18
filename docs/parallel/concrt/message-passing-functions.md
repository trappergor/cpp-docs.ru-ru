---
title: Функции передачи сообщений | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- message passing functions
ms.assetid: 42477c9e-a8a6-4dc4-a98e-93c6dc8c4dd0
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 9eecb7d2a45079ff14740167a192eafaab268150
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2018
---
# <a name="message-passing-functions"></a>Функции передачи сообщений
Библиотека асинхронных агентов предоставляет несколько функций, которые позволяют передавать сообщения между компонентами.  
  
 Эти функции передачи сообщений используются с различными типами блоков сообщений. Дополнительные сведения о типах блоков сообщений, которые определены в среде выполнения с параллелизмом см. в разделе [асинхронные блоки сообщений](../../parallel/concrt/asynchronous-message-blocks.md).  
  
##  <a name="top"></a> Разделы  
 В этом разделе описываются следующие функции передачи сообщений.  
  
-   [Send и asend](#send)  
  
-   [Получение и try_receive](#receive)  
  
-   [Примеры](#examples)  
  
##  <a name="send"></a> Send и asend  

 [Concurrency::send](reference/concurrency-namespace-functions.md#send) функция отправляет сообщение заданному целевому объекту синхронно и [concurrency::asend](reference/concurrency-namespace-functions.md#asend) функция отправляет сообщение заданному целевому объекту асинхронно. Как `send` и `asend` функции подождать, пока целевой объект укажет, что он будет в конечном счете принять или отклонить сообщение.  
  
 `send` Функция ожидает, пока целевой объект принимает или отклоняет сообщение, прежде чем вернуть. `send` Возврата функцией `true` Если сообщение было доставлено и `false` в противном случае. Поскольку `send` функция работает синхронно, `send` функция ожидает целевой объект для получения сообщения, прежде чем вернуть.  
  
 И наоборот `asend` функция не ожидает целевой объект, чтобы принять или отклонить сообщение перед возвратом. Вместо этого `asend` возврата функцией `true` Если целевой объект получает сообщение и в конечном счете примет его. В противном случае `asend` возвращает `false` для указания, что целевой объект отклонил сообщение или отложил решение о принятии сообщения.  
  
 [[В начало](#top)]  
  
##  <a name="receive"></a> Получение и try_receive  

 [Concurrency::receive](reference/concurrency-namespace-functions.md#receive) и [concurrency::try_receive](reference/concurrency-namespace-functions.md#try_receive) функции считывают данные из источника. `receive` Функция ожидает поступления данных станут доступными, тогда как `try_receive` функция немедленно возвращает.  
  
 Используйте `receive` работает, если необходимо иметь данные, чтобы продолжить. Используйте `try_receive` работать, если не должны блокировать текущий контекст или нет соответствующих данных, чтобы продолжить.  
  
 [[В начало](#top)]  
  
##  <a name="examples"></a> Примеры  
 Примеры использования `send` и `asend`, и `receive` функции, см. в следующих разделах:  
  
-   [Асинхронные блоки сообщений](../../parallel/concrt/asynchronous-message-blocks.md)  
  
-   [Практическое руководство. Реализация различных шаблонов "источник-приемник"](../../parallel/concrt/how-to-implement-various-producer-consumer-patterns.md)  
  
-   [Практическое руководство. Предоставление рабочих функций классам call и transformer](../../parallel/concrt/how-to-provide-work-functions-to-the-call-and-transformer-classes.md)  
  
-   [Практическое руководство. Использование преобразователя в конвейере данных](../../parallel/concrt/how-to-use-transformer-in-a-data-pipeline.md)  
  
-   [Практическое руководство. Выбор среди завершенных задач](../../parallel/concrt/how-to-select-among-completed-tasks.md)  
  
-   [Практическое руководство. Отправка сообщений через определенные интервалы](../../parallel/concrt/how-to-send-a-message-at-a-regular-interval.md)  
  
-   [Практическое руководство. Использование фильтра блоков сообщений](../../parallel/concrt/how-to-use-a-message-block-filter.md)  
  
 [[В начало](#top)]  
  
## <a name="see-also"></a>См. также  
 [Библиотека асинхронных агентов](../../parallel/concrt/asynchronous-agents-library.md)   
 [Асинхронные блоки сообщений](../../parallel/concrt/asynchronous-message-blocks.md)   
 [Функция Send](reference/concurrency-namespace-functions.md#send)   
 [Функция asend](reference/concurrency-namespace-functions.md#asend)   
 [Функция Receive](reference/concurrency-namespace-functions.md#receive)   
 [Функция try_receive](reference/concurrency-namespace-functions.md#try_receive)


