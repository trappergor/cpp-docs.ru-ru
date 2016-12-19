---
title: "Практическое руководство. Предоставление рабочих функций классам call и transformer | Microsoft Docs"
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
  - "класс call, пример"
  - "использование класса transformer [среда выполнения с параллелизмом]"
  - "использование класса call [среда выполнения с параллелизмом]"
ms.assetid: df715ce4-8507-41ca-b204-636d11707a73
caps.latest.revision: 15
caps.handback.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Практическое руководство. Предоставление рабочих функций классам call и transformer
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Этот раздел иллюстрирует несколько способов предоставления рабочих функций для классов [concurrency::call](../../parallel/concrt/reference/call-class.md) и [concurrency::transformer](../../parallel/concrt/reference/transformer-class.md).  
  
 Первый пример демонстрирует, как передать лямбда\-выражение объекту `call`.  Второй пример демонстрирует, как передать объект функции объекту `call`.  Третий пример демонстрирует, как привязать метод класса к объекту `call`.  
  
 Для иллюстрации во всех примерах этого раздела используется класс `call`.  Пример, который использует класс `transformer`, см. в разделе [Практическое руководство. Использование преобразователя в конвейере данных](../../parallel/concrt/how-to-use-transformer-in-a-data-pipeline.md).  
  
## Пример  
 В следующем примере показан обычный способ использования класса `call`.  В этом примере конструктору `call` передается лямбда\-функция.  
  
 [!code-cpp[concrt-call-lambda#1](../../parallel/concrt/codesnippet/CPP/how-to-provide-work-functions-to-the-call-and-transformer-classes_1.cpp)]  
  
 В результате выполнения примера получается следующий результат:  
  
  **13 в квадрате равно 169.**   
## Пример  
 Следующий пример похож на предыдущий, но в нем класс `call` используется совместно с объектом функции \(функтором\).  
  
 [!code-cpp[concrt-call-functor#1](../../parallel/concrt/codesnippet/CPP/how-to-provide-work-functions-to-the-call-and-transformer-classes_2.cpp)]  
  
## Пример  
 Следующий пример похож на предыдущий, но использует функции [std::bind1st](../Topic/bind1st%20Function.md) и [std::mem\_fun](../Topic/mem_fun%20Function.md) для привязки объекта `call` к методу класса.  
  
 Используйте этот способ, если требуется привязать объект `call` или `transformer` к конкретному методу класса, а не к оператору вызова функции, `operator()`.  
  
 [!code-cpp[concrt-call-method#1](../../parallel/concrt/codesnippet/CPP/how-to-provide-work-functions-to-the-call-and-transformer-classes_3.cpp)]  
  
 Результат функции `bind1st` также можно назначать объекту [std::function](../../standard-library/function-class.md) или использовать ключевое слово `auto`, как показано в следующем примере.  
  
 [!code-cpp[concrt-call-method#2](../../parallel/concrt/codesnippet/CPP/how-to-provide-work-functions-to-the-call-and-transformer-classes_4.cpp)]  
  
## Компиляция кода  
 Скопируйте код примера и вставьте его в проект Visual Studio или в файл с именем `call.cpp`, затем выполните в окне командной строки Visual Studio следующую команду.  
  
 **cl.exe \/EHsc call.cpp**  
  
## См. также  
 [Библиотека асинхронных агентов](../../parallel/concrt/asynchronous-agents-library.md)   
 [Асинхронные блоки сообщений](../../parallel/concrt/asynchronous-message-blocks.md)   
 [Практическое руководство. Использование преобразователя в конвейере данных](../../parallel/concrt/how-to-use-transformer-in-a-data-pipeline.md)   
 [Класс call](../../parallel/concrt/reference/call-class.md)   
 [Класс transformer](../../parallel/concrt/reference/transformer-class.md)