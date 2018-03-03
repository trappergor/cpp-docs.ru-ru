---
title: "Custom (C++) | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- vc-attr.custom
dev_langs:
- C++
helpviewer_keywords:
- custom attributes, defining
ms.assetid: 3abac928-4d55-4ea6-8cf6-8427a4ad79f1
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: e55fd4ad47470a86a0a3d61cc847c20fb21768e8
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
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
 *UUID*  
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
