---
title: "HelpString | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: vc-attr.helpstring
dev_langs: C++
helpviewer_keywords: helpstring attribute [C++]
ms.assetid: 0401e905-a63e-4fad-98d0-d1efea111966
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 27cf95f5017775fbf7a0315341cea19931f64068
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="helpstring"></a>helpstring
Определяет строку символов, используемый для описания элемента, к которому он применяется.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
      [ helpstring(  
   "string"  
) ]  
```  
  
#### <a name="parameters"></a>Параметры  
 `string`  
 Текст справки строки.  
  
## <a name="remarks"></a>Примечания  
 **Helpstring** языка C++ имеет ту же функциональность, что [helpstring](http://msdn.microsoft.com/library/windows/desktop/aa366856) языка MIDL.  
  
## <a name="example"></a>Пример  
 Далее приведен пример [defaultvalue](../windows/defaultvalue.md) пример демонстрирует использование **helpstring**.  
  
## <a name="requirements"></a>Требования  
  
### <a name="attribute-context"></a>Контекст атрибута  
  
|||  
|-|-|  
|**Применение**|`interface`, `typedef`, **класса**, метод, свойство|  
|**Повторяемый**|Нет|  
|**Обязательные атрибуты**|Нет|  
|**Недопустимые атрибуты**|Нет|  
  
 Дополнительные сведения см. в разделе [Контексты атрибутов](../windows/attribute-contexts.md).  
  
## <a name="see-also"></a>См. также  
 [Атрибуты IDL](../windows/idl-attributes.md)   
 [Атрибуты интерфейса](../windows/interface-attributes.md)   
 [Атрибуты классов](../windows/class-attributes.md)   
 [Атрибуты метода](../windows/method-attributes.md)   
 [TypeDef, Enum, Union и Struct атрибуты](../windows/typedef-enum-union-and-struct-attributes.md)   
 [файл справки](../windows/helpfile.md)   
 [helpcontext](../windows/helpcontext.md)   
