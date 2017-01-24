---
title: "_bstr_t::GetAddress | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "_bstr_t::GetAddress"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "GetAddress - метод"
ms.assetid: 09bc9180-867e-4ee5-b22a-8339dc663142
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# _bstr_t::GetAddress
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Блок, относящийся только к системам Microsoft**  
  
 Освобождает любую существующую строку и возвращает адрес новой строки, которой была выделена память.  
  
## Синтаксис  
  
```  
  
BSTR* GetAddress( );  
  
```  
  
## Возвращаемое значение  
 Указатель на строку `BSTR`, инкапсулированную объектом `_bstr_t`.  
  
## Заметки  
 Функция `GetAddress` действует на все объекты `_bstr_t`, которые совместно используют строку `BSTR`.  Одну и ту же строку `BSTR` может совместно использовать несколько объектов `_bstr_t`. Это делается при помощи конструктора копии и `operator=`.  
  
## Пример  
 Пример использования функции `GetAddress` см. в разделе [\_bstr\_t::Assign](../cpp/bstr-t-assign.md).  
  
 **Завершение блока, относящегося только к системам Microsoft**  
  
## См. также  
 [Класс \_bstr\_t](../cpp/bstr-t-class.md)