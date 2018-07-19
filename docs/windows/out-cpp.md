---
title: out (C++) | Документы Microsoft
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
ms.openlocfilehash: b23ff91a67962ec36cf6a9c2f5ebbf8122ab73c1
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2018
ms.locfileid: "33876817"
---
# <a name="out-c"></a>out (C++)
Определяет параметры-указатели, которые возвращаются из вызываемой процедуры в вызывающую (от сервера к клиенту).  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
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
 [значение по умолчанию](../windows/defaultvalue.md)   
 [id](../windows/id.md)   
