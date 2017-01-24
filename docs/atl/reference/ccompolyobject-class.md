---
title: "CComPolyObject Class | Microsoft Docs"
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
  - "CComPolyObject"
  - "ATL.CComPolyObject<contained>"
  - "ATL::CComPolyObject"
  - "ATL::CComPolyObject<contained>"
  - "ATL.CComPolyObject"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "aggregate objects [C++], в ATL"
  - "aggregation [C++], ATL-объекты"
  - "CComPolyObject class"
ms.assetid: eaf67c18-e855-48ca-9b15-f1df3106121b
caps.latest.revision: 19
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CComPolyObject Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Этот класс реализует **IUnknown** для статистически вычислениеого или nonaggregated объекта.  
  
## Синтаксис  
  
```  
  
      template<  
   class contained   
>  
class CComPolyObject : public IUnknown, public CComObjectRootEx  
   < contained::_ThreadModel::ThreadModelNoCS >  
```  
  
#### Параметры  
 `contained`  
 Класс, производный от [CComObjectRoot](../../atl/reference/ccomobjectroot-class.md) или [CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md), а также от других интерфейсов нужно поддерживать в объекте.  
  
## Члены  
  
### Открытые конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|[CComPolyObject::CComPolyObject](../Topic/CComPolyObject::CComPolyObject.md)|Конструктор.|  
|[CComPolyObject::~CComPolyObject](../Topic/CComPolyObject::~CComPolyObject.md)|Деструктор.|  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[CComPolyObject::AddRef](../Topic/CComPolyObject::AddRef.md)|Увеличивает число ссылок объекта.|  
|[CComPolyObject::CreateInstance](../Topic/CComPolyObject::CreateInstance.md)|\(Статический\) Позволяет создать новый объект **CComPolyObject\<** `contained`**\>** без издержек [CoCreateInstance](http://msdn.microsoft.com/library/windows/desktop/ms686615).|  
|[CComPolyObject::FinalConstruct](../Topic/CComPolyObject::FinalConstruct.md)|Выполняет инициализацию `m_contained` окончательную.|  
|[CComPolyObject::FinalRelease](../Topic/CComPolyObject::FinalRelease.md)|Выполняет окончательное разрушение `m_contained`.|  
|[CComPolyObject::QueryInterface](../Topic/CComPolyObject::QueryInterface.md)|Извлекает указатель на запрашиваемый интерфейс.|  
|[CComPolyObject::Release](../Topic/CComPolyObject::Release.md)|Уменьшает счетчик ссылок объекта.|  
  
### Открытые члены данных  
  
|Имя|Описание|  
|---------|--------------|  
|[CComPolyObject::m\_contained](../Topic/CComPolyObject::m_contained.md)|Вызовы делегатов **IUnknown** к внешнему неизвестный если объект статистической обработки или в **IUnknown** объекта, если объект не статистической обработки.|  
  
## Заметки  
 Средства [IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509)`CComPolyObject` для статистически вычислениеого или nonaggregated объекта.  
  
 Если экземпляр `CComPolyObject` создания, проверено значение внешнего неизвестным.  Если это **NULL**, то **IUnknown** реализуется для nonaggregated объекта.  Если внешний неизвестно не **NULL**, то **IUnknown** реализуется для статистически вычислениеого объекта.  
  
 Преимущество использования `CComPolyObject` что позволяет избежать [CComAggObject](../../atl/reference/ccomaggobject-class.md) и having и [CComObject](../../atl/reference/ccomobject-class.md) в модуле, чтобы настроить статистические и nonaggregated вариантов.  Один объект `CComPolyObject` обрабатывает оба варианта.  Это означает, что только одна копия vtable и одна копия функций существуют в модуле.  Если в таблице vtable велико, это может значительно снизить свой размер модуля.  Однако если в таблице vtable мало, то с помощью `CComPolyObject` могут вызвать несколько более большом размере модуля, поскольку оно не оптимизироватьо для статистически вычислениеого или nonaggregated объекта, например `CComAggObject` и `CComObject`.  
  
 Если макрос `DECLARE_POLY_AGGREGATABLE` определен в определении класса объекта, `CComPolyObject` будет использоваться для создания объекта.  `DECLARE_POLY_AGGREGATABLE` автоматически будет объявлено при использовании мастера проектов библиотеки ATL для создания полный контроль и управление Internet Explorer.  
  
 Если выполняется обработка проводится объект `CComPolyObject` имеет собственное **IUnknown**, отдельно от **IUnknown** внешнего объекта, и поддерживаются собственным счетчика ссылок.  `CComPolyObject` использует [CComContainedObject](../../atl/reference/ccomcontainedobject-class.md) чтобы делегировать к внешнему неизвестный тип.  
  
 Дополнительные сведения о агрегате см. в статье [Принципы COM\-объект библиотеки ATL](../../atl/fundamentals-of-atl-com-objects.md).  
  
## Иерархия наследования  
 `CComObjectRootBase`  
  
 [CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md)  
  
 `IUnknown`  
  
 `CComPolyObject`  
  
## Требования  
 **Header:**  atlcom.h  
  
## См. также  
 [CComObjectRootEx Class](../../atl/reference/ccomobjectrootex-class.md)   
 [DECLARE\_POLY\_AGGREGATABLE](../Topic/DECLARE_POLY_AGGREGATABLE.md)   
 [Class Overview](../../atl/atl-class-overview.md)