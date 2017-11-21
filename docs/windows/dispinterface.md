---
title: "disp-интерфейса | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: vc-attr.dispinterface
dev_langs: C++
helpviewer_keywords: dispinterface attribute
ms.assetid: 61c5a4a1-ae92-47e9-8ee4-f847be90172b
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: e52d050b9b05ccb72969c531297367e729c258b1
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="dispinterface"></a>dispinterface
Помещает интерфейс в IDL-файл в качестве интерфейса диспетчеризации.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
[dispinterface]  
  
```  
  
## <a name="remarks"></a>Примечания  
 Если интерфейсу предшествует атрибут **dispinterface** языка C++, это вызывает помещение интерфейса в блок library созданного IDL-файла.  
  
 Если не указать базовый класс, интерфейс диспетчеризации будет производным от `IDispatch`. Необходимо указать [идентификатор](../windows/id.md) для членов интерфейса диспетчеризации.  
  
 Пример использования [dispinterface](http://msdn.microsoft.com/library/windows/desktop/aa366802) в документации MIDL:  
  
```  
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
|**Применение**|`interface`|  
|**Повторяемый**|Нет|  
|**Обязательные атрибуты**|Нет|  
|**Недопустимые атрибуты**|**dual**, **object**, **oleautomation**, `local`, **ms_union**|  
  
 Дополнительные сведения см. в разделе [Контексты атрибутов](../windows/attribute-contexts.md).  
  
## <a name="see-also"></a>См. также  
 [Атрибуты IDL](../windows/idl-attributes.md)   
 [Список атрибутов по использованию](../windows/attributes-by-usage.md)   
 [UUID](../windows/uuid-cpp-attributes.md)   
 [Двойная](../windows/dual.md)   
 [пользовательские](../windows/custom-cpp.md)   
 [object](../windows/object-cpp.md)   
 [__interface](../cpp/interface.md)   
