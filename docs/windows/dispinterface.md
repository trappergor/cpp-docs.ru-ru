---
title: disp-интерфейс | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.dispinterface
dev_langs:
- C++
helpviewer_keywords:
- dispinterface attribute
ms.assetid: 61c5a4a1-ae92-47e9-8ee4-f847be90172b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 18308cc66e2a01aa5e0396f098096ee9d49416bf
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/08/2018
ms.locfileid: "39644334"
---
# <a name="dispinterface"></a>dispinterface
Помещает интерфейс в IDL-файл в качестве интерфейса диспетчеризации.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
[dispinterface]  
```  
  
## <a name="remarks"></a>Примечания  
 Если интерфейсу предшествует атрибут **dispinterface** языка C++, это вызывает помещение интерфейса в блок library созданного IDL-файла.  
  
 Если не указать базовый класс, интерфейс диспетчеризации будет производным от `IDispatch`. Необходимо указать [идентификатор](../windows/id.md) для членов интерфейса диспетчеризации.  
  
 Пример использования [dispinterface](http://msdn.microsoft.com/library/windows/desktop/aa366802) в документации MIDL:  
  
```cpp  
dispinterface helloPro   
   { interface hello; };   
```  
  
 не является допустимым для атрибута **dispinterface** .  
  
## <a name="example"></a>Пример  
 Просмотрите пример с [bindable](../windows/bindable.md) , чтобы увидеть, как можно использовать **dispinterface**.  
  
## <a name="requirements"></a>Требования  
  
### <a name="attribute-context"></a>Контекст атрибута  
  
|||  
|-|-|  
|**Применение**|**interface**|  
|**Повторяемый**|Нет|  
|**Обязательные атрибуты**|Нет|  
|**Недопустимые атрибуты**|`dual`, `object`, `oleautomation`, `local`, `ms_union`|  
  
 Дополнительные сведения см. в разделе [Контексты атрибутов](../windows/attribute-contexts.md).  
  
## <a name="see-also"></a>См. также  
 [Атрибуты IDL](../windows/idl-attributes.md)   
 [Список атрибутов по использованию](../windows/attributes-by-usage.md)   
 [UUID](../windows/uuid-cpp-attributes.md)   
 [Dual](../windows/dual.md)   
 [Custom](../windows/custom-cpp.md)   
 [object](../windows/object-cpp.md)   
 [__interface](../cpp/interface.md)   