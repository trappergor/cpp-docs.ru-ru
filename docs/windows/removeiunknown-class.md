---
title: "Класс RemoveIUnknown | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "client/Microsoft::WRL::Details::RemoveIUnknown"
dev_langs: 
  - "C++"
ms.assetid: 998e711a-7d1a-44c6-a016-e6167aa40863
caps.latest.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# Класс RemoveIUnknown
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Предназначено для поддержки инфраструктуры WRL, а не для непосредственного использования в коде.  
  
## Синтаксис  
  
```  
template <  
   typename T  
>  
struct RemoveIUnknown;  
  
template <  
   typename T  
>  
class RemoveIUnknown : public T;  
```  
  
#### Параметры  
 `T`  
 Класс.  
  
## Примечания  
 Создает тип, эквивалентный базовому типу `IUnknown`, но имеющий невиртуальные функции\-члены `QueryInterface`, `AddRef` и `Release`.  
  
 По умолчанию методы модели COM предоставляют виртуальные методы `QueryInterface`, `AddRef` и Release.  Однако `ComPtr` не требует нагрузки виртуальных методов.  `RemoveIUnknown` исключает эту нагрузку, предоставляя закрытые, невиртуальные методы `QueryInterface`, `AddRef` и `Release`.  
  
## Члены  
  
### Общедоступные Typedefs  
  
|Имя|Описание|  
|---------|--------------|  
|`ReturnType`|Синоним для типа, эквивалентного параметру `T` шаблона, но имеющего невиртуальные члены IUnknown.|  
  
## Иерархия наследования  
 `T`  
  
 `RemoveIUnknown`  
  
## Требования  
 **Заголовок:** client.h  
  
 **Пространство имен:** Microsoft::WRL::Details  
  
## См. также  
 [Пространство имен Microsoft::WRL::Details](../windows/microsoft-wrl-details-namespace.md)