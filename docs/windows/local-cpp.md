---
title: локальный (C++) | Документация Майкрософт
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
ms.openlocfilehash: ad1fb4dd281918b0d9ab3494c9a9f060468fc389
ms.sourcegitcommit: 38af5a1bf35249f0a51e3aafc6e4077859c8f0d9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/09/2018
ms.locfileid: "40018101"
---
# <a name="local-c"></a>local (C++)
При использовании в заголовке интерфейс позволяет использовать как генератор заголовка компилятора MIDL. При использовании в отдельной функции, обозначает локальной процедуры, для которого создаются без заглушек.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
[local]  
```  
  
## <a name="remarks"></a>Примечания  
 **Локального** атрибут C++ имеет ту же функциональность, что [локального](http://msdn.microsoft.com/library/windows/desktop/aa367071) описании атрибута MIDL.  
  
## <a name="example"></a>Пример  
 См. в разделе [call_as](../windows/call-as.md) пример демонстрирует использование **локального**.  
  
## <a name="requirements"></a>Требования  
  
### <a name="attribute-context"></a>Контекст атрибута  
  
|||  
|-|-|  
|**Применение**|**интерфейс**, метод интерфейса|  
|**Повторяемый**|Нет|  
|**Обязательные атрибуты**|Нет|  
|**Недопустимые атрибуты**|`dispinterface`|  
  
 Дополнительные сведения см. в разделе [Контексты атрибутов](../windows/attribute-contexts.md).  
  
## <a name="see-also"></a>См. также  
 [Атрибуты IDL](../windows/idl-attributes.md)   
 [Атрибуты интерфейса](../windows/interface-attributes.md)   
 [Атрибуты метода](../windows/method-attributes.md)   
 [call_as](../windows/call-as.md)   