---
title: "Практическое руководство. Отправка сообщений через определенные интервалы | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Класс timer, пример"
  - "отправка сообщений через равные интервалы [среда выполнения с параллелизмом]"
ms.assetid: 4b60ea6c-97c8-4d69-9f7b-ad79f3548026
caps.latest.revision: 19
caps.handback.revision: 19
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Практическое руководство. Отправка сообщений через определенные интервалы
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

В этом примере показано, как использовать параллелизм::[класс timer](../../parallel/concrt/reference/timer-class.md) для отправки сообщений через определенные интервалы.  
  
## <a name="example"></a>Пример  
 В следующем примере используется `timer` объекта для отчета о ходе выполнения длительной операции. В данном примере содержатся ссылки `timer` объект [concurrency::call](../../parallel/concrt/reference/call-class.md) объекта.  `call` Выводит индикатор хода выполнения на консоль через определенные интервалы.  [Concurrency::Timer:: Start](../Topic/timer::start%20Method.md) запускает таймер в отдельном контексте.  `perform_lengthy_operation` Вызовы функций [concurrency::wait](../Topic/wait%20Function.md) функции в основном контексте для имитации длительной операции.  
  
 [!CODE [concrt-report-progress#1](../CodeSnippet/VS_Snippets_ConcRT/concrt-report-progress#1)]  
  
 Этот пример выдает следующий результат:  
  
```Output  
Performing a lengthy operation..........done.  
```  
  
## <a name="compiling-the-code"></a>Компиляция кода  
 Скопируйте код примера и вставьте его в проект Visual Studio и вставьте его в файл с именем `report-progress.cpp` и затем выполните следующую команду в окне командной строки Visual Studio.  
  
 **/ EHsc CL.exe report-progress.cpp**  
  
## <a name="see-also"></a>См. также раздел  
 [Библиотека асинхронных агентов](../../parallel/concrt/asynchronous-agents-library.md)   
 [Асинхронные блоки сообщений](../../parallel/concrt/asynchronous-message-blocks.md)   
 [Функции передачи сообщений](../../parallel/concrt/message-passing-functions.md)
