---
title: "Класс conditional | Microsoft Docs"
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
  - "std::tr1::conditional"
  - "std.tr1.conditional"
  - "conditional"
  - "std.conditional"
  - "std::conditional"
  - "type_traits/std::conditional"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "conditional - класс [TR1]"
  - "conditional"
ms.assetid: ece9f539-fb28-4e26-a79f-3264bc984493
caps.latest.revision: 22
caps.handback.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Класс conditional
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Выделяет один из 2 типов в зависимости от указанного условия.  
  
## Синтаксис  
  
```  
template <bool B, class T1, class T2>  
    struct conditional;  
  
template <bool _Test, class _T1, class _T2>  
    using conditional_t = typename conditional<_Test, _T1, _T2>::type;  
```  
  
#### Параметры  
 `B`  
 Значение, определяющее выбранный тип.  
  
 `T1`  
 Результат типа, если B — true.  
  
 `T2`  
 Результат типа, если B — false.  
  
## Заметки  
 Член шаблона typedef `conditional<B, T1, T2>::type` равен `T1`, если параметр `B` равен `true`, или `T2`, если параметр `B` равен `false`.  
  
## Требования  
 **Заголовок:** \<type\_traits\>  
  
 **Пространство имен:** std  
  
## См. также  
 [\<type\_traits\>](../standard-library/type-traits.md)