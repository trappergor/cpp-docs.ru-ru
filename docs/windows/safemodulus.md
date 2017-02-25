---
title: "SafeModulus | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "SafeModulus"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "SafeModulus - функция"
ms.assetid: ae5c81eb-5dcf-45a5-aa76-465fdfe68654
caps.latest.revision: 6
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
caps.handback.revision: 6
---
# SafeModulus
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Выполняет операцию модуля на номерах 2.  
  
## Синтаксис  
  
```  
template<typename T, typename U>  
inline bool SafeModulus (  
   const T t,  
   const U u,  
   T& result  
) throw ();  
```  
  
#### Параметры  
 \[входящий\] `t`  
 Делитель.  Это должно быть типа T.  
  
 \[входящий\] `u`  
 Делимое.  Это должно быть типа U.  
  
 \[исходящий\] `result`  
 Параметр, `SafeModulus` сохраняет результат.  
  
## Возвращаемое значение  
 `true`, если ошибка не возникает. `false` при возникновении ошибки.  
  
## Заметки  
 Этот метод часть [Библиотека SafeInt](../windows/safeint-library.md) и предназначен для одной операции модуля без создания экземпляра [Класс SafeInt](../windows/safeint-class.md).  
  
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
 [SafeDivide](../windows/safedivide.md)