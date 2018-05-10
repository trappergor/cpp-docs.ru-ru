---
title: объект (C++) | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.object
dev_langs:
- C++
helpviewer_keywords:
- object attribute
ms.assetid: f2d3c231-630d-4b4c-bd15-b1c30df362dd
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 601d67fb48f0ae826474d33e7dca0fbffff9478c
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2018
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
 [Два двухъядерных](../windows/dual.md)   
 [Disp-интерфейс](../windows/dispinterface.md)   
 [Настройка](../windows/custom-cpp.md)   
 [__interface](../cpp/interface.md)   
