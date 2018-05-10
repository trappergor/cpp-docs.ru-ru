---
title: 'Как: реализация различных шаблонов производитель получатель | Документы Microsoft'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- producer-consumer patterns, implementing [Concurrency Runtime]
- implementing producer-consumer patterns [Concurrency Runtime]
ms.assetid: 75f2c7cc-5399-49ea-98eb-847fe6747169
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 50a6683db37fb6e994c1957a8df3ab6469acff6d
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2018
---
# <a name="how-to-implement-various-producer-consumer-patterns"></a>Практическое руководство. Реализация различных шаблонов "источник-приемник"
Описывается, как для реализации шаблона производитель получатель в приложении. В этом шаблоне *производитель* отправляет сообщения в блок сообщений, а *потребитель* считывает сообщения из этого блока.  
  
 В этом разделе показано два сценария. В первом сценарии получатель должен получить каждое сообщение, отправленное производителем. Во втором сценарии получатель запрашивает данные периодически и поэтому не должен принять каждое сообщение.  
  
 В обоих примерах в этом разделе для передачи сообщений от производителя получателю использовать агенты, блоки сообщений и функции передачи сообщений. Использует агент производителя [concurrency::send](reference/concurrency-namespace-functions.md#send) функцию для записи сообщений в [concurrency::ITarget](../../parallel/concrt/reference/itarget-class.md) объекта. Использует агент потребителя [concurrency::receive](reference/concurrency-namespace-functions.md#receive) функция для чтения сообщений из [concurrency::ISource](../../parallel/concrt/reference/isource-class.md) объекта. Оба агента содержат контрольного значения для координации о завершении обработки.  
  
 Дополнительные сведения об асинхронных агентов см. в разделе [асинхронных агентов](../../parallel/concrt/asynchronous-agents.md). Дополнительные сведения о блоках сообщений и функции передачи сообщений см. в разделе [асинхронные блоки сообщений](../../parallel/concrt/asynchronous-message-blocks.md) и [функции передачи сообщений](../../parallel/concrt/message-passing-functions.md).  
  
## <a name="example"></a>Пример  
 В этом примере агент производителя отправляет агенту получателя ряд чисел. Потребитель получает эти числа и вычисляет их среднее значение. Приложение записывает среднее значение на консоль.  
  
 В этом примере используется [concurrency::unbounded_buffer](reference/unbounded-buffer-class.md) объект для разрешения для очереди сообщений. `unbounded_buffer` Класс реализует `ITarget` и `ISource` , чтобы потребитель и производитель могут отправлять и получать сообщения из общего буфера. `send` И `receive` координируют задачу передачи данных от производителя получателю.  
  
 [!code-cpp[concrt-producer-consumer-average#1](../../parallel/concrt/codesnippet/cpp/how-to-implement-various-producer-consumer-patterns_1.cpp)]  
  
 В этом примере формируются следующие данные:  
  
```Output  
The average is 50.  
```  
  
## <a name="example"></a>Пример  
 В этом примере агент производителя отправляет агенту получателя ряд биржевых котировок. Агент потребителя периодически выполняет чтение текущей котировки и выводит на консоль.  
  
 В этом примере похож на предыдущий, за исключением того, что он использует [concurrency::overwrite_buffer](../../parallel/concrt/reference/overwrite-buffer-class.md) для обеспечения совместного использования одного сообщения к получателю. Как в предыдущем примере `overwrite_buffer` класс реализует `ITarget` и `ISource` , чтобы потребитель и производитель могут действовать от общего буфера.  
  
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
  
 В отличие от с `unbounded_buffer` объекта, `receive` функция не удаляет сообщение из `overwrite_buffer` объекта. Если потребитель считывает из буфера сообщений более чем один раз, прежде чем производитель перезапишет это сообщение, получатель получает это сообщение каждый раз.  
  
## <a name="compiling-the-code"></a>Компиляция кода  
 Скопируйте код примера и вставьте его в проект Visual Studio или вставить его в файл с именем `producer-consumer.cpp` , а затем запустите следующую команду в окне командной строки Visual Studio.  
  
 **CL.exe/EHsc производитель consumer.cpp**  
  
## <a name="see-also"></a>См. также  
 [Библиотека асинхронных агентов](../../parallel/concrt/asynchronous-agents-library.md)   
 [Асинхронные агенты](../../parallel/concrt/asynchronous-agents.md)   
 [Асинхронные блоки сообщений](../../parallel/concrt/asynchronous-message-blocks.md)   
 [Функции передачи сообщений](../../parallel/concrt/message-passing-functions.md)
