---
title: "регистр (C++) | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- vc-attr.case
dev_langs:
- C++
helpviewer_keywords:
- case attribute
ms.assetid: 6fb883c3-0526-4932-a901-b4564dcaeb7d
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: adacffa4dbce4cc908c393cb5019375234e9ff85
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="case-c"></a>case (C++)
При использовании [switch_type](../windows/switch-type.md) атрибута в **объединение**.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
      [ case(  
   value  
) ]  
```  
  
#### <a name="parameters"></a>Параметры  
 *значение*  
 Возможное значение ввода, для которого требуется обеспечить обработку. Тип **значение** может принимать одно из следующих типов:  
  
-   `int`  
  
-   `char`  
  
-   `boolean`  
  
-   `enum`  
  
 или идентификатор такого типа.  
  
## <a name="remarks"></a>Примечания  
 **Случай** языка C++ имеет ту же функциональность, что **случай** языка MIDL. Этот атрибут используется только с [switch_type](../windows/switch-type.md) атрибута.  
  
## <a name="example"></a>Пример  
 В следующем коде показано использование **случай** атрибута:  
  
```  
// cpp_attr_ref_case.cpp  
// compile with: /LD  
#include <unknwn.h>  
[export]  
struct SizedValue2 {  
   [switch_type(char), switch_is(kind)] union {  
      [case(1), string]  
          wchar_t* wval;  
      [default, string]  
          char* val;  
   };  
    char kind;  
};  
[module(name="ATLFIRELib")];  
```  
  
## <a name="requirements"></a>Требования  
  
### <a name="attribute-context"></a>Контекст атрибута  
  
|||  
|-|-|  
|**Применение**|Член **класса** или`struct`|  
|**Повторяемый**|Нет|  
|**Обязательные атрибуты**|Нет|  
|**Недопустимые атрибуты**|Нет|  
  
 Дополнительные сведения о контекстах атрибутов см. в разделе [Контексты атрибутов](../windows/attribute-contexts.md).  
  
## <a name="see-also"></a>См. также  
 [Атрибуты IDL](../windows/idl-attributes.md)   
 [TypeDef, Enum, Union и Struct атрибуты](../windows/typedef-enum-union-and-struct-attributes.md)   
 [Атрибуты классов](../windows/class-attributes.md)   
