---
title: "Структура CreatorMap | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::Details::CreatorMap
- implements/Microsoft::WRL::Details::CreatorMap
dev_langs:
- C++
helpviewer_keywords:
- CreatorMap structure
ms.assetid: 94e40927-90c3-4107-bca3-3ad2dc4beda9
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: a941f052527b3617772bcb18b2092fdc35ea3a22
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="creatormap-structure"></a>CreatorMap - структура
Поддерживает инфраструктуру библиотека шаблонов C++ среды выполнения Windows и не предназначен для использования непосредственно из программного кода.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
struct CreatorMap;  
```  
  
## <a name="remarks"></a>Примечания  
 Содержит сведения об инициализации, регистрировать и отменять регистрацию объектов.  
  
 CreatorMap содержит следующие сведения:  
  
-   Как инициализировать, регистрировать и отменять регистрацию объектов.  
  
-   Как сравнить данные активации, в зависимости от фабрику классического COM или среды выполнения Windows.  
  
-   Сведения о фабрики кэша и имя сервера для интерфейса.  
  
## <a name="members"></a>Участники  
  
### <a name="public-data-members"></a>Открытые члены данных  
  
|Имя|Описание:|  
|----------|-----------------|  
|[Элемент данных CreatorMap::activationId](../windows/creatormap-activationid-data-member.md)|Представляет идентификатор объекта, определяемого по классического COM-код класса или имя среды выполнения Windows.|  
|[Элемент данных CreatorMap::factoryCache](../windows/creatormap-factorycache-data-member.md)|Хранит указатель на кэш фабрики для объекта CreatorMap.|  
|[Элемент данных CreatorMap::factoryCreator](../windows/creatormap-factorycreator-data-member.md)|Создает фабрику для указанного объекта CreatorMap.|  
|[Элемент данных CreatorMap::serverName](../windows/creatormap-servername-data-member.md)|Хранит имя сервера для объекта CreatorMap.|  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `CreatorMap`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** module.h  
  
 **Пространство имен:** Microsoft::wrl:: Details  
  
## <a name="see-also"></a>См. также  
 [Пространство имен Microsoft::WRL::Details](../windows/microsoft-wrl-details-namespace.md)