---
title: 'Как: предоставление рабочих функций классам call и transformer | Документы Microsoft'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- call class, example
- using the transformer class [Concurrency Runtime]
- using the call class [Concurrency Runtime]
ms.assetid: df715ce4-8507-41ca-b204-636d11707a73
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: ca7948a1258ac1b5193d379dd37f426360edc42e
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2018
---
# <a name="how-to-provide-work-functions-to-the-call-and-transformer-classes"></a>Практическое руководство. Предоставление рабочих функций классам call и transformer
В этом разделе приводится несколько способов предоставления рабочих функций [concurrency::call](../../parallel/concrt/reference/call-class.md) и [concurrency::transformer](../../parallel/concrt/reference/transformer-class.md) классы.  
  
 Первый пример показывает, как передавать лямбда-выражение, `call` объекта. Во втором примере показано, как передать объект функции в `call` объекта. Третий пример показано, как привязать метод класса для `call` объекта.  
  
 Иллюстрации каждого примера в этом разделе используются `call` класса. Пример, использующий `transformer` см. в описании [как: использование преобразователя в конвейере данных](../../parallel/concrt/how-to-use-transformer-in-a-data-pipeline.md).  
  
## <a name="example"></a>Пример  
 В следующем примере показано простой способ использования `call` класса. В этом примере передается лямбда-функцией для `call` конструктор.  
  
 [!code-cpp[concrt-call-lambda#1](../../parallel/concrt/codesnippet/cpp/how-to-provide-work-functions-to-the-call-and-transformer-classes_1.cpp)]  
  
 В этом примере формируются следующие данные:  
  
```Output  
13 squared is 169.  
```  
  
## <a name="example"></a>Пример  
 Следующий пример похож на предыдущий, за исключением того, что он использует `call` класса вместе с объектом функции (функтор).  
  
 [!code-cpp[concrt-call-functor#1](../../parallel/concrt/codesnippet/cpp/how-to-provide-work-functions-to-the-call-and-transformer-classes_2.cpp)]  
  
## <a name="example"></a>Пример  

 Следующий пример похож на предыдущий, за исключением того, что он использует [std::bind1st](../../standard-library/functional-functions.md#bind1st) и [std::mem_fun](../../standard-library/functional-functions.md#mem_fun) функции связываемом `call` объекта к методу класса.  

  
 Этот метод следует использовать, если требуется привязать `call` или `transformer` в метод определенного класса, а не к оператору вызова функции `operator()`.  
  
 [!code-cpp[concrt-call-method#1](../../parallel/concrt/codesnippet/cpp/how-to-provide-work-functions-to-the-call-and-transformer-classes_3.cpp)]  
  
 Можно также назначить результат `bind1st` функция [std::function](../../standard-library/function-class.md) или `auto` ключевое слово, как показано в следующем примере.  
  
 [!code-cpp[concrt-call-method#2](../../parallel/concrt/codesnippet/cpp/how-to-provide-work-functions-to-the-call-and-transformer-classes_4.cpp)]  
  
## <a name="compiling-the-code"></a>Компиляция кода  
 Скопируйте код примера и вставьте его в проект Visual Studio или вставить его в файл с именем `call.cpp` , а затем запустите следующую команду в окне командной строки Visual Studio.  
  
 **CL.exe call.cpp/EHsc**  
  
## <a name="see-also"></a>См. также  
 [Библиотека асинхронных агентов](../../parallel/concrt/asynchronous-agents-library.md)   
 [Асинхронные блоки сообщений](../../parallel/concrt/asynchronous-message-blocks.md)   
 [Как: использование преобразователя в конвейере данных](../../parallel/concrt/how-to-use-transformer-in-a-data-pipeline.md)   
 [Класс Call](../../parallel/concrt/reference/call-class.md)   
 [Класс transformer](../../parallel/concrt/reference/transformer-class.md)
