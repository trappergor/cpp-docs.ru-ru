---
title: "Перечисление FactoryCacheFlags | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: module/Microsoft::WRL::FactoryCacheFlags
dev_langs: C++
ms.assetid: 6f54258f-0144-4264-9608-414e5905f6fb
caps.latest.revision: "4"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: bb4efeb716255ae67a01fca7cf04a54816e227d9
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
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