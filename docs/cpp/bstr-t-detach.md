---
title: "_bstr_t::Detach | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "_bstr_t::Detach"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Detach - метод"
ms.assetid: cc8284bd-f68b-4fff-b2e6-ce8354dabf8b
caps.latest.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# _bstr_t::Detach
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Блок, относящийся только к системам Microsoft**  
  
 Возвращает строку `BSTR`, инкапсулированную объектом `_bstr_t`, и отсоединяет ее \(`BSTR`\) от этого объекта \(`_bstr_t`\).  
  
## Синтаксис  
  
```  
  
BSTR Detach( ) throw;  
  
```  
  
## Возвращаемое значение  
 `BSTR` в оболочке `_bstr_t`.  
  
## Пример  
 Пример использования команды **Detach** см. в разделе [\_bstr\_t::Assign](../cpp/bstr-t-assign.md).  
  
 **Завершение блока, относящегося только к системам Microsoft**  
  
## См. также  
 [Класс \_bstr\_t](../cpp/bstr-t-class.md)