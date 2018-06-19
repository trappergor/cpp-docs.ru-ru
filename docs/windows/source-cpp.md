---
title: источник (C++) | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.source
dev_langs:
- C++
helpviewer_keywords:
- source attribute
ms.assetid: 1878d05d-7709-4e97-b114-c62f38f5140e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 11ee58fb2d500a7194fb08ee18b1af5cc7897830
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2018
ms.locfileid: "33889866"
---
# <a name="source-c"></a>source (C++)
В классе задает исходных интерфейсов COM-объект для точки подключения. Для свойства или метода означает, что член возвращает объект или ВАРИАНТ, который является источником событий.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
      [ source(  
   interfaces  
) ]  
```  
  
#### <a name="parameters"></a>Параметры  
 `interfaces`  
 Один или несколько интерфейсов, укажите при применении исходного атрибута к классу. Этот параметр не используется при применении исходного свойства или метода.  
  
## <a name="remarks"></a>Примечания  
 **Источника** языка C++ имеет ту же функциональность, что [источника](http://msdn.microsoft.com/library/windows/desktop/aa367166) языка MIDL.  
  
 Можно использовать [по умолчанию](../windows/default-cpp.md) атрибут, чтобы задать исходный интерфейс по умолчанию для объекта.  
  
## <a name="example"></a>Пример  
  
```  
// cpp_attr_ref_source.cpp  
// compile with: /LD  
#include "windows.h"  
#include "unknwn.h"  
[module(name="MyLib")];  
  
[object, uuid(11111111-1111-1111-1111-111111111111)]  
__interface b  
{  
   [id(0), propget, bindable, displaybind, defaultbind, requestedit]  
   HRESULT get_I([out, retval]long *i);  
};  
  
[object, uuid(11111111-1111-1111-1111-111111111131)]  
__interface c  
{  
   [id(0), propget, bindable, displaybind, defaultbind, requestedit]   
   HRESULT et_I([out, retval]long *i);  
};  
  
[coclass, default(c), uuid(11111111-1111-1111-1111-111111111132)]  
class N : public b  
{  
};  
  
[coclass, source(c), default(b, c), uuid(11111111-1111-1111-1111-111111111133)]  
class NN : public b  
{  
};  
```  
  
## <a name="requirements"></a>Требования  
  
### <a name="attribute-context"></a>Контекст атрибута  
  
|||  
|-|-|  
|**Применение**|**Класс**, `struct`, `interface`|  
|**Повторяемый**|Нет|  
|**Обязательные атрибуты**|**Компонентный класс** (при применении класс или структура)|  
|**Недопустимые атрибуты**|Нет|  
  
 Дополнительные сведения о контекстах атрибутов см. в разделе [Контексты атрибутов](../windows/attribute-contexts.md).  
  
## <a name="see-also"></a>См. также  
 [Атрибуты IDL](../windows/idl-attributes.md)   
 [Атрибуты классов](../windows/class-attributes.md)   
 [Атрибуты метода](../windows/method-attributes.md)   
 [coclass](../windows/coclass.md)   
