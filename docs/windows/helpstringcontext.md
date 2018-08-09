---
title: helpstringcontext | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.helpstringcontext
dev_langs:
- C++
helpviewer_keywords:
- helpstringcontext attribute [C++]
ms.assetid: d4cd135e-d91c-4aa3-9353-8aeb096f52cf
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: b71d8183921e0df66d6b9a82ff79faf24ccb41d3
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/08/2018
ms.locfileid: "39642338"
---
# <a name="helpstringcontext"></a>helpstringcontext
Указывает идентификатор раздела справки в файл с расширением .hlp или .chm.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
[ helpstringcontext(  
   contextID  
) ]  
```  
  
### <a name="parameters"></a>Параметры  
 *contextID*  
 В 32-разрядный идентификатор контекста справки в **помочь** файл.  
  
## <a name="remarks"></a>Примечания  
 **Helpstringcontext** атрибут C++ имеет ту же функциональность, что [helpstringcontext](http://msdn.microsoft.com/library/windows/desktop/aa366858) ODL-атрибут.  
  
## <a name="example"></a>Пример  
  
```cpp  
// cpp_attr_ref_helpstringcontext.cpp  
// compile with: /LD  
#include <unknwn.h>  
[module(name="MyLib")];  
  
[   object,   
   helpstring("help string"),   
   helpstringcontext(1),   
   uuid="11111111-1111-1111-1111-111111111111"  
]  
__interface IMyI   
{  
   HRESULT xx();  
};  
```  
  
## <a name="requirements"></a>Требования  
  
### <a name="attribute-context"></a>Контекст атрибута  
  
|||  
|-|-|  
|**Применение**|**Класс**, **интерфейс**, метод интерфейса|  
|**Повторяемый**|Нет|  
|**Обязательные атрибуты**|Нет|  
|**Недопустимые атрибуты**|Нет|  
  
 Дополнительные сведения см. в разделе [Контексты атрибутов](../windows/attribute-contexts.md).  
  
## <a name="see-also"></a>См. также  
 [Атрибуты IDL](../windows/idl-attributes.md)   
 [Атрибуты интерфейса](../windows/interface-attributes.md)   
 [Атрибуты классов](../windows/class-attributes.md)   
 [Атрибуты метода](../windows/method-attributes.md)   
 [модуль](../windows/module-cpp.md)   