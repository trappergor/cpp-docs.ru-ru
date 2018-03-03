---
title: "объект (C++) | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- vc-attr.object
dev_langs:
- C++
helpviewer_keywords:
- object attribute
ms.assetid: f2d3c231-630d-4b4c-bd15-b1c30df362dd
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 5714d7c3bd029c7b1df636044ed1968f53600848
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="object-c"></a>object (C++)
Определяет пользовательский интерфейс.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
[object]  
  
```  
  
## <a name="remarks"></a>Примечания  
 Если предшествующие определение интерфейса **объекта** языка C++ вызывает интерфейс помещается в IDL-файл как пользовательский интерфейс.  
  
 Любой интерфейс, отмеченный атрибутом объект должен наследовать от **IUnknown**. Это условие выполнено, если любой из этих базовых интерфейсов наследуют от **IUnknown**. Если базовые интерфейсы не наследуют от **IUnknown**, компилятор вызывает интерфейс, отмеченный атрибутом **объекта** для наследования от **IUnknown**.  
  
## <a name="example"></a>Пример  
 В разделе [nonbrowsable](../windows/nonbrowsable.md) пример демонстрирует использование **объекта**.  
  
## <a name="requirements"></a>Требования  
  
### <a name="attribute-context"></a>Контекст атрибута  
  
|||  
|-|-|  
|**Применение**|`interface`|  
|**Повторяемый**|Нет|  
|**Обязательные атрибуты**|Нет|  
|**Недопустимые атрибуты**|Нет|  
  
 Дополнительные сведения о контекстах атрибутов см. в разделе [Контексты атрибутов](../windows/attribute-contexts.md).  
  
## <a name="see-also"></a>См. также  
 [Атрибуты IDL](../windows/idl-attributes.md)   
 [Атрибуты интерфейса](../windows/interface-attributes.md)   
 [Двойная](../windows/dual.md)   
 [disp-интерфейс](../windows/dispinterface.md)   
 [пользовательские](../windows/custom-cpp.md)   
 [__interface](../cpp/interface.md)   
