---
title: "Идентификатор | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- vc-attr.id
dev_langs:
- C++
helpviewer_keywords:
- id attribute
ms.assetid: a48d2c99-c5d2-4f46-bf96-5ac88dcb5d0c
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 9225a87f32c3c7bf42ca5fc7de98dd0ab8f12639
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="id"></a>id
Указывает `dispid` параметра для функции-члена (свойство или метод в интерфейсе или disp-интерфейс).  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
      [ id(  
   dispid  
) ]  
```  
  
#### <a name="parameters"></a>Параметры  
 `dispid`  
 Идентификатор диспетчеризации для метода интерфейса.  
  
## <a name="remarks"></a>Примечания  
 **Идентификатор** языка C++ имеет ту же функциональность, что [идентификатор](http://msdn.microsoft.com/library/windows/desktop/aa367040) языка MIDL.  
  
## <a name="example"></a>Пример  
 Далее приведен пример [привязываемых](../windows/bindable.md) пример демонстрирует использование **идентификатор**.  
  
## <a name="requirements"></a>Требования  
  
### <a name="attribute-context"></a>Контекст атрибута  
  
|||  
|-|-|  
|**Применение**|Метод интерфейса|  
|**Повторяемый**|Нет|  
|**Обязательные атрибуты**|Нет|  
|**Недопустимые атрибуты**|Нет|  
  
 Дополнительные сведения см. в разделе [Контексты атрибутов](../windows/attribute-contexts.md).  
  
## <a name="see-also"></a>См. также  
 [Атрибуты IDL](../windows/idl-attributes.md)   
 [Атрибуты метода](../windows/method-attributes.md)   
 [Атрибуты членов данных](../windows/data-member-attributes.md)   
 [значение по умолчанию](../windows/defaultvalue.md)   
 [in](../windows/in-cpp.md)   
 [out](../windows/out-cpp.md)   
