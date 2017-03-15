---
title: "Структура CreatorMap | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "module/Microsoft::WRL::Details::CreatorMap"
  - "implements/Microsoft::WRL::Details::CreatorMap"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CreatorMap - структура"
ms.assetid: 94e40927-90c3-4107-bca3-3ad2dc4beda9
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# Структура CreatorMap
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Предназначено для поддержки инфраструктуры [!INCLUDE[cppwrl](../windows/includes/cppwrl_md.md)], а не для непосредственного использования в коде.  
  
## Синтаксис  
  
```  
struct CreatorMap;  
```  
  
## Примечания  
 Содержит сведения об инициализации, регистрации и отмене регистрации объектов.  
  
 CreatorMap содержит следующие подразделы:  
  
-   Процедура инициализации, регистрации и отмены регистрации объектов.  
  
-   Процедура сравнения сведений об активации в зависимости от классической модели COM или фабрики [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)].  
  
-   Сведения о кэше фабрики и имени сервера для интерфейса.  
  
## Члены  
  
### Открытые члены данных  
  
|Имя|Описание|  
|---------|--------------|  
|[Элемент данных CreatorMap::activationId](../windows/creatormap-activationid-data-member.md)|Представляет идентификатор объекта, который определен или идентификатором класса классической модели COM, или именем [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)].|  
|[Элемент данных CreatorMap::factoryCache](../windows/creatormap-factorycache-data-member.md)|Сохраняет указатель на кэш фабрики для CreatorMap.|  
|[Элемент данных CreatorMap::factoryCreator](../Topic/CreatorMap::factoryCreator%20Data%20Member.md)|Создает фабрику для указанного CreatorMap.|  
|[Элемент данных CreatorMap::serverName](../windows/creatormap-servername-data-member.md)|Хранит имя сервера для CreatorMap.|  
  
## Иерархия наследования  
 `CreatorMap`  
  
## Требования  
 **Заголовок:** module.h  
  
 **Пространство имен:** Microsoft::WRL::Details  
  
## См. также  
 [Пространство имен Microsoft::WRL::Details](../windows/microsoft-wrl-details-namespace.md)