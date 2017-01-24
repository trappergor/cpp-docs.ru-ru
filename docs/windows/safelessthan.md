---
title: "SafeLessThan | Microsoft Docs"
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
  - "SafeLessThan"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "SafeLessThan - функция"
ms.assetid: 9d85bc0d-8d94-4d59-9b72-ef3c63a120a0
caps.latest.revision: 6
caps.handback.revision: 6
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# SafeLessThan
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Определяет, является ли один номер, чем другие.  
  
## Синтаксис  
  
```  
template<typename T, typename U>  
inline bool SafeLessThan (  
   const T t,  
   const U u  
) throw ();  
```  
  
#### Параметры  
 \[входящий\] `t`  
 Первый номер.  Это должно быть типа T.  
  
 \[входящий\] `u`  
 Второе numer.  Это должно быть типа U.  
  
## Возвращаемое значение  
 `true` при `t`, чем `u`; в противном случае `false`.  
  
## Заметки  
 Этот метод позволяет стандартный оператор сравнения, поскольку `SafeLessThan` позволяет сравнивать 2 поддерживаются два числа.  
  
 Этот метод часть [Библиотека SafeInt](../windows/safeint-library.md) и предназначен для одной операции сравнения без создания экземпляра [Класс SafeInt](../windows/safeint-class.md).  
  
> [!NOTE]
>  Этот метод должен использоваться, только если одна математических операций необходимо защитить.  Если несколько операций, то следует использовать класс `SafeInt`, а не отдельные отдельный вызов функции.  
  
 Дополнительные сведения о типах T шаблона и U см. в разделе [Функции SafeInt](../windows/safeint-functions.md).  
  
## Требования  
 **Заголовок:** safeint.h  
  
 **Пространство имен:** Microsoft::Utilities  
  
## См. также  
 [Функции SafeInt](../windows/safeint-functions.md)   
 [Библиотека SafeInt](../windows/safeint-library.md)   
 [Класс SafeInt](../windows/safeint-class.md)   
 [SafeLessThanEquals](../windows/safelessthanequals.md)   
 [SafeGreaterThan](../windows/safegreaterthan.md)   
 [SafeGreaterThanEquals](../windows/safegreaterthanequals.md)