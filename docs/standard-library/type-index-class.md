---
title: "Класс type_index | Microsoft Docs"
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
  - "typeindex/std::type_index"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "type_index - класс"
ms.assetid: db366119-74cb-43e8-aacf-9679e561fa2f
caps.latest.revision: 14
caps.handback.revision: 4
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Класс type_index
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Класс `type_index` создания указатель на [Класс type\_info](../cpp/type-info-class.md) для облегчения индексировании такими объектами.  
  
```  
class type_index {  
public:  
    type_index(const type_info& tinfo);  
    const char *name() const;  
    size_t hash_code() const;  
    bool operator==(const type_info& right) const;  
    bool operator!=(const type_info& right) const;  
    bool operator<(const type_info& right) const;  
    bool operator<=(const type_info& right) const;  
    bool operator>(const type_info& right) const;  
    bool operator>=(const type_info& right) const;  
};  
```  
  
 Конструктор инициализирует `ptr` в `&tinfo`.  
  
 `name` возвращает `ptr->name()`.  
  
 `hash_code` возвращает `ptr->hash_code().`.  
  
 `operator==` возвращает `*ptr == right.ptr`.  
  
 `operator!=` возвращает `!(*this == right)`.  
  
 `operator<` возвращает `*ptr->before(*right.ptr)`.  
  
 `operator<=` возвращает `!(right < *this).`.  
  
 `operator>` возвращает `right < *this`.  
  
 `operator>=` возвращает `!(*this < right)`.  
  
## См. также  
 [Сведения о типах времени выполнения](../Topic/Run-Time%20Type%20Information.md)   
 [\<typeindex\>](../standard-library/typeindex.md)