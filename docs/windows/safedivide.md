---
title: "SafeDivide | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "SafeDivide"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "SafeDivide - функция"
ms.assetid: b5b27484-ad6e-46b1-ba9f-1c7120dd103b
caps.latest.revision: 5
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
caps.handback.revision: 5
---
# SafeDivide
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Делит 2 числа в поведении защищает от при делении на ноль.  
  
## Синтаксис  
  
```  
template<typename T, typename U>  
inline bool SafeDivide (  
   T t,  
   U u,  
   T& result  
) throw ();  
```  
  
#### Параметры  
 \[входящий\] `t`  
 Делитель.  Это должно быть типа T.  
  
 \[входящий\] `u`  
 Делимое.  Это должно быть типа U.  
  
 \[исходящий\] `result`  
 Параметр, `SafeDivide` сохраняет результат.  
  
## Возвращаемое значение  
 `true`, если ошибка не возникает. `false` при возникновении ошибки.  
  
## Заметки  
 Этот метод часть [Библиотека SafeInt](../windows/safeint-library.md) и предназначен для одной операции деления без создания экземпляра [Класс SafeInt](../windows/safeint-class.md).  
  
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
 [SafeModulus](../windows/safemodulus.md)   
 [SafeMultiply](../Topic/SafeMultiply.md)