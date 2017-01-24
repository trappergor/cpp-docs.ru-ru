---
title: "Оператор HString::Operator!= | Microsoft Docs"
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
  - "corewrappers/Microsoft::WRL::Wrappers::HString::operator!="
dev_langs: 
  - "C++"
ms.assetid: dcdd2aca-e7d6-4bf1-b2de-03efbb430a93
caps.latest.revision: 2
caps.handback.revision: 2
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Оператор HString::Operator!=
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Указывает, действительно ли два параметра не равны.  
  
## Синтаксис  
  
```cpp  
  
   inline bool operator!=(  
                  const HString& lhs,   
                  const HString& rhs) throw()  
  
inline bool operator!=(  
                  const HStringReference& lhs,   
                  const HString& rhs) throw()  
  
inline bool operator!=(  
                  const HString& lhs,   
                  const HStringReference& rhs) throw()  
  
inline bool operator!=(  
                  const HSTRING& lhs,   
                  const HString& rhs) throw()  
  
inline bool operator!=(  
                  const HString& lhs,   
                  const HSTRING& rhs) throw()  
  
```  
  
#### Параметры  
 `lhs`  
 Первый параметр для сравнения.  `lhs` может быть объектом HString или HStringReference или дескриптором HSTRING.  
  
 `rhs`  
 Второй параметр для сравнения.`rhs` может быть объектом HString или HStringReference или дескриптором HSTRING.  
  
## Возвращаемое значение  
 Значение `true`, если параметры `lhs` и `rhs` не равны; в противном случае — значение `false`.  
  
## Требования  
 **Заголовок:** corewrappers.h  
  
 **Пространство имен:** Microsoft::WRL::Wrappers  
  
## См. также  
 [Класс HString](../windows/hstring-class.md)