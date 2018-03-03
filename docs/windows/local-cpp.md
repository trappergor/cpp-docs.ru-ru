---
title: "локальный (C++) | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- vc-attr.local
dev_langs:
- C++
helpviewer_keywords:
- local attribute
ms.assetid: 35cdd668-bd8e-492a-b7b8-263e7b662437
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 3543adfe0cb25f7946e6ed6c81c4bd66a7b60324
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
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
