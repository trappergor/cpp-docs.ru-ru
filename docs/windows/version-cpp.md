---
title: версия (C++) | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.version
dev_langs:
- C++
helpviewer_keywords:
- version attribute
- version information, version attribute
ms.assetid: db6ce5d8-82c2-4329-b1a8-8ca2f67342cb
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 43da63d75d3541915eba3e561ee08fe1048fa579
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2018
---
# <a name="version-c"></a>version (C++)
Определяет конкретную версию несколькими версиями класса.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
      [ version(  
   "version"  
) ]  
```  
  
#### <a name="parameters"></a>Параметры  
 *version*  
 Номер версии компонентного класса. Если не указан, 1.0 помещается в IDL-файл.  
  
## <a name="remarks"></a>Примечания  
 **Версии** языка C++ имеет ту же функциональность, что [версии](http://msdn.microsoft.com/library/windows/desktop/aa367306) языка MIDL и передается через созданного IDL-файла.  
  
## <a name="example"></a>Пример  
 В разделе [привязываемых](../windows/bindable.md) пример приведен пример использования **версии**.  
  
## <a name="requirements"></a>Требования  
  
### <a name="attribute-context"></a>Контекст атрибута  
  
|||  
|-|-|  
|**Применение**|**class**, `struct`|  
|**Повторяемый**|Нет|  
|**Обязательные атрибуты**|**coclass**|  
|**Недопустимые атрибуты**|Нет|  
  
 Дополнительные сведения о контекстах атрибутов см. в разделе [Контексты атрибутов](../windows/attribute-contexts.md).  
  
## <a name="see-also"></a>См. также  
 [Атрибуты компилятора](../windows/compiler-attributes.md)   
 [Атрибуты классов](../windows/class-attributes.md)   
