---
title: "Как: Создание задачи, выполняемой после задержки | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- task_completion_event class, example
- create a task that completes after a delay, example [C++]
ms.assetid: 3fc0a194-3fdb-4eba-8b8a-b890981a985d
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: f9547bb5e586c20a22ce79d1227fa5f15b3ea305
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="how-to-create-a-task-that-completes-after-a-delay"></a>Практическое руководство. Создание задачи, выполняемой после задержки
В этом примере показано, как использовать [concurrency::task](../../parallel/concrt/reference/task-class.md), [concurrency::cancellation_token_source](../../parallel/concrt/reference/cancellation-token-source-class.md), [concurrency::cancellation_token](../../parallel/concrt/reference/cancellation-token-class.md), [ Concurrency::task_completion_event](../../parallel/concrt/reference/task-completion-event-class.md), [concurrency::timer](../../parallel/concrt/reference/timer-class.md), и [concurrency::call](../../parallel/concrt/reference/call-class.md) классы для создания задачи, выполняемой после задержки. Этот метод можно использовать для создания циклов, которые иногда запрашивают данные, используют время ожидания, задерживают обработку вводимых пользователем данных на заранее определенное время и т. д.  
  
## <a name="example"></a>Пример  
 В следующем примере показаны функции `complete_after` и `cancel_after_timeout`. Функция `complete_after` создает объект `task`, который выполняется после заданной задержки. Она использует объект `timer` и объект `call` для установки объекта `task_completion_event` после заданной задержки. С помощью класса `task_completion_event` можно определить задачу, которая выполняется после того, как поток или другая задача сообщает, что значение доступно. Когда событие установлено, задачи прослушивателя выполняются и их продолжения планируются для запуска.  
  
> [!TIP]
>  Дополнительные сведения о `timer` и `call` классы, которые являются частью библиотеки асинхронных агентов, в разделе [асинхронные блоки сообщений](../../parallel/concrt/asynchronous-message-blocks.md).  
  
 Функция `cancel_after_timeout` основана на функции `complete_after` и используется для отмены задачи, если эта задача не завершается до истечения заданного времени ожидания. Функция `cancel_after_timeout` создает две задачи. Первая задача указывает на успешное завершение и выполняется после завершения предоставленной задачи; вторая задача указывает на неудачный результат и выполняется после истечения заданного времени ожидания. Функция `cancel_after_timeout` создает задачу продолжения, которая выполняется после выполнения задачи, связанной с успешным или неудачным результатом. Если задача, связанная с неудачным результатом, завершается первой, продолжение отменяет источник токена для отмены всей задачи.  
  
 [!code-cpp[concrt-task-delay#1](../../parallel/concrt/codesnippet/cpp/how-to-create-a-task-that-completes-after-a-delay_1.cpp)]  
  
## <a name="example"></a>Пример  
 В следующем примере вычисляется количество простых чисел в диапазоне [0, 100000] несколько раз. Операция завершается неудачей, если она не выполняется полностью за указанное время. Функция `count_primes` демонстрирует, как использовать функцию `cancel_after_timeout`. Она подсчитывает количество простых чисел в заданном диапазоне и завершается неудачей, если задача не выполняется за предоставленное время. Функция `wmain` несколько раз вызывает функцию `count_primes`. Каждый раз она сокращает выделенное время в два раза. Программа завершается после того, как операция не выполняется за выделенное время.  
  
 [!code-cpp[concrt-task-delay#2](../../parallel/concrt/codesnippet/cpp/how-to-create-a-task-that-completes-after-a-delay_2.cpp)]  
  
 При использовании этого метода для отмены задачи после задержки все незапущенные задачи не запускаются после того, как отменяется общая задача. Однако важно, чтобы все продолжительные задачи реагировали на отмену своевременно. Дополнительные сведения об отмене задачи см. в разделе [Отмена в PPL](cancellation-in-the-ppl.md).  
  
## <a name="example"></a>Пример  
 Ниже приведен полный код этого примера.  
  
 [!code-cpp[concrt-task-delay#3](../../parallel/concrt/codesnippet/cpp/how-to-create-a-task-that-completes-after-a-delay_3.cpp)]  
  
## <a name="compiling-the-code"></a>Компиляция кода  
 Чтобы скомпилировать код, скопируйте его и затем вставьте его в проект Visual Studio или в файл с именем `task-delay.cpp` , а затем запустите следующую команду в окне командной строки Visual Studio.  
  
 **CL.exe/EHsc task-delay.cpp**  
  
## <a name="see-also"></a>См. также  
 [Параллелизм задач](../../parallel/concrt/task-parallelism-concurrency-runtime.md)   
 [Класс Task (среда выполнения параллелизма)](../../parallel/concrt/reference/task-class.md)   
 [Класс cancellation_token_source](../../parallel/concrt/reference/cancellation-token-source-class.md)   
 [Класс cancellation_token](../../parallel/concrt/reference/cancellation-token-class.md)   
 [Класс task_completion_event](../../parallel/concrt/reference/task-completion-event-class.md)   
 [Класс Timer](../../parallel/concrt/reference/timer-class.md)   
 [Класс Call](../../parallel/concrt/reference/call-class.md)   
 [Асинхронные блоки сообщений](../../parallel/concrt/asynchronous-message-blocks.md)   
 [Отмена в библиотеке параллельных шаблонов](cancellation-in-the-ppl.md)

