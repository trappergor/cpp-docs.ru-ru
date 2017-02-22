---
title: "Абстрактные деклараторы в C | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "абстрактные деклараторы"
  - "деклараторы, абстрактный"
ms.assetid: 6a556ad7-0555-421a-aa02-294d77cda8b5
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# Абстрактные деклараторы в C
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Абстрактный декларатор — это декларатор без идентификатора, состоящий из одного или нескольких указателей, массивов или модификаторов функций.  Модификатор указателя \(**\***\) всегда предшествует идентификатору в деклараторе; модификаторы массива \(**\[ \]**\) и функций \( **\( \)** \) следуют за идентификатором.  Зная это, можно определить, появится ли идентификатор в абстрактном деклараторе, и интерпретировать декларатор соответствующим образом.  В разделе [Интерпретация более сложных деклараторов](../c-language/interpreting-more-complex-declarators.md) содержатся дополнительные сведения и примеры сложных деклараторов.  Обычно для упрощения деклараторов можно использовать `typedef`.  См. раздел [Объявления Typedef](../c-language/typedef-declarations.md).  
  
 Абстрактные деклараторы могут быть сложными.  Круглые скобки в сложном абстрактном деклараторе определяют определенную интерпретацию, точно так же как для сложных деклараторов в объявлениях.  
  
 В следующих примерах показаны абстрактные деклараторы.  
  
```  
int *         // The type name for a pointer to type int:  
  
int *[3]      // An array of three pointers to int  
  
int (*) [5]   // A pointer to an array of five int  
  
int *()       // A function with no parameter specification  
              // returning a pointer to int  
  
// A pointer to a function taking no arguments and   
// returning an int  
  
int (*) ( void )    
  
// An array of an unspecified number of constant pointers to   
// functions each with one parameter that has type unsigned int   
// and an unspecified number of other parameters returning an int   
  
int (*const []) ( unsigned int, ... )  
```  
  
> [!NOTE]
>  Абстрактный декларатор не может состоять из набора пустых скобок, **\( \)**, поскольку он является неоднозначным.  Невозможно определить, принадлежит ли неявный идентификатор области внутри скобок \(и является в этом случае неизмененным типом\) или перед скобками \(и является в этом случае типом функции\).  
  
## См. также  
 [Деклараторы и объявления переменных](../c-language/declarators-and-variable-declarations.md)