---
title: "версия (C++) | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: vc-attr.version
dev_langs: C++
helpviewer_keywords:
- version attribute
- version information, version attribute
ms.assetid: db6ce5d8-82c2-4329-b1a8-8ca2f67342cb
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 757ab7a6d2c8b846a51da359c4b8dc5a72c6e9e8
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
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
