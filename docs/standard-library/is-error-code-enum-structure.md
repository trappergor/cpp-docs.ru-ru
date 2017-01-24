---
title: "Структура is_error_code_enum | Microsoft Docs"
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
  - "future/std::is_error_code_enum"
dev_langs: 
  - "C++"
ms.assetid: 84ae4b99-66d2-41ba-9b50-645fcbe14630
caps.latest.revision: 13
caps.handback.revision: 3
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Структура is_error_code_enum
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Специализация, указывающую, что [future\_errc](../Topic/future_errc%20Enumeration.md) используется для хранения [error\_code](../standard-library/error-code-class.md).  
  
## Синтаксис  
  
```  
template<>  
struct is_error_code_enum<Future_errc> : public true_type;  
```  
  
## Требования  
 **Заголовок:** future  
  
 **Пространство имен:** std  
  
## См. также  
 [Справочные материалы по файлам заголовков](../standard-library/cpp-standard-library-header-files.md)   
 [\<future\>](../standard-library/future.md)