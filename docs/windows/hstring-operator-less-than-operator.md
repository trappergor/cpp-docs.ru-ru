---
title: "Оператор HString::Operator&lt; | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "corewrappers/Microsoft::WRL::Wrappers::HString::operator<"
dev_langs: 
  - "C++"
ms.assetid: 48a051cb-4609-42be-b48c-d35fc99d1eab
caps.latest.revision: 2
caps.handback.revision: 2
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Оператор HString::Operator&lt;
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Указывает, меньше ли первый параметр второго.  
  
## Синтаксис  
  
```cpp  
  
inline bool operator<(  
    const HString& lhs,   
    const HString& rhs) throw()  
  
```  
  
#### Параметры  
 `lhs`  
 Первый параметр для сравнения.  `lhs` может быть ссылкой на HString.  
  
 `rhs`  
 Второй параметр для сравнения.  `rhs` может быть ссылкой на HString.  
  
## Возвращаемое значение  
 `true`, если значение параметра `lhs` меньше значения параметра `rhs`; в противном случае — значение `false`.  
  
## Требования  
 **Заголовок:** corewrappers.h  
  
 **Пространство имен:** Microsoft::WRL::Wrappers  
  
## См. также  
 [Класс HString](../windows/hstring-class.md)