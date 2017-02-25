---
title: "CComAggObject Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "ATL::CComAggObject<contained>"
  - "ATL.CComAggObject"
  - "ATL.CComAggObject<contained>"
  - "CComAggObject"
  - "ATL::CComAggObject"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "aggregate objects [C++], в ATL"
  - "aggregation [C++], ATL-объекты"
  - "CComAggObject class"
ms.assetid: 7aa90d69-d399-477b-880d-e2cdf0ef7881
caps.latest.revision: 29
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 32
---
# CComAggObject Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Этот класс реализует интерфейс [IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509) для статистически вычислениеого объекта.  По определению, объединенный объект содержится внутри внешний объект.  Класс `CComAggObject` похож на [CComObject Class](../../atl/reference/ccomobject-class.md), за исключением того, что предоставляет интерфейс, который доступен непосредственно к внешним клиентам.  
  
## Синтаксис  
  
```  
  
      template<  
   class contained  
>  
class CComAggObject :  
   public IUnknown, public CComObjectRootEx  
   < contained::_ThreadModel::ThreadModelNoCS >  
```  
  
#### Параметры  
 `contained`  
 Класс, производный от [CComObjectRoot](../../atl/reference/ccomobjectroot-class.md) или [CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md), а также от других интерфейсов нужно поддерживать в объекте.  
  
## Члены  
  
### Открытые конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|[CComAggObject::CComAggObject](../Topic/CComAggObject::CComAggObject.md)|Конструктор.|  
|[CComAggObject::~CComAggObject](../Topic/CComAggObject::~CComAggObject.md)|Деструктор.|  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[CComAggObject::AddRef](../Topic/CComAggObject::AddRef.md)|Увеличивает счетчик ссылок для статистически вычислениеом объекте.|  
|[CComAggObject::CreateInstance](../Topic/CComAggObject::CreateInstance.md)|Эта статическая функция позволяет создать новый объект **CComAggObject\<** `contained`**\>** без издержек [CoCreateInstance](http://msdn.microsoft.com/library/windows/desktop/ms686615).|  
|[CComAggObject::FinalConstruct](../Topic/CComAggObject::FinalConstruct.md)|Выполняет инициализацию `m_contained` окончательную.|  
|[CComAggObject::FinalRelease](../Topic/CComAggObject::FinalRelease.md)|Выполняет окончательное разрушение `m_contained`.|  
|[CComAggObject::QueryInterface](../Topic/CComAggObject::QueryInterface.md)|Извлекает указатель на запрашиваемый интерфейс.|  
|[CComAggObject::Release](../Topic/CComAggObject::Release.md)|Уменьшает счетчик ссылок для статистически вычислениеом объекте.|  
  
### Открытые члены данных  
  
|Имя|Описание|  
|---------|--------------|  
|[CComAggObject::m\_contained](../Topic/CComAggObject::m_contained.md)|Вызовы делегатов `IUnknown` к внешнему неизвестный тип.|  
  
## Заметки  
 Средства [IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509)`CComAggObject` для статистически вычислениеого объекта.  `CComAggObject` имеет свой собственный интерфейс **IUnknown**, отдельно от интерфейса **IUnknown** внешнего объекта, и поддерживаются собственным счетчика ссылок.  
  
 Дополнительные сведения о агрегате см. в статье [Принципы COM\-объект библиотеки ATL](../../atl/fundamentals-of-atl-com-objects.md).  
  
## Иерархия наследования  
 `CComObjectRootBase`  
  
 [CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md)  
  
 `IUnknown`  
  
 `CComAggObject`  
  
## Требования  
 **Header:**  atlcom.h  
  
## См. также  
 [CComObject Class](../../atl/reference/ccomobject-class.md)   
 [CComPolyObject Class](../../atl/reference/ccompolyobject-class.md)   
 [DECLARE\_AGGREGATABLE](../Topic/DECLARE_AGGREGATABLE.md)   
 [DECLARE\_ONLY\_AGGREGATABLE](../Topic/DECLARE_ONLY_AGGREGATABLE.md)   
 [DECLARE\_NOT\_AGGREGATABLE](../Topic/DECLARE_NOT_AGGREGATABLE.md)   
 [Class Overview](../../atl/atl-class-overview.md)