---
title: в (C++) | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.in
dev_langs:
- C++
helpviewer_keywords:
- in attribute
ms.assetid: 7b450cc4-4d2e-4910-a195-7487c6b7c373
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 8522b3af527267706a2e2697b88049a38b0f092f
ms.sourcegitcommit: 38af5a1bf35249f0a51e3aafc6e4077859c8f0d9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/09/2018
ms.locfileid: "40017195"
---
# <a name="in-c"></a>in (C++)
Указывает, что параметр передается из вызывающей процедуры вызываемой процедуры.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
[in]  
```  
  
## <a name="remarks"></a>Примечания  
 **В** атрибут C++ имеет ту же функциональность, что [в](http://msdn.microsoft.com/library/windows/desktop/aa367051) описании атрибута MIDL.  
  
## <a name="example"></a>Пример  
 См. в разделе [bindable](../windows/bindable.md) пример демонстрирует использование **в**.  
  
## <a name="requirements"></a>Требования  
  
### <a name="attribute-context"></a>Контекст атрибута  
  
|||  
|-|-|  
|**Применение**|Параметр интерфейса, метод интерфейса|  
|**Повторяемый**|Нет|  
|**Обязательные атрибуты**|Нет|  
|**Недопустимые атрибуты**|**retval**|  
  
 Дополнительные сведения о контекстах атрибутов см. в разделе [Контексты атрибутов](../windows/attribute-contexts.md).  
  
## <a name="see-also"></a>См. также  
 [Атрибуты IDL](../windows/idl-attributes.md)   
 [Атрибуты параметра](../windows/parameter-attributes.md)   
 [Атрибуты метода](../windows/method-attributes.md)   
 [DefaultValue](../windows/defaultvalue.md)   
 [Идентификатор](../windows/id.md)   
 [out](../windows/out-cpp.md)   