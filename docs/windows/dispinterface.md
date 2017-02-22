---
title: "dispinterface | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "vc-attr.dispinterface"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "dispinterface - атрибут"
ms.assetid: 61c5a4a1-ae92-47e9-8ee4-f847be90172b
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# dispinterface
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Помещает интерфейс в IDL\-файл в качестве интерфейса диспетчеризации.  
  
## Синтаксис  
  
```  
  
[dispinterface]  
  
```  
  
## Заметки  
 Если интерфейсу предшествует атрибут **dispinterface** языка C\+\+, это вызывает помещение интерфейса в блок library созданного IDL\-файла.  
  
 Если не указать базовый класс, интерфейс диспетчеризации будет производным от `IDispatch`. Необходимо указать [идентификатор](../windows/id.md) для членов интерфейса диспетчеризации.  
  
 Пример использования [dispinterface](http://msdn.microsoft.com/library/windows/desktop/aa366802) в документации MIDL:  
  
```  
dispinterface helloPro   
   { interface hello; };   
```  
  
 не является допустимым для атрибута **dispinterface**.  
  
## Пример  
 Просмотрите пример с [bindable](../windows/bindable.md), чтобы увидеть, как можно использовать **dispinterface**.  
  
## Требования  
  
### Контекст атрибута  
  
|||  
|-|-|  
|**Применение**|`interface`|  
|**Повторяемый**|Нет|  
|**Обязательные атрибуты**|Нет|  
|**Недопустимые атрибуты**|**dual**, **object**, **oleautomation**, `local`, **ms\_union**|  
  
 Дополнительные сведения см. в разделе [Контексты атрибутов](../windows/attribute-contexts.md).  
  
## См. также  
 [IDL Attributes](../windows/idl-attributes.md)   
 [Attributes by Usage](../windows/attributes-by-usage.md)   
 [uuid](../windows/uuid-cpp-attributes.md)   
 [dual](../Topic/dual.md)   
 [custom](../windows/custom-cpp.md)   
 [object](../Topic/object%20\(C++\).md)   
 [\_\_interface](../Topic/__interface.md)   
 [Attributes Samples](http://msdn.microsoft.com/ru-ru/558ebdb2-082f-44dc-b442-d8d33bf7bdb8)