---
title: "SafeSubtract | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "SafeSubtract"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "SafeSubtract - функция"
ms.assetid: c2712ddc-173f-46a1-b09c-e7ebbd9e68b2
caps.latest.revision: 5
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
caps.handback.revision: 5
---
# SafeSubtract
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Вычитает 2 числа в поведении защищает от переполнения.  
  
## Синтаксис  
  
```  
template<typename T, typename U>  
inline bool SafeSubtract (  
   T t,  
   U u,  
   T& result  
) throw ();  
```  
  
#### Параметры  
 \[входящий\] `t`  
 Первый номер в вычитании.  Это должно быть типа T.  
  
 \[входящий\] `u`  
 Число, которое вычитается из `t`.  Это должно быть типа U.  
  
 \[исходящий\] `result`  
 Параметр, `SafeSubtract` сохраняет результат.  
  
## Возвращаемое значение  
 `true`, если ошибка не возникает. `false` при возникновении ошибки.  
  
## Заметки  
 Этот метод часть [Библиотека SafeInt](../windows/safeint-library.md) и предназначен для одной операции вычитания без создания экземпляра [Класс SafeInt](../windows/safeint-class.md).  
  
> [!NOTE]
>  Этот метод должен использоваться, только если одна математических операций необходимо защитить.  Если несколько операций, то следует использовать класс `SafeInt` вместо вызова отдельных изолированных функции.  
  
 Дополнительные сведения о типах T шаблона и U см. в разделе [Функции SafeInt](../windows/safeint-functions.md).  
  
## Требования  
 **Заголовок:** safeint.h  
  
 **Пространство имен:** Microsoft::Utilities  
  
## См. также  
 [Функции SafeInt](../windows/safeint-functions.md)   
 [Библиотека SafeInt](../windows/safeint-library.md)   
 [Класс SafeInt](../windows/safeint-class.md)   
 [SafeAdd](../windows/safeadd.md)