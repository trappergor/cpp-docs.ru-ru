---
title: Перечисление FactoryCacheFlags | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::FactoryCacheFlags
dev_langs:
- C++
ms.assetid: 6f54258f-0144-4264-9608-414e5905f6fb
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 5ba3d9b75ff72399e1b9a027c937c24bba4a6c37
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2018
ms.locfileid: "33874334"
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