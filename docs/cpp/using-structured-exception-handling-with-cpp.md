---
title: "Использование структурированной обработки исключений с C++ | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- C++ exception handling, mixed with SEH
- structured exception handling, with C++ exception handling
ms.assetid: ec34b528-8c26-4429-b24a-6a68553aaa91
caps.latest.revision: 7
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 6ffef5f51e57cf36d5984bfc43d023abc8bc5c62
ms.openlocfilehash: 8f9805479d7ee9589cfd0da8491b0344d0bd7de1
ms.contentlocale: ru-ru
ms.lasthandoff: 09/25/2017

---
# <a name="using-structured-exception-handling-with-c"></a>Использование структурированной обработки исключений с C++
Структурированная обработка исключений, описанная в этих статьях, работает с файлами исходного кода на языках C и C++. Однако она не была разработана специально для языка C++ и ее использование не рекомендуется. Для того чтобы ваш код лучше переносился, лучше использовать механизм обработки исключений языка C++. Кроме того, механизм обработки исключений языка C++ обеспечивает более высокую гибкость, поскольку может обрабатывать исключения любого типа.  
  
 В Microsoft C++ теперь поддерживается модель обработки исключений C++, основанная на стандарте ANSI C++. Этот механизм обеспечивает автоматическое уничтожение локальных объектов во время очистки стека. Если при создании отказоустойчивого кода на языке C++ необходимо реализовать обработку исключений, настоятельно рекомендуется использовать обработку исключений языка C++, а не структурированную обработку исключений. (Обратите внимание, что в то время как компилятор C++ поддерживает конструкции структурированной обработки исключений, как описано в следующих статьях, но стандартный компилятор языка C не поддерживает синтаксис обработки исключений языка C++.) Подробные сведения об обработке исключений в C++ см. в разделе [обработку исключений C++](../cpp/cpp-exception-handling.md) и *аннотированного справочного руководства по C++* Эллис (Margaret Ellis) и Страуструп (Bjarne Stroustrup).  
  
## <a name="see-also"></a>См. также  
 [Структурированная обработка исключений (C/C++)](../cpp/structured-exception-handling-c-cpp.md)
