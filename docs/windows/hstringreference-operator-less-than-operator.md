---
title: "Оператор HStringReference::Operator&lt; | Microsoft Docs"
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
  - "corewrappers/Microsoft::WRL::Wrappers::HStringReference::operator<"
dev_langs: 
  - "C++"
ms.assetid: 55aa48e8-7c96-4123-9ebe-42b4cd8b9377
caps.latest.revision: 2
caps.handback.revision: 2
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Оператор HStringReference::Operator&lt;
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Указывает, меньше ли первый параметр второго.  
  
## Синтаксис  
  
```cpp  
  
inline bool operator<(  
    const HStringReference& lhs,   
    const HStringReference& rhs) throw()  
  
```  
  
#### Параметры  
 `lhs`  
 Первый параметр для сравнения.  `lhs` может быть ссылкой на HStringReference.  
  
 `rhs`  
 Второй параметр, с которым выполняется сравнение.  `rhs` может быть ссылкой на HStringReference.  
  
## Возвращаемое значение  
 `true`, если значение параметра `lhs` меньше значения параметра `rhs`; в противном случае — значение `false`.  
  
## Требования  
 **Заголовок:** corewrappers.h  
  
 **Пространство имен:** Microsoft::WRL::Wrappers  
  
## См. также  
 [Класс HStringReference](../windows/hstringreference-class.md)