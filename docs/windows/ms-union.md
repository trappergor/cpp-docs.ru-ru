---
title: "ms_union | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: vc-attr.ms_union
dev_langs: C++
helpviewer_keywords: ms_union attribute
ms.assetid: bb548689-6962-457e-af56-8ffdf68987eb
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: f70f4403c3318729ae0dcf42e717902c48c8759b
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="msunion"></a>ms_union
Управляет выравниванием представление данных сети nonencapsulated объединений.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
[ms_union]  
  
```  
  
## <a name="remarks"></a>Примечания  
 **Ms_union** языка C++ имеет ту же функциональность, что [ms_union](http://msdn.microsoft.com/library/windows/desktop/aa367100) языка MIDL.  
  
## <a name="example"></a>Пример  
 В следующем коде показано размещение **ms_union**:  
  
```  
// cpp_attr_ref_ms_union.cpp  
// compile with: /LD  
#include <unknwn.h>  
[object, ms_union, uuid("00000000-0000-0000-0000-000000000001")]  
__interface IFireTabCtrl {  
   HRESULT DisplayString([in, string] char * p1);  
};  
  
[export, switch_type(short)] union _WILLIE_UNION_TYPE  {  
   [case(24)]  
      float fMays;  
   [case(25)]  
      double dMcCovey;  
   [default]  
      int x;  
 };  
  
[public] typedef _WILLIE_UNION_TYPE WILLIE_UNION_TYPE;  
  
[module(name="ATLFIRELib")];  
```  
  
## <a name="requirements"></a>Требования  
  
### <a name="attribute-context"></a>Контекст атрибута  
  
|||  
|-|-|  
|**Применение**|Nonencapsulated объединения|  
|**Повторяемый**|Нет|  
|**Обязательные атрибуты**|Нет|  
|**Недопустимые атрибуты**|**dispinterface**|  
  
 Дополнительные сведения см. в разделе [Контексты атрибутов](../windows/attribute-contexts.md).  
  
## <a name="see-also"></a>См. также  
 [Атрибуты IDL](../windows/idl-attributes.md)   
 [Атрибуты Typedef, Enum, Union и Struct](../windows/typedef-enum-union-and-struct-attributes.md)   
