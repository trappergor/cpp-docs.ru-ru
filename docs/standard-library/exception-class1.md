---
title: "Класс exception | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "std.exception"
  - "exception"
  - "std::exception"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "exception - класс"
ms.assetid: 4f181f67-5888-4b50-89a6-745091ffb2fe
caps.latest.revision: 19
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Класс exception
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Этот класс служит базовым классом для всех исключений, определенными выражениями стандартной библиотеки C\+\+.  
  
## Синтаксис  
  
```  
class exception {  
public:  
    exception();  
    exception(const char * const &message);  
    exception(const char * const &message, int);  
    exception(const exception &right);  
    exception& operator=(const exception &right);  
    virtual ~exception();  
    virtual const char *what() const;  
};  
```  
  
## Заметки  
 В частности, этот базовый класс корень стандартных классов исключений, определенных в [\<stdexcept\>](../standard-library/stdexcept.md).  Строковое значение C, `what` производится неуказанным конструктором по умолчанию, но может быть определено производным классом конструкторов для определенных как предоставления определенной строке C.  Ни один из вызывают функции\-члены все исключения.  
  
 Параметр `int` позволяет определить отсутствия памяти не должна быть выбрана.  Значение `int` игнорируется.  
  
> [!NOTE]
>  Конструкторы `exception(const char * const &message)` и `exception(const char * const &message, int)` расширения Microsoft C в стандартной библиотеке C\+\+.  
  
## Пример  
 Примеры использования стандартных классов исключений, которые являются производными от класса `exception` см. в любые классы, указанным в [\<stdexcept\>](../standard-library/stdexcept.md).  
  
## Требования  
 **Заголовок:**\<exception\>  
  
 **Пространство имен:** std  
  
## См. также  
 [Потокобезопасность в стандартной библиотеке C\+\+](../standard-library/thread-safety-in-the-cpp-standard-library.md)