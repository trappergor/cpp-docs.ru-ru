---
title: "CComCachedTearOffObject Class | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "ATL::CComCachedTearOffObject"
  - "ATL.CComCachedTearOffObject"
  - "ATL.CComCachedTearOffObject<contained>"
  - "CComCachedTearOffObject"
  - "ATL::CComCachedTearOffObject<contained>"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "кэш, ATL cached tear-off objects"
  - "CComCachedTearOffObject class"
ms.assetid: ae19507d-a1de-4dbc-a988-da9f75a50c95
caps.latest.revision: 19
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CComCachedTearOffObject Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Этот класс реализует [IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509), запрещены интерфейса.  
  
## Синтаксис  
  
```  
  
      template <  
   class contained  
>  
class CComCachedTearOffObject : public IUnknown,  
   public CComObjectRootEx< contained::_ThreadModel::ThreadModelNoCS >  
```  
  
#### Параметры  
 `contained`  
 Перемещаемый собственный класс, производный от `CComTearOffObjectBase` и интерфейсы требуется пользовательский перемещаемый объект к поддержке.  
  
## Члены  
  
### Открытые конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|[CComCachedTearOffObject::CComCachedTearOffObject](../Topic/CComCachedTearOffObject::CComCachedTearOffObject.md)|Конструктор.|  
|[CComCachedTearOffObject::~CComCachedTearOffObject](../Topic/CComCachedTearOffObject::~CComCachedTearOffObject.md)|Деструктор.|  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[CComCachedTearOffObject::AddRef](../Topic/CComCachedTearOffObject::AddRef.md)|Увеличивает счетчик ссылок для объекта `CComCachedTearOffObject`.|  
|[CComCachedTearOffObject::FinalConstruct](../Topic/CComCachedTearOffObject::FinalConstruct.md)|Вызывает метод `m_contained::FinalConstruct` \(перемещаемый классов\).|  
|[CComCachedTearOffObject::FinalRelease](../Topic/CComCachedTearOffObject::FinalRelease.md)|Вызывает метод `m_contained::FinalRelease` \(перемещаемый классов\).|  
|[CComCachedTearOffObject::QueryInterface](../Topic/CComCachedTearOffObject::QueryInterface.md)|Возвращает указатель на `IUnknown` объекта `CComCachedTearOffObject` или на запрашиваемый интерфейс в перемещаемом классе \(классе `contained`\).|  
|[CComCachedTearOffObject::Release](../Topic/CComCachedTearOffObject::Release.md)|Уменьшает счетчик ссылок для объекта `CComCachedTearOffObject` и удаляет его, если счетчик ссылок 0.|  
  
### Открытые члены данных  
  
|Имя|Описание|  
|---------|--------------|  
|[CComCachedTearOffObject::m\_contained](../Topic/CComCachedTearOffObject::m_contained.md)|Объект `CComContainedObject`, производный от класса `contained` перемещаемые класса \(\).|  
  
## Заметки  
 Средства [IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509)`CComCachedTearOffObject`, запрещены интерфейса.  Этот класс отличается от `CComTearOffObject` в том, что `CComCachedTearOffObject` имеет собственное **IUnknown**, отдельно от **IUnknown** объекта владельцем \(владелец объекта, для которого создается перемещаемое\).  `CComCachedTearOffObject` поддерживает собственный счетчика ссылок на своем **IUnknown** и удаляются после его значение счетчика ссылок равен нулю.  Однако при запросе любого из его перемещаемых интерфейсов, то будет увеличивается счетчик ссылок **IUnknown** объекта владельцем.  
  
 Если объект, реализующий `CComCachedTearOffObject` перемещаемое представляют готовый и перемещаемый интерфейс для вновь запрашивается, то один и тот же объект `CComCachedTearOffObject` используется повторно.  Напротив, если перемещаемый интерфейс, реализованный `CComTearOffObject` вновь запрашивается для посредством объекта владельцем другой, `CComTearOffObject` будет создан экземпляр.  
  
 Класс владелец должен реализовать `FinalRelease` и вызвать **Выпуск** в кэшированном **IUnknown** для `CComCachedTearOffObject`, уменьшает его счетчик ссылок.  Это приведет к `FinalRelease` объекта `CComCachedTearOffObject` вызываться и удаление перемещаемое.  
  
## Иерархия наследования  
 `CComObjectRootBase`  
  
 [CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md)  
  
 `IUnknown`  
  
 `CComCachedTearOffObject`  
  
## Требования  
 **Header:**  atlcom.h  
  
## См. также  
 [CComTearOffObject Class](../../atl/reference/ccomtearoffobject-class.md)   
 [CComObjectRootEx Class](../../atl/reference/ccomobjectrootex-class.md)   
 [Class Overview](../../atl/atl-class-overview.md)