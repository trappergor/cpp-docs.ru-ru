---
title: "Класс bad_exception | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "std.bad_exception"
  - "bad_exception"
  - "std::bad_exception"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "bad_exception - класс"
ms.assetid: 5ae2c4ef-c7ad-4469-8a9e-a773e86bb000
caps.latest.revision: 20
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 20
---
# Класс bad_exception
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Данный класс описывает исключение, которое может быть создано из непредвиденный обработчик.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class bad_exception    : public exception {};  
```  
  
## <a name="remarks"></a>Заметки  
 [Непредвиденная](../Topic/%3Cexception%3E%20functions.md#unexpected) вызовет `bad_exception` вместо завершения или вместо вызова другой функции, указанной с помощью [set_unexpected](../Topic/%3Cexception%3E%20functions.md#set_unexpected) Если `bad_exception` включены в список исключения из функции.  
  
 Значение, возвращаемое **что** является строка C конкретной реализации. Ни одна из функций-членов не создает исключение.  
  
 Список наследуемых членов `bad_exception` см. в разделе [исключение класса](../standard-library/exception-class1.md).  
  
## <a name="example"></a>Пример  
 В разделе [set_unexpected](../Topic/%3Cexception%3E%20functions.md#set_unexpected) Пример использования [Непредвиденная](../Topic/%3Cexception%3E%20functions.md#unexpected) генерации `bad_exception`.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** \< исключения>  
  
 **Пространство имен:** std  
  
## <a name="see-also"></a>См. также  
[Класс Exception](../standard-library/exception-class1.md)
 [потокобезопасность в стандартной библиотеке C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)

