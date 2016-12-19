---
title: "Оператор HStringReference::Operator== | Microsoft Docs"
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
  - "corewrappers/Microsoft::WRL::Wrappers::HStringReference::operator=="
dev_langs: 
  - "C++"
ms.assetid: cad3d52d-cd67-4194-a270-5239b1121a09
caps.latest.revision: 2
caps.handback.revision: 2
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Оператор HStringReference::Operator==
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Указывает, действительно ли два параметра равны.  
  
## Синтаксис  
  
```cpp  
  
inline bool operator==(  
               const HStringReference& lhs,   
               const HStringReference& rhs) throw()  
  
inline bool operator==(  
               const HSTRING& lhs,   
               const HStringReference& rhs) throw()  
  
inline bool operator==(  
               const HStringReference& lhs,   
               const HSTRING& rhs) throw()  
  
```  
  
#### Параметры  
 `lhs`  
 Первый параметр для сравнения.  `lhs` может быть объектом HStringReference или дескриптором HSTRING.  
  
 `rhs`  
 Второй параметр для сравнения.  `rhs` может быть HStringReference или дескриптором HSTRING.  
  
## Возвращаемое значение  
 Значение `true`, если параметры `lhs` и `rhs` равны; в противном случае — значение `false`.  
  
## Требования  
 **Заголовок:** corewrappers.h  
  
 **Пространство имен:** Microsoft::WRL::Wrappers  
  
## См. также  
 [Класс HStringReference](../windows/hstringreference-class.md)