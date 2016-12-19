---
title: "Структура once_flag | Microsoft Docs"
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
  - "mutex/std::once_flag"
dev_langs: 
  - "C++"
ms.assetid: 71bfb88d-ca8c-4082-a6e1-ff52151e8629
caps.latest.revision: 13
caps.handback.revision: 3
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Структура once_flag
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Представляет `struct`, используемый с шаблонной функцией [call\_once](../Topic/call_once%20Function.md), чтобы убедиться, что код инициализации вызывается только один раз, даже при наличии блокирующих нескольких потоков выполнения.  
  
## Синтаксис  
  
```cpp  
struct once_flag  
{  
   constexpr once_flag() noexcept;  
   once_flag(const once_flag&);  
   once_flag& operator=(const once_flag&);  
};  
```  
  
## Заметки  
 `once_flag` `struct` имеет только конструктор по умолчанию.  
  
 Объекты типа `once_flag` можно создать, но они не могут быть скопированы.  
  
## Требования  
 **Заголовок:** mutex  
  
 **Пространство имен:** std  
  
## См. также  
 [Справочные материалы по файлам заголовков](../standard-library/cpp-standard-library-header-files.md)   
 [\<mutex\>](../standard-library/mutex.md)