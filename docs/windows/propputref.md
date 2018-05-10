---
title: propputref | Документы Microsoft
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
ms.openlocfilehash: 3ac9784e450746a4474879aae346a4242bbe2fd2
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2018
---
# <a name="propputref"></a>propputref
Задает функцию настройки свойства, которое использует ссылку вместо значения.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
[propputref]  
  
```  
  
## <a name="remarks"></a>Примечания  
 **Propputref** языка C++ имеет ту же функциональность, что [propputref](http://msdn.microsoft.com/library/windows/desktop/aa367147) языка MIDL.  
  
## <a name="example"></a>Пример  
 Далее приведен пример [привязываемых](../windows/bindable.md) для приведен пример использования **propputref**.  
  
## <a name="requirements"></a>Требования  
  
### <a name="attribute-context"></a>Контекст атрибута  
  
|||  
|-|-|  
|**Применение**|Метод|  
|**Повторяемый**|Нет|  
|**Обязательные атрибуты**|Нет|  
|**Недопустимые атрибуты**|**propget**, **propput**|  
  
 Дополнительные сведения о контекстах атрибутов см. в разделе [Контексты атрибутов](../windows/attribute-contexts.md).  
  
## <a name="see-also"></a>См. также  
 [Атрибуты IDL](../windows/idl-attributes.md)   
 [Атрибуты метода](../windows/method-attributes.md)   
 [propget](../windows/propget.md)   
 [propput](../windows/propput.md)   
