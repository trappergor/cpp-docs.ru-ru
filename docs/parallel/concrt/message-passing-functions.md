---
title: "Функции передачи сообщений | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "функции передачи сообщений"
ms.assetid: 42477c9e-a8a6-4dc4-a98e-93c6dc8c4dd0
caps.latest.revision: 23
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 22
---
# Функции передачи сообщений
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Библиотека асинхронных агентов предоставляет несколько функций, которые позволяют передавать сообщения между компонентами.  
  
 Эти функции передачи сообщений используются с различными типами блоков сообщений.  Дополнительные сведения о типах блоков сообщений, определяемых средой выполнения с параллелизмом, см. в разделе [Асинхронные блоки сообщений](../../parallel/concrt/asynchronous-message-blocks.md).  
  
##  <a name="top"></a> Подразделы  
 В этом разделе описываются следующие функции передачи сообщений:  
  
-   [send и asend](#send)  
  
-   [receive и try\_receive](#receive)  
  
-   [Примеры](#examples)  
  
##  <a name="send"></a> send и asend  
 Функция [concurrency::send](../Topic/send%20Function.md) отправляет сообщение заданному целевому объекту синхронно, а функция [concurrency::asend](../Topic/asend%20Function.md) — асинхронно.  Функции `send` и `asend` ждут, пока целевой объект укажет, примет он сообщение или отклонит.  
  
 Перед возвращением функция `send` ожидает принятия или отклонения сообщения целевым объектом.  Функция `send` возвращает значение `true`, если сообщение было доставлено; в противном случае — значение `false`.  Поскольку функция `send` работает синхронно, перед возвращением эта функция `send` ожидает получения сообщения целевым объектом.  
  
 Функция `asend`, наоборот, перед возвратом не ждет, пока целевой объект примет или отклонит сообщение.  Вместо этого функция `asend` возвращает значение `true`, если целевой объект получает сообщение и в конечном счете примет его.  В противном случае `asend` возвращает значение `false`, чтобы указать, что целевой объект отклонил сообщение или отложил решение о принятии сообщения.  
  
 \[[Наверх](#top)\]  
  
##  <a name="receive"></a> receive и try\_receive  
 Функции [concurrency::receive](../Topic/receive%20Function.md) и [concurrency::try\_receive](../Topic/try_receive%20Function.md) считывают данные из данного источника.  Функция `receive` ожидает, пока данные станут доступными, а функция `try_receive` возвращается немедленно.  
  
 Использовать функцию `receive` следует в случаях, когда для продолжения обязательно наличие данных.  Использовать функцию `try_receive` следует в случаях, когда нельзя блокировать текущий контекст или для продолжения не обязательно наличие данных.  
  
 \[[Наверх](#top)\]  
  
##  <a name="examples"></a> Примеры  
 Примеры использования функций `send`, `asend` и `receive` см. в следующих разделах.  
  
-   [Асинхронные блоки сообщений](../../parallel/concrt/asynchronous-message-blocks.md)  
  
-   [Практическое руководство. Реализация различных шаблонов "источник\-приемник"](../../parallel/concrt/how-to-implement-various-producer-consumer-patterns.md)  
  
-   [Практическое руководство. Предоставление рабочих функций классам call и transformer](../../parallel/concrt/how-to-provide-work-functions-to-the-call-and-transformer-classes.md)  
  
-   [Практическое руководство. Использование преобразователя в конвейере данных](../../parallel/concrt/how-to-use-transformer-in-a-data-pipeline.md)  
  
-   [Практическое руководство. Выбор среди завершенных задач](../../parallel/concrt/how-to-select-among-completed-tasks.md)  
  
-   [Практическое руководство. Отправка сообщений через определенные интервалы](../../parallel/concrt/how-to-send-a-message-at-a-regular-interval.md)  
  
-   [Практическое руководство. Использование фильтра блоков сообщений](../../parallel/concrt/how-to-use-a-message-block-filter.md)  
  
 \[[Наверх](#top)\]  
  
## См. также  
 [Библиотека асинхронных агентов](../../parallel/concrt/asynchronous-agents-library.md)   
 [Асинхронные блоки сообщений](../../parallel/concrt/asynchronous-message-blocks.md)   
 [Функция send](../Topic/send%20Function.md)   
 [Функция asend](../Topic/asend%20Function.md)   
 [Функция receive](../Topic/receive%20Function.md)   
 [Функция try\_receive](../Topic/try_receive%20Function.md)