---
title: "Класс make_unsigned | Microsoft Docs"
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
  - "std.tr1.make_unsigned"
  - "make_unsigned"
  - "std::tr1::make_unsigned"
  - "std.make_unsigned"
  - "std::make_unsigned"
  - "type_traits/std::make_unsigned"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "make_unsigned - класс [TR1]"
  - "make_unsigned"
ms.assetid: 7a6a3c4f-1a4c-47e8-9ee2-ac1f7b669353
caps.latest.revision: 18
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Класс make_unsigned
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Создает тип или наименьший беззнаковый тип, размер которого больше или равен размеру типа.  
  
## Синтаксис  
  
```  
template<class T>  
    struct make_unsigned;  
  
template<class T>  
    using make_unsigned_t = typename make_unsigned<T>::type;  
  
```  
  
#### Параметры  
  
|Параметр|Описание|  
|--------------|--------------|  
|`T`|Тип для изменения.|  
  
## Заметки  
 Экземпляр модификатора типа содержит модифицированный тип, т. е. `T`, если `is_unsigned<T>` содержит значение true.  В противном случае это наименьший тип со знаком `ST`, для которого `sizeof (T) <= sizeof (ST)`.  
  
## Требования  
 **Заголовок:** \<type\_traits\>  
  
 **Пространство имен:** std  
  
## См. также  
 [\<type\_traits\>](../standard-library/type-traits.md)