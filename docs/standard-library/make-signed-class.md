---
title: "Класс make_signed | Microsoft Docs"
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
  - "std::tr1::make_signed"
  - "make_signed"
  - "std.tr1.make_signed"
  - "std.make_signed"
  - "std::make_signed"
  - "type_traits/std::make_signed"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "make_signed - класс [TR1]"
  - "make_signed"
ms.assetid: 686247c0-247c-496b-9b1b-ba9dcd633621
caps.latest.revision: 18
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Класс make_signed
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Создает тип или наименьшей знаковый тип, размер которого больше или равен размеру типа.  
  
## Синтаксис  
  
```  
template<class T>  
    struct make_signed;  
  
template<class T>  
    using make_signed_t = typename make_signed<T>::type;  
```  
  
#### Параметры  
 `T`  
 Тип для изменения.  
  
## Заметки  
 Экземпляр модификатора типа содержит модифицированный тип, т. е. `T`, если `is_signed<T>` содержит значение true. В противном случае это наименьший тип без знака `UT` для которого `sizeof (T) <= sizeof (UT)`.  
  
## Требования  
 **Заголовок:** \<type\_traits\>  
  
 **Пространство имен:** std  
  
## См. также  
 [\<type\_traits\>](../standard-library/type-traits.md)