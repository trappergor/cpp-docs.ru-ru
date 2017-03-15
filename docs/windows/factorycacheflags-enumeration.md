---
title: "Перечисление FactoryCacheFlags | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "module/Microsoft::WRL::FactoryCacheFlags"
dev_langs: 
  - "C++"
ms.assetid: 6f54258f-0144-4264-9608-414e5905f6fb
caps.latest.revision: 4
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 4
---
# Перечисление FactoryCacheFlags
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Определяет, кэшируются ли объекты фабрики.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
enum FactoryCacheFlags;  
```  
  
## <a name="remarks"></a>Примечания  
 По умолчанию политика кэширования задается в виде [Тип модуля](../Topic/ModuleType%20Enumeration.md) параметр шаблона при создании [модуль](../windows/module-class.md) объекта. Для переопределения этой политики укажите значение `FactoryCacheFlags` при создании объекта фабрики.  
  
|||  
|-|-|  
|`FactoryCacheDefault`|Используется политика кэширования объекта `Module`.|  
|`FactoryCacheEnabled`|Включает кэширование фабрики независимо от параметра шаблона `ModuleType`, используемого для создания объекта `Module`.|  
|`FactoryCacheDisabled`|Выключает кэширование фабрики независимо от параметра шаблона `ModuleType`, используемого для создания объекта `Module`.|  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** implements.h  
  
 **Пространство имен:** Microsoft::WRL  
  
## <a name="see-also"></a>См. также раздел  
 [Пространство имен Microsoft::WRL](../windows/microsoft-wrl-namespace.md)