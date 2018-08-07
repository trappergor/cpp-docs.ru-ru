---
title: retval | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.retval
dev_langs:
- C++
helpviewer_keywords:
- retval attribute
ms.assetid: bfa16f08-157d-4eea-afde-1232c54b8501
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: d6f17f44e520018f82dc82abe88427a2410d68e7
ms.sourcegitcommit: 4586bfc32d8bc37ab08b24816d7fad5df709bfa3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/07/2018
ms.locfileid: "39606355"
---
# <a name="retval"></a>retval
Назначает параметр, который получает возвращаемое значение члена.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
[retval]  
```  
  
## <a name="remarks"></a>Примечания  
 **Retval** атрибут C++ имеет ту же функциональность, что [retval](http://msdn.microsoft.com/library/windows/desktop/aa367158) описании атрибута MIDL.  
  
 **retval** должны располагаться на последний аргумент в объявлении функции.  
  
## <a name="example"></a>Пример  
 См. в примере [bindable](../windows/bindable.md) использовать образец **retval**.  
  
## <a name="requirements"></a>Требования  
  
### <a name="attribute-context"></a>Контекст атрибута  
  
|||  
|-|-|  
|**Применение**|Параметр интерфейса, метод интерфейса|  
|**Повторяемый**|Нет|  
|**Обязательные атрибуты**|**out**|  
|**Недопустимые атрибуты**|**in**|  
  
 Дополнительные сведения о контекстах атрибутов см. в разделе [Контексты атрибутов](../windows/attribute-contexts.md).  
  
## <a name="see-also"></a>См. также  
 [Атрибуты IDL](../windows/idl-attributes.md)   
 [Атрибуты параметра](../windows/parameter-attributes.md)   
 [Атрибуты метода](../windows/method-attributes.md)   