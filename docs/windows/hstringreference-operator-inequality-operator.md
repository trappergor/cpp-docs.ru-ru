---
title: "Оператор HStringReference::O | Microsoft Docs"
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
  - "corewrappers/Microsoft::WRL::Wrappers::HStringReference::operator!="
dev_langs: 
  - "C++"
ms.assetid: 01ab6691-1fc7-4feb-85f0-fe795593a160
caps.latest.revision: 2
caps.handback.revision: 2
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Оператор HStringReference::O
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Указывает, действительно ли два параметра не равны.  
  
## Синтаксис  
  
```cpp  
  
inline bool operator==(  
               const HStringReference& lhs,   
               const HSTRING& rhs) throw()  
  
inline bool operator!=(  
               const HStringReference& lhs,   
               const HStringReference& rhs) throw()  
  
inline bool operator!=(  
               const HSTRING& lhs,   
               const HStringReference& rhs) throw()  
  
inline bool operator!=(  
               const HStringReference& lhs,   
               const HSTRING& rhs) throw()  
  
```  
  
#### Параметры  
 `lhs`  
 Первый параметр для сравнения.  `lhs` может быть объектом HStringReference или дескриптором HSTRING.  
  
 `rhs`  
 Второй параметр для сравнения. `rhs` может быть объектом типа HStringReference или дескриптором HSTRING.  
  
## Возвращаемое значение  
 Значение `true`, если параметры `lhs` и `rhs` не равны; в противном случае — значение `false`.  
  
## Требования  
 **Заголовок:** corewrappers.h  
  
 **Пространство имен:** Microsoft::WRL::Wrappers  
  
## См. также  
 [Класс HStringReference](../windows/hstringreference-class.md)