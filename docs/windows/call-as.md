---
title: call_as | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.call_as
dev_langs:
- C++
helpviewer_keywords:
- call_as attribute
ms.assetid: a09d7f1f-353b-4870-9b45-f0284161695d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 68707ea7e00665d12165c7838b1a2ad3440f944d
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2018
---
# <a name="callas"></a>call_as
Включает [локального](../windows/local-cpp.md) функции для сопоставления удаленной функции так, что при вызове удаленной функции локальной функции.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
      [ call_as(  
   function  
) ]  
```  
  
#### <a name="parameters"></a>Параметры  
 *function*  
 Локальная функция, которую требуется вызывать при вызове удаленной функции.  
  
## <a name="remarks"></a>Примечания  
 **Call_as** языка C++ имеет ту же функциональность, что [call_as](http://msdn.microsoft.com/library/windows/desktop/aa366748) языка MIDL.  
  
## <a name="example"></a>Пример  
 В следующем коде показано, как использовать **call_as** сопоставляется функции не поддерживающие удаленное взаимодействие (**f1**) функции удаленного взаимодействия (**Remf1**):  
  
```  
// cpp_attr_ref_call_as.cpp  
// compile with: /LD  
#include "unknwn.h"  
[module(name="MyLib")];  
[dual, uuid("00000000-0000-0000-0000-000000000001")]  
__interface IMInterface {  
   [local] HRESULT f1 ( int i );  
   [call_as(f1)] HRESULT Remf1 ( int i );   
};  
```  
  
## <a name="requirements"></a>Требования  
  
### <a name="attribute-context"></a>Контекст атрибута  
  
|||  
|-|-|  
|**Применение**|Метод интерфейса|  
|**Повторяемый**|Нет|  
|**Обязательные атрибуты**|Нет|  
|**Недопустимые атрибуты**|Нет|  
  
 Дополнительные сведения о контекстах атрибутов см. в разделе [Контексты атрибутов](../windows/attribute-contexts.md).  
  
## <a name="see-also"></a>См. также  
 [Атрибуты IDL](../windows/idl-attributes.md)   
 [Атрибуты метода](../windows/method-attributes.md)   
 [Локальные](../windows/local-cpp.md)   
