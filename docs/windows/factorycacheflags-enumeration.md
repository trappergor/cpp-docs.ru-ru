---
title: "Перечисление FactoryCacheFlags | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::FactoryCacheFlags
dev_langs:
- C++
ms.assetid: 6f54258f-0144-4264-9608-414e5905f6fb
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 41b31ccede1cca717418c9f489ab7de67d313319
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="factorycacheflags-enumeration"></a>Перечисление FactoryCacheFlags
Определяет, кэшируются ли объекты фабрики.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
enum FactoryCacheFlags;  
```  
  
## <a name="remarks"></a>Примечания  
 По умолчанию политика кэширования указывается как [ModuleType](../windows/moduletype-enumeration.md) параметр шаблона при создании [модуль](../windows/module-class.md) объекта. Для переопределения этой политики укажите значение `FactoryCacheFlags` при создании объекта фабрики.  
  
|||  
|-|-|  
|`FactoryCacheDefault`|Используется политика кэширования объекта `Module`.|  
|`FactoryCacheEnabled`|Включает кэширование фабрики независимо от параметра шаблона `ModuleType`, используемого для создания объекта `Module`.|  
|`FactoryCacheDisabled`|Выключает кэширование фабрики независимо от параметра шаблона `ModuleType`, используемого для создания объекта `Module`.|  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** implements.h  
  
 **Пространство имен:** Microsoft::WRL  
  
## <a name="see-also"></a>См. также  
 [Пространство имен Microsoft::WRL](../windows/microsoft-wrl-namespace.md)