---
title: локальный (C++) | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.local
dev_langs:
- C++
helpviewer_keywords:
- local attribute
ms.assetid: 35cdd668-bd8e-492a-b7b8-263e7b662437
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 17a57ad56402b345aa64e4e4fd02bc57dd7f0321
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2018
---
# <a name="local-c"></a>local (C++)
При использовании в заголовке интерфейс позволяет использовать компилятор MIDL как генератор заголовок. При использовании в отдельную функцию, назначает локальной процедуры, для которого заглушки не создаются.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
[local]  
  
```  
  
## <a name="remarks"></a>Примечания  
 `local` Языка C++ имеет ту же функциональность, что [локального](http://msdn.microsoft.com/library/windows/desktop/aa367071) языка MIDL.  
  
## <a name="example"></a>Пример  
 В разделе [call_as](../windows/call-as.md) пример демонстрирует использование `local`.  
  
## <a name="requirements"></a>Требования  
  
### <a name="attribute-context"></a>Контекст атрибута  
  
|||  
|-|-|  
|**Применение**|`interface`, метод|  
|**Повторяемый**|Нет|  
|**Обязательные атрибуты**|Нет|  
|**Недопустимые атрибуты**|**dispinterface**|  
  
 Дополнительные сведения см. в разделе [Контексты атрибутов](../windows/attribute-contexts.md).  
  
## <a name="see-also"></a>См. также  
 [Атрибуты IDL](../windows/idl-attributes.md)   
 [Атрибуты интерфейса](../windows/interface-attributes.md)   
 [Атрибуты метода](../windows/method-attributes.md)   
 [call_as](../windows/call-as.md)   
