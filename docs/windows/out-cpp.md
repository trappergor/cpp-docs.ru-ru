---
title: out (C++) | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.out
dev_langs:
- C++
helpviewer_keywords:
- out attribute
ms.assetid: 5051b1bf-4949-4bf1-b82f-35e14f0f244b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: f83314de19548c93afa43feced8b2a877af00738
ms.sourcegitcommit: 38af5a1bf35249f0a51e3aafc6e4077859c8f0d9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/09/2018
ms.locfileid: "40019057"
---
# <a name="out-c"></a>out (C++)
Определяет параметры-указатели, которые возвращаются из вызываемой процедуры в вызывающую (от сервера к клиенту).  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
[out]  
```  
  
## <a name="remarks"></a>Примечания  
 Атрибут **out** языка C++ имеет ту же функциональность, как и атрибут [out](http://msdn.microsoft.com/library/windows/desktop/aa367136) языка MIDL.  
  
## <a name="example"></a>Пример  
 Просмотрите пример с [bindable](../windows/bindable.md) , чтобы увидеть, как можно использовать **out**.  
  
## <a name="requirements"></a>Требования  
  
### <a name="attribute-context"></a>Контекст атрибута  
  
|||  
|-|-|  
|**Применение**|Параметр интерфейса|  
|**Повторяемый**|Нет|  
|**Обязательные атрибуты**|Нет|  
|**Недопустимые атрибуты**|Нет|  
  
 Дополнительные сведения о контекстах атрибутов см. в разделе [Контексты атрибутов](../windows/attribute-contexts.md).  
  
## <a name="see-also"></a>См. также  
 [Атрибуты IDL](../windows/idl-attributes.md)   
 [Атрибуты параметра](../windows/parameter-attributes.md)   
 [DefaultValue](../windows/defaultvalue.md)   
 [id](../windows/id.md)   