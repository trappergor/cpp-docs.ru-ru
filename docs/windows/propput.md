---
title: propput | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.propput
dev_langs:
- C++
helpviewer_keywords:
- propput attribute
ms.assetid: 1f84dda9-9cce-4e16-aaf0-b2c5219827f2
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 679b019c15d72586b5ca186e0b54c9a9172db53a
ms.sourcegitcommit: 4586bfc32d8bc37ab08b24816d7fad5df709bfa3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/07/2018
ms.locfileid: "39608460"
---
# <a name="propput"></a>propput
Задает функцию настройки свойства.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
[propput]  
```  
  
## <a name="remarks"></a>Примечания  
 **Propput** атрибут C++ имеет ту же функциональность, что [propput](http://msdn.microsoft.com/library/windows/desktop/aa367146) описании атрибута MIDL.  
  
## <a name="example"></a>Пример  
 См. в примере [bindable](../windows/bindable.md) использовать образец **propput**.  
  
## <a name="requirements"></a>Требования  
  
### <a name="attribute-context"></a>Контекст атрибута  
  
|||  
|-|-|  
|**Применение**|Метод|  
|**Повторяемый**|Нет|  
|**Обязательные атрибуты**|Нет|  
|**Недопустимые атрибуты**|`propget`, `propputref`|  
  
 Дополнительные сведения о контекстах атрибутов см. в разделе [Контексты атрибутов](../windows/attribute-contexts.md).  
  
## <a name="see-also"></a>См. также  
 [Атрибуты IDL](../windows/idl-attributes.md)   
 [Атрибуты метода](../windows/method-attributes.md)   
 [propget](../windows/propget.md)   
 [propputref](../windows/propputref.md)