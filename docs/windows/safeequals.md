---
title: "SafeEquals | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "SafeEquals"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "SafeEquals - функция"
ms.assetid: 6019627d-f170-413b-9abd-2b5b34396a72
caps.latest.revision: 6
caps.handback.revision: 6
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# SafeEquals
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Сравнивает числа 2, чтобы определить, являются ли они равны.  
  
## Синтаксис  
  
```  
template<typename T, typename U>  
inline bool SafeEquals (  
   const T t,  
   const U u  
) throw ();  
```  
  
#### Параметры  
 \[входящий\] `t`  
 Первое число для сравнения.  Это должно быть типа T.  
  
 \[входящий\] `u`  
 Второе число для сравнения.  Это должно быть типа U.  
  
## Возвращаемое значение  
 `true`, если `t` и `u` равны; в ином случае — `false`.  
  
## Заметки  
 Метод увеличивает `==`, поскольку `SafeEquals` позволяет сравнивать 2 другого типа чисел.  
  
 Этот метод часть [Библиотека SafeInt](../windows/safeint-library.md) и предназначен для одной операции сравнения без создания экземпляра [Класс SafeInt](../windows/safeint-class.md).  
  
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
 [SafeNotEquals](../Topic/SafeNotEquals.md)