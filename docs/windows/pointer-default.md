---
title: pointer_default | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.pointer_default
dev_langs:
- C++
helpviewer_keywords:
- pointer_default attribute
ms.assetid: 2d0c7bbc-a1e8-4337-9e54-e304523e2735
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 562bc3ebd0c80423eb94d2bc328f72aed8e67985
ms.sourcegitcommit: 4586bfc32d8bc37ab08b24816d7fad5df709bfa3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/07/2018
ms.locfileid: "39604392"
---
# <a name="pointerdefault"></a>pointer_default
Указывает атрибут указатель по умолчанию для всех указателей, за исключением верхнего уровня указателей, которые отображаются в списках параметров.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
[ pointer_default(  
   value  
) ]  
```  
  
#### <a name="parameters"></a>Параметры  
 *значение*  
 Значение, описывающее тип указателя: **ptr**, **ref**, или **уникальный**.  
  
## <a name="remarks"></a>Примечания  
 **Pointer_default** атрибут C++ имеет ту же функциональность, что [pointer_default](http://msdn.microsoft.com/library/windows/desktop/aa367141) описании атрибута MIDL.  
  
## <a name="example"></a>Пример  
 См. в примере [defaultvalue](../windows/defaultvalue.md) использовать образец **pointer_default**.  
  
## <a name="requirements"></a>Требования  
  
### <a name="attribute-context"></a>Контекст атрибута  
  
|||  
|-|-|  
|**Применение**|**interface**|  
|**Повторяемый**|Нет|  
|**Обязательные атрибуты**|Нет|  
|**Недопустимые атрибуты**|Нет|  
  
 Дополнительные сведения о контекстах атрибутов см. в разделе [Контексты атрибутов](../windows/attribute-contexts.md).  
  
## <a name="see-also"></a>См. также  
 [Атрибуты IDL](../windows/idl-attributes.md)   
 [Атрибуты интерфейса](../windows/interface-attributes.md)   