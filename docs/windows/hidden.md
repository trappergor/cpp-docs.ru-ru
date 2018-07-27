---
title: скрытые | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.hidden
dev_langs:
- C++
helpviewer_keywords:
- hidden attribute
ms.assetid: 199c96dd-fc07-46c7-af93-92020aebebe7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 444994f046b58fbd54dcd3982836bb7fc4d53ed1
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2018
ms.locfileid: "33879689"
---
# <a name="hidden"></a>hidden
Указывает, что элемент существует, но не должен отображаться в пользовательском браузере.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
[hidden]  
  
```  
  
## <a name="remarks"></a>Примечания  
 **Скрытые** языка C++ имеет ту же функциональность, что [скрытые](http://msdn.microsoft.com/library/windows/desktop/aa366861) языка MIDL.  
  
## <a name="example"></a>Пример  
 Далее приведен пример [привязываемых](../windows/bindable.md) пример демонстрирует использование **скрытые**.  
  
## <a name="requirements"></a>Требования  
  
### <a name="attribute-context"></a>Контекст атрибута  
  
|||  
|-|-|  
|**Применение**|`interface`, **класса**, `struct`, метод, свойство|  
|**Повторяемый**|Нет|  
|**Обязательные атрибуты**|**кокласс** (при применении к **классу** или `struct`)|  
|**Недопустимые атрибуты**|Нет|  
  
 Дополнительные сведения см. в разделе [Контексты атрибутов](../windows/attribute-contexts.md).  
  
## <a name="see-also"></a>См. также  
 [Атрибуты IDL](../windows/idl-attributes.md)   
 [Атрибуты интерфейса](../windows/interface-attributes.md)   
 [Атрибуты классов](../windows/class-attributes.md)   
 [Атрибуты метода](../windows/method-attributes.md)   
