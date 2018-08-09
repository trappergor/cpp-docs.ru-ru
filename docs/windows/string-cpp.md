---
title: строка (C++) | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.string
dev_langs:
- C++
helpviewer_keywords:
- string attribute
ms.assetid: ddde900a-2e99-4fcd-86e8-57e1bdba7c93
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 459f786863f7d10797008b87e276afb0c95e184a
ms.sourcegitcommit: 38af5a1bf35249f0a51e3aafc6e4077859c8f0d9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/09/2018
ms.locfileid: "40020090"
---
# <a name="string-c"></a>string (C++)
Указывает, что одномерный массив **char**, **wchar_t**, `byte` (или эквивалентную) массив или указатель на такой массив должен обрабатываться как строка.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
[string]  
```  
  
## <a name="remarks"></a>Примечания  
 **Строка** атрибут C++ имеет ту же функциональность, что [строка](http://msdn.microsoft.com/library/windows/desktop/aa367270) описании атрибута MIDL.  
  
## <a name="example"></a>Пример  
 Ниже показано, как использовать **строка** в интерфейсе, а также на определение типа:  
  
```cpp  
// cpp_attr_ref_string.cpp  
// compile with: /LD  
#include "unknwn.h"  
[module(name="ATLFIRELib")];  
[export, string] typedef char a[21];  
[dispinterface, restricted, uuid("00000000-0000-0000-0000-000000000001")]  
__interface IFireTabCtrl  
{  
   [id(1)] HRESULT Method3([in, string] char *pC);  
};  
```  
  
## <a name="requirements"></a>Требования  
  
### <a name="attribute-context"></a>Контекст атрибута  
  
|||  
|-|-|  
|**Применение**|Массив или указатель на массив, параметр интерфейса, метод интерфейса|  
|**Повторяемый**|Нет|  
|**Обязательные атрибуты**|Нет|  
|**Недопустимые атрибуты**|Нет|  
  
 Дополнительные сведения о контекстах атрибутов см. в разделе [Контексты атрибутов](../windows/attribute-contexts.md).  
  
## <a name="see-also"></a>См. также  
 [Атрибуты IDL](../windows/idl-attributes.md)   
 [Атрибуты массивов](../windows/array-attributes.md)   
 [export](../windows/export.md)   