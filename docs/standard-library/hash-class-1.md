---
title: "Класс hash | Microsoft Docs"
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
  - "std.hash"
  - "xfunctional/std::hash"
  - "hash"
  - "typeindex/std::hash"
  - "std::hash"
  - "std.tr1.hash"
  - "std::tr1::hash"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "hash - класс"
  - "hash - класс [TR1]"
ms.assetid: e1b500c6-a5c8-4f6f-ad33-7ec52eb8e2e4
caps.latest.revision: 21
caps.handback.revision: 13
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Класс hash
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Вычисляет хэш\-код для значения.  
  
## Синтаксис  
  
```  
template<class Ty>  
    struct hash  
        : public unary_function<Ty, size_t> {  
    size_t operator()(Ty _Val) const;  
    };  
```  
  
## Заметки  
 Определяет, соответствующее функцию\-член хэш\-функции для сопоставления значений типа `Ty` на распределение значений индекса.  Оператор члена возвращает хэш\-код для `_Val`, не подходит для использования с шаблонными классами `unordered_map`, `unordered_multimap`, `unordered_set` и `unordered_multiset`.  `Ty` может быть любым скалярным типом, `string`, `wstring`, `error_code`, `error_condition`, `u16string` или `u32string`.  
  
## Пример  
  
```  
// std_tr1__functional__hash.cpp   
// compile with: /EHsc   
#include <functional>   
#include <iostream>   
#include <unordered_set>   
  
int main()   
    {   
    std::unordered_set<int, std::hash<int> > c0;   
    c0.insert(3);   
    std::cout << *c0.find(3) << std::endl;   
  
    return (0);   
    }  
  
```  
  
 **3**   
## Требования  
 **Заголовок:** \<functional\>  
  
 **Пространство имен:** std  
  
## См. также  
 [\<unordered\_map\>](../standard-library/unordered-map.md)   
 [Класс unordered\_multimap](../standard-library/unordered-multimap-class.md)   
 [Класс unordered\_multiset](../standard-library/unordered-multiset-class.md)   
 [\<unordered\_set\>](../standard-library/unordered-set.md)