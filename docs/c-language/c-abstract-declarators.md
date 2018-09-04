---
title: Абстрактные деклараторы в C | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- declarators, abstract
- abstract declarations
ms.assetid: 6a556ad7-0555-421a-aa02-294d77cda8b5
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: ea9ca44dbc484749cc10a59fec0b91d096921827
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/29/2018
ms.locfileid: "43214536"
---
# <a name="c-abstract-declarators"></a>Абстрактные деклараторы в C
Абстрактный декларатор — это декларатор без идентификатора, состоящий из одного или нескольких указателей, массивов или модификаторов функций. Модификатор указателя (<strong>\*</strong>) всегда предшествует идентификатору в деклараторе, а за идентификатором следуют модификаторы массива (**[ ]**) и функций (**( )**). Зная это, можно определить, появится ли идентификатор в абстрактном деклараторе, и интерпретировать декларатор соответствующим образом. В статье [Интерпретация сложных деклараторов](../c-language/interpreting-more-complex-declarators.md) содержатся дополнительные сведения и примеры сложных деклараторов. Обычно для упрощения деклараторов можно использовать `typedef`. См. статью [Объявления Typedef](../c-language/typedef-declarations.md).  
  
 Абстрактные деклараторы могут быть сложными. Круглые скобки в сложном абстрактном деклараторе определяют определенную интерпретацию, точно так же как для сложных деклараторов в объявлениях.  
  
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
>  Абстрактный декларатор не может состоять из набора пустых скобок, **( )**, поскольку такая запись является неоднозначной. Невозможно определить, принадлежит ли неявный идентификатор области внутри скобок (и является в этом случае неизмененным типом) или перед скобками (и является в этом случае типом функции).  
  
## <a name="see-also"></a>См. также  
 [Деклараторы и объявления переменных](../c-language/declarators-and-variable-declarations.md)