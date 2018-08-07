---
title: Идентификатор | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.id
dev_langs:
- C++
helpviewer_keywords:
- id attribute
ms.assetid: a48d2c99-c5d2-4f46-bf96-5ac88dcb5d0c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: b36a45dad71f2144c3e3d0990ab7715d00e8ff21
ms.sourcegitcommit: 4586bfc32d8bc37ab08b24816d7fad5df709bfa3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/07/2018
ms.locfileid: "39605712"
---
# <a name="id"></a>id
Указывает *dispid* параметра для функции-члена (свойство или метод, в интерфейс или диспетчерский интерфейс).  
  
## <a name="syntax"></a>Синтаксис  
  
```  
[ id(  
   dispid  
) ]  
```  
  
### <a name="parameters"></a>Параметры  
 *Идентификатор DISPID*  
 Идентификатор диспетчеризации метода интерфейса.  
  
## <a name="remarks"></a>Примечания  
 **Идентификатор** атрибут C++ имеет ту же функциональность, что [идентификатор](http://msdn.microsoft.com/library/windows/desktop/aa367040) описании атрибута MIDL.  
  
## <a name="example"></a>Пример  
 См. в примере [bindable](../windows/bindable.md) пример демонстрирует использование **идентификатор**.  
  
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
 [DefaultValue](../windows/defaultvalue.md)   
 [in](../windows/in-cpp.md)   
 [out](../windows/out-cpp.md)   