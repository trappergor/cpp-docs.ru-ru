---
title: Структура FactoryCache | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::Details::FactoryCache
dev_langs:
- C++
helpviewer_keywords:
- FactoryCache structure
ms.assetid: 624544e6-0989-47f6-a3e9-edb60e1ee6d4
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 04356316b67f3c341fe1dd1821750fcd3136aa40
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2018
---
# <a name="factorycache-structure"></a>FactoryCache - структура
Поддерживает инфраструктуру библиотека шаблонов C++ среды выполнения Windows и не предназначен для использования непосредственно из программного кода.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
struct FactoryCache;  
```  
  
## <a name="remarks"></a>Примечания  
 Содержит местоположение фабрики класса и значение, которое идентифицирует зарегистрированный среды выполнения Windows или COM-класса объекта.  
  
## <a name="members"></a>Участники  
  
### <a name="public-data-members"></a>Открытые члены данных  
  
|Имя|Описание|  
|----------|-----------------|  
|[Элемент данных FactoryCache::cookie](../windows/factorycache-cookie-data-member.md)|Содержит значение, которое идентифицирует зарегистрированный объект класса среды выполнения Windows или COM, а впоследствии будет использоваться для отмены регистрации объекта.|  
|[Элемент данных FactoryCache::factory](../windows/factorycache-factory-data-member.md)|Указывает на фабрику классов среды выполнения Windows или COM.|  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `FactoryCache`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** module.h  
  
 **Пространство имен:** Microsoft::wrl:: Details  
  
## <a name="see-also"></a>См. также  
 [Пространство имен Microsoft::WRL::Details](../windows/microsoft-wrl-details-namespace.md)