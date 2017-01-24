---
title: "SafeCast | Microsoft Docs"
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
  - "SafeCast"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "SafeCast - функция"
ms.assetid: 55316729-8456-403a-9f96-59d4038f67af
caps.latest.revision: 7
caps.handback.revision: 7
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# SafeCast
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Номера приведения одного типа в другой тип.  
  
## Синтаксис  
  
```  
template<typename T, typename U>  
inline bool SafeCast (  
   const T From,  
   U& To  
);  
```  
  
#### Параметры  
 \[входящий\] `From`  
 Номер источника, которое требуется преобразовать.  Это должно быть типа T.  
  
 \[исходящий\] `To`  
 Ссылка на новый тип числа.  Это должно быть типа U.  
  
## Возвращаемое значение  
 `true`, если ошибка не возникает. `false` при возникновении ошибки.  
  
## Заметки  
 Этот метод часть [Библиотека SafeInt](../windows/safeint-library.md) и предназначен для одной операции приведения без создания экземпляра [Класс SafeInt](../windows/safeint-class.md).  
  
> [!NOTE]
>  Этот метод должен использоваться, только если единственная операция необходимо защитить.  Если несколько операций, то следует использовать класс `SafeInt` вместо вызова отдельных изолированных функции.  
  
 Дополнительные сведения о типах T шаблона и U см. в разделе [Функции SafeInt](../windows/safeint-functions.md).  
  
## Требования  
 **Заголовок:** safeint.h  
  
 **Пространство имен:** Microsoft::Utilities  
  
## См. также  
 [Функции SafeInt](../windows/safeint-functions.md)   
 [Библиотека SafeInt](../windows/safeint-library.md)   
 [Класс SafeInt](../windows/safeint-class.md)