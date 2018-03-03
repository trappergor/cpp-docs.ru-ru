---
title: "Как: отправить сообщение через определенные интервалы | Документы Microsoft"
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
- timer class, example
- sending messages at regular intervals [Concurrency Runtime]
ms.assetid: 4b60ea6c-97c8-4d69-9f7b-ad79f3548026
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: f12d9f8af028d1e2e1fc149eeb77181c2f6b1730
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="how-to-send-a-message-at-a-regular-interval"></a>Практическое руководство. Отправка сообщений через определенные интервалы
В этом примере показано, как использовать параллелизма::[класс timer](../../parallel/concrt/reference/timer-class.md) для отправки сообщений через определенные интервалы.  
  
## <a name="example"></a>Пример  

 В следующем примере используется `timer` объекта уведомления о ходе выполнения длительной операции. Этот пример ссылки `timer` объект [concurrency::call](../../parallel/concrt/reference/call-class.md) объекта. `call` Выводит индикатор хода выполнения на консоль с регулярным интервалом. [Concurrency::Timer:: Start](reference/timer-class.md#start) запускает таймер в отдельном контексте. `perform_lengthy_operation` Вызовов функций [concurrency::wait](reference/concurrency-namespace-functions.md#wait) функции в основном контексте для имитации длительной операции.  

  
 [!code-cpp[concrt-report-progress#1](../../parallel/concrt/codesnippet/cpp/how-to-send-a-message-at-a-regular-interval_1.cpp)]  
  
 В этом примере получается следующий результат:  
  
```Output  
Performing a lengthy operation..........done.  
```  
  
## <a name="compiling-the-code"></a>Компиляция кода  
 Скопируйте код примера и вставьте его в проект Visual Studio или вставить его в файл с именем `report-progress.cpp` , а затем запустите следующую команду в окне командной строки Visual Studio.  
  
 **CL.exe/EHsc report-progress.cpp**  
  
## <a name="see-also"></a>См. также  
 [Библиотека асинхронных агентов](../../parallel/concrt/asynchronous-agents-library.md)   
 [Асинхронные блоки сообщений](../../parallel/concrt/asynchronous-message-blocks.md)   
 [Функции передачи сообщений](../../parallel/concrt/message-passing-functions.md)
