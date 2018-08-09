---
title: LCID | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.lcid
dev_langs:
- C++
helpviewer_keywords:
- LCID attribute
ms.assetid: 7f248c69-ee1c-42c3-9411-39cf27c9f43d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 803b4652d4a6482e9e7615121d3a85f0bee309f7
ms.sourcegitcommit: 38af5a1bf35249f0a51e3aafc6e4077859c8f0d9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/09/2018
ms.locfileid: "40013669"
---
# <a name="lcid"></a>lcid
Позволяет передать код языка функции.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
[lcid]  
```  
  
## <a name="remarks"></a>Примечания  
 **Lcid** атрибут C++ реализует функции [lcid](http://msdn.microsoft.com/library/windows/desktop/aa367067) описании атрибута MIDL. Если вы хотите реализовать языкового стандарта для блока библиотеки, используйте **lcid =** `lcid` параметр [модуль](../windows/module-cpp.md) атрибута.  
  
## <a name="example"></a>Пример  
  
```cpp  
// cpp_attr_ref_lcid.cpp  
// compile with: /LD  
#include <unknwn.h>  
[module(name="MyLibrary")];  
typedef long HRESULT;  
  
[dual, uuid("2F5F63F1-16DA-11d2-9E7B-00C04FB926DA")]  
__interface IStatic {  
   HRESULT MyFunc([in, lcid] long LocaleID, [out, retval] BSTR * ReturnVal);  
};  
```  
  
## <a name="requirements"></a>Требования  
  
### <a name="attribute-context"></a>Контекст атрибута  
  
|||  
|-|-|  
|**Применение**|Параметр интерфейса|  
|**Повторяемый**|Нет|  
|**Обязательные атрибуты**|Нет|  
|**Недопустимые атрибуты**|Нет|  
  
 Дополнительные сведения см. в разделе [Контексты атрибутов](../windows/attribute-contexts.md).  
  
## <a name="see-also"></a>См. также  
 [Атрибуты IDL](../windows/idl-attributes.md)   
 [Атрибуты параметра](../windows/parameter-attributes.md)   