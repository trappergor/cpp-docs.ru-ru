---
title: Custom (C++) | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.custom
dev_langs:
- C++
helpviewer_keywords:
- custom attributes, defining
ms.assetid: 3abac928-4d55-4ea6-8cf6-8427a4ad79f1
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 7b37d87d5380b9d4dac69cee702654285461ead6
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2018
ms.locfileid: "33871631"
---
# <a name="custom-c"></a>custom (C++)
Определяет метаданные для объекта в библиотеке типов.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
      [ custom(  
   uuid,   
   value  
) ];  
```  
  
#### <a name="parameters"></a>Параметры  
 *uuid*  
 Уникальный идентификатор.  
  
 *значение*  
 Значение, которое можно поместить в тип variant.  
  
## <a name="remarks"></a>Примечания  
 **Пользовательские** атрибута C++ приведет к информации, должен быть помещен в библиотеку типов. Вам потребуется средство, которое считывает пользовательское значение из библиотеки типов.  
  
 **Пользовательские** атрибут имеет ту же функциональность, что [пользовательские](http://msdn.microsoft.com/library/windows/desktop/aa366766) языка MIDL.  
  
## <a name="requirements"></a>Требования  
  
### <a name="attribute-context"></a>Контекст атрибута  
  
|||  
|-|-|  
|**Применение**|COM не `interface`, **класса**, `enum`s, `idl_module` методов, члены интерфейса, параметры интерфейса `typedef`s, **объединение**s, `struct`s|  
|**Повторяемый**|Да|  
|**Обязательные атрибуты**|**Компонентный класс** (при использовании класса)|  
|**Недопустимые атрибуты**|Нет|  
  
 Дополнительные сведения о контекстах атрибутов см. в разделе [Контексты атрибутов](../windows/attribute-contexts.md).  
  
## <a name="see-also"></a>См. также  
 [Атрибуты IDL](../windows/idl-attributes.md)   
 [Изолированные атрибуты](../windows/stand-alone-attributes.md)   
 [TypeDef, Enum, Union и Struct атрибуты](../windows/typedef-enum-union-and-struct-attributes.md)   
 [Атрибуты параметра](../windows/parameter-attributes.md)   
 [Атрибуты метода](../windows/method-attributes.md)   
 [Атрибуты классов](../windows/class-attributes.md)   
 [Атрибуты интерфейса](../windows/interface-attributes.md)   
