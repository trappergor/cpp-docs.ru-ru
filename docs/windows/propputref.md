---
title: propputref | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.propputref
dev_langs:
- C++
helpviewer_keywords:
- propputref attribute
ms.assetid: 9b0aed74-fdc7-4e59-9117-949bea4f86dd
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: fc11561401ff34b629fecdc31a00ffb845d6a2d8
ms.sourcegitcommit: 4586bfc32d8bc37ab08b24816d7fad5df709bfa3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/07/2018
ms.locfileid: "39606804"
---
# <a name="propputref"></a>propputref
Задает функцию настройки свойства, которая использует ссылку вместо значения.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
[propputref]  
```  
  
## <a name="remarks"></a>Примечания  
 **Propputref** атрибут C++ имеет ту же функциональность, что [propputref](http://msdn.microsoft.com/library/windows/desktop/aa367147) описании атрибута MIDL.  
  
## <a name="example"></a>Пример  
 См. в примере [bindable](../windows/bindable.md) использовать образец **propputref**.  
  
## <a name="requirements"></a>Требования  
  
### <a name="attribute-context"></a>Контекст атрибута  
  
|||  
|-|-|  
|**Применение**|Метод|  
|**Повторяемый**|Нет|  
|**Обязательные атрибуты**|Нет|  
|**Недопустимые атрибуты**|`propget`, `propput`|  
  
 Дополнительные сведения о контекстах атрибутов см. в разделе [Контексты атрибутов](../windows/attribute-contexts.md).  
  
## <a name="see-also"></a>См. также  
 [Атрибуты IDL](../windows/idl-attributes.md)   
 [Атрибуты метода](../windows/method-attributes.md)   
 [propget](../windows/propget.md)   
 [propput](../windows/propput.md)   