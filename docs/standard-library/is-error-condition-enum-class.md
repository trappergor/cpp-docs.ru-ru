---
title: "Класс is_error_condition_enum | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "std::is_error_condition_enum"
  - "std.is_error_condition_enum"
  - "is_error_condition_enum"
  - "system_error/std::is_error_condition_enum"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "is_error_condition_enum - класс"
ms.assetid: 752bb87a-c61c-4304-9254-5aaf228b59c0
caps.latest.revision: 15
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 15
---
# Класс is_error_condition_enum
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Представляет предикат типа, тесты для перечисления [error\_condition](../standard-library/error-condition-class.md).  
  
## Синтаксис  
  
```  
template<_Enum>  
    class is_error_condition_enum;  
```  
  
## Заметки  
 Экземпляр этого [предикат типа](../standard-library/type-traits.md) присвоено значение true, если тип `_Enum` перечисление соответствующее значение для хранения в объекте типа `error_condition`.  
  
 Допустимо добавлять специализации в этот тип для пользовательских типов.  
  
## Требования  
 **Заголовок:**\<system\_error\>  
  
 **Пространство имен:** std  
  
## См. также  
 [\<type\_traits\>](../standard-library/type-traits.md)   
 [\<system\_error\>](../standard-library/system-error.md)