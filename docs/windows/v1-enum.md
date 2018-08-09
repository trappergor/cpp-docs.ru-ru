---
title: v1_enum | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.v1_enum
dev_langs:
- C++
helpviewer_keywords:
- v1_enum attribute
ms.assetid: 2fe92d92-81b9-4a1c-b6ce-437d0eb770ca
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: b057ef891a00829fd64d967ffa860a66d6d49d5d
ms.sourcegitcommit: 38af5a1bf35249f0a51e3aafc6e4077859c8f0d9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/09/2018
ms.locfileid: "40012346"
---
# <a name="v1enum"></a>v1_enum
Указывает, что заданного перечислимого типа, передаваться в объект 32-разрядной, а не по умолчанию 16-разрядное.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
[v1_enum]  
```  
  
## <a name="remarks"></a>Примечания  
 **V1_enum** атрибут C++ имеет ту же функциональность, что [v1_enum](http://msdn.microsoft.com/library/windows/desktop/aa367303) описании атрибута MIDL.  
  
## <a name="example"></a>Пример  
 В следующем коде показано использование **v1_enum**:  
  
```cpp  
// cpp_attr_ref_v1_enum.cpp  
// compile with: /LD  
[module(name="MyLibrary")];  
  
[export, v1_enum]   
enum eList {   
   e1 = 1,   
   e2 = 2  
};  
```  
  
## <a name="requirements"></a>Требования  
  
### <a name="attribute-context"></a>Контекст атрибута  
  
|||  
|-|-|  
|**Применение**|Перечислимый тип|  
|**Повторяемый**|Нет|  
|**Обязательные атрибуты**|Нет|  
|**Недопустимые атрибуты**|Нет|  
  
 Дополнительные сведения о контекстах атрибутов см. в разделе [Контексты атрибутов](../windows/attribute-contexts.md).  
  
## <a name="see-also"></a>См. также  
 [Атрибуты IDL](../windows/idl-attributes.md)   
 [Атрибуты Typedef, Enum, Union и Struct](../windows/typedef-enum-union-and-struct-attributes.md)   