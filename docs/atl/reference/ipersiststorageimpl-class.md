---
title: "IPersistStorageImpl Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "ATL::IPersistStorageImpl"
  - "ATL::IPersistStorageImpl<T>"
  - "ATL.IPersistStorageImpl<T>"
  - "IPersistStorageImpl"
  - "ATL.IPersistStorageImpl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "IPersistStorageImpl class"
  - "хранение, ATL - библиотека"
ms.assetid: d652f02c-239c-47c7-9a50-3e9fc3014fff
caps.latest.revision: 20
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 23
---
# IPersistStorageImpl Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Этот класс реализует интерфейс [IPersistStorage](http://msdn.microsoft.com/library/windows/desktop/ms679731).  
  
> [!IMPORTANT]
>  Этот класс и его члены нельзя использовать в приложениях, выполняемых в [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)].  
  
## Синтаксис  
  
```  
  
      template <  
class T  
>  
class ATL_NO_VTABLE IPersistStorageImpl :  
public IPersistStorage  
```  
  
#### Параметры  
 `T`  
 Класс, производный от `IPersistStorageImpl`.  
  
## Члены  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[IPersistStorageImpl::GetClassID](../Topic/IPersistStorageImpl::GetClassID.md)|Извлекает идентификатор CLSID объекта.|  
|[IPersistStorageImpl::HandsOffStorage](../Topic/IPersistStorageImpl::HandsOffStorage.md)|Указывает объект для освобождения всех объектов хранилища и выполнить вход в режим HandsOff.  Реализация библиотеки ATL возвращает `S_OK`.|  
|[IPersistStorageImpl::InitNew](../Topic/IPersistStorageImpl::InitNew.md)|Инициализирует новое хранилище.|  
|[IPersistStorageImpl::IsDirty](../Topic/IPersistStorageImpl::IsDirty.md)|Проверяет, были ли изменены данные объекта с момента последнего сохранены их.|  
|[IPersistStorageImpl::Load](../Topic/IPersistStorageImpl::Load.md)|Загружает свойства объекта из указанного хранилища.|  
|[IPersistStorageImpl::Save](../Topic/IPersistStorageImpl::Save.md)|Сохраняет свойства объекта в указанном хранилище.|  
|[IPersistStorageImpl::SaveCompleted](../Topic/IPersistStorageImpl::SaveCompleted.md)|Уведомляет объект, он может возвратить в обычный режим записи к его объект хранилища.  Реализация библиотеки ATL возвращает `S_OK`.|  
  
## Заметки  
 `IPersistStorageImpl` реализует интерфейс [IPersistStorage](http://msdn.microsoft.com/library/windows/desktop/ms679731), который позволяет клиенту запроса, что ваша загрузка объекта и сохраняет его постоянных данных с помощью хранения.  
  
 Реализация этого класса требуется, чтобы класс `T` делает реализация интерфейса `IPersistStreamInit` доступные через `QueryInterface`.  Обычно это означает, что `T` класс должен наследовать от [IPersistStreamInitImpl](../../atl/reference/ipersiststreaminitimpl-class.md), предоставить запись для `IPersistStreamInit` в [Сопоставление модели COM](../Topic/BEGIN_COM_MAP.md) и использовать [сопоставление свойств](../Topic/BEGIN_PROP_MAP.md) для описания сведений о типе постоянные.  
  
 **Связанные статьи** [Учебник по библиотеке ATL](../Topic/Active%20Template%20Library%20\(ATL\)%20Tutorial.md), [Создание проекта библиотеки ATL](../../atl/reference/creating-an-atl-project.md)  
  
## Иерархия наследования  
 `IPersistStorage`  
  
 `IPersistStorageImpl`  
  
## Требования  
 **Header:**  atlcom.h  
  
## См. также  
 [Storages and Streams](http://msdn.microsoft.com/library/windows/desktop/aa380352)   
 [IPersistStreamInitImpl Class](../../atl/reference/ipersiststreaminitimpl-class.md)   
 [IPersistPropertyBagImpl Class](../../atl/reference/ipersistpropertybagimpl-class.md)   
 [Class Overview](../../atl/atl-class-overview.md)