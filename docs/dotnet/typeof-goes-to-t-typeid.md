---
title: "Переход typeof в T::typeid | Microsoft Docs"
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
  - "__typeof - ключевое слово"
  - "typeid - ключевое слово [C++]"
  - "typeid - оператор"
ms.assetid: 6a0d35a7-7a1a-4070-b187-cff37cfdc205
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Переход typeof в T::typeid
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Оператор `typeof`, используемый в управляемых расширениях для C\+\+, был заменен ключевым словом `typeid` в [!INCLUDE[cpp_current_long](../dotnet/includes/cpp_current_long_md.md)].  
  
 В управляемых расширениях оператор `__typeof()` возвращает связанный объект `Type*` при передаче ему имени управляемого типа.  Примеры.  
  
```  
// Creates and initializes a new Array instance.  
Array* myIntArray =   
   Array::CreateInstance( __typeof(Int32), 5 );  
```  
  
 В новом синтаксисе `__typeof` заменяется дополнительной формой `typeid`, возвращающей `Type^` после указания управляемого типа.  
  
```  
// Creates and initializes a new Array instance.  
Array^ myIntArray =   
   Array::CreateInstance( Int32::typeid, 5 );  
```  
  
## См. также  
 [Общие изменения в языке](../Topic/General%20Language%20Changes%20\(C++-CLI\).md)   
 [typeid](../Topic/typeid%20%20\(C++%20Component%20Extensions\).md)