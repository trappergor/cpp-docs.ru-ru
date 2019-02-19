---
title: Абстрактные деклараторы в C
ms.date: 11/04/2016
helpviewer_keywords:
- declarators, abstract
- abstract declarations
ms.assetid: 6a556ad7-0555-421a-aa02-294d77cda8b5
ms.openlocfilehash: f2ca0f4a367abf939ed4307611517a883d8b82e0
ms.sourcegitcommit: f4be868c0d1d78e550fba105d4d3c993743a1f4b
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/12/2019
ms.locfileid: "56152668"
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
