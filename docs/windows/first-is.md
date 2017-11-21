---
title: "first_is | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: vc-attr.first_is
dev_langs: C++
helpviewer_keywords: first_is attribute
ms.assetid: 89acbf56-3b38-4d44-83e8-1ce2f6f74ffd
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 478b4f501e16ab9fff2e66a4b36fac6e8d29ac70
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="firstis"></a>first_is
Указывает индекс первого элемента массива для передачи.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
      [ first_is(  
   "expression"  
) ]  
```  
  
#### <a name="parameters"></a>Параметры  
 *выражение*  
 Одно или несколько выражений языка C. Допускаются слоты пустой аргумент.  
  
## <a name="remarks"></a>Примечания  
 **First_is** языка C++ имеет ту же функциональность, что [first_is](http://msdn.microsoft.com/library/windows/desktop/aa366831) языка MIDL.  
  
## <a name="example"></a>Пример  
 В следующем коде показано несколько способов определения раздел в массиве:  
  
```  
// cpp_attr_ref_first_is.cpp  
// compile with: /LD  
#include "windows.h"  
#include "unknwn.h"  
  
[module(name="MyLib")];  
  
[object, uuid(11111111-1111-1111-1111-111111111111)]  
__interface b   
{  
   [id(0), propget, bindable, displaybind, defaultbind,   
requestedit] HRESULT get_I([out, retval]long *i);  
   HRESULT Proc1([in] short First, [in] short Last,   
[first_is(First), last_is(Last), size_is(Last-First)] char Arr1[]);   
   HRESULT Proc2([in] short First, [in] short Last,   
[last_is(First), size_is(Last)] char Arr2[]);  
};  
```  
  
## <a name="requirements"></a>Требования  
  
### <a name="attribute-context"></a>Контекст атрибута  
  
|||  
|-|-|  
|**Применение**|Поле в `struct` или **объединение**, интерфейс параметр, метод|  
|**Повторяемый**|Нет|  
|**Обязательные атрибуты**|Нет|  
|**Недопустимые атрибуты**|Нет|  
  
 Дополнительные сведения см. в разделе [Контексты атрибутов](../windows/attribute-contexts.md).  
  
## <a name="see-also"></a>См. также  
 [Атрибуты IDL](../windows/idl-attributes.md)   
 [TypeDef, Enum, Union и Struct атрибуты](../windows/typedef-enum-union-and-struct-attributes.md)   
 [Атрибуты параметра](../windows/parameter-attributes.md)   
 [last_is](../windows/last-is.md)   
 [max_is](../windows/max-is.md)   
 [length_is](../windows/length-is.md)   
 [size_is](../windows/size-is.md)   
