---
title: "Класс is_error_code_enum | Microsoft Docs"
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
  - "system_error/std::is_error_code_enum"
  - "std.is_error_code_enum"
  - "is_error_code_enum"
  - "std::is_error_code_enum"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "is_error_code_enum - класс"
ms.assetid: cee5be2d-7c20-4cec-a352-1ab8b7d32601
caps.latest.revision: 15
caps.handback.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Класс is_error_code_enum
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Представляет предикат типа, тесты для перечисления [error\_code](../standard-library/error-code-class.md).  
  
## Синтаксис  
  
```  
template<_Enum>  
    class is_error_code_enum;  
```  
  
## Заметки  
 Экземпляр этого [предикат типа](../standard-library/type-traits.md) присвоено значение true, если тип `_Enum` перечисление соответствующее значение для хранения в объекте типа `error_code`.  
  
 Допустимо добавлять специализации в этот тип для пользовательских типов.  
  
## Требования  
 **Заголовок:**\<system\_error\>  
  
 **Пространство имен:** std  
  
## См. также  
 [\<type\_traits\>](../standard-library/type-traits.md)   
 [\<system\_error\>](../standard-library/system-error.md)