---
title: "Implementing CComObject, CComAggObject, and CComPolyObject | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CComPolyObject"
  - "CComAggObject"
  - "CComObject"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CComAggObject class"
  - "CComObject class, реализация"
  - "CComPolyObject class, реализация"
  - "CreateInstance - метод"
ms.assetid: 5aabe938-104d-492e-9c41-9f7fb1c62098
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# Implementing CComObject, CComAggObject, and CComPolyObject
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Классифицирует шаблон [CComObject](../atl/reference/ccomobject-class.md), [CComAggObject](../atl/reference/ccomaggobject-class.md) и [CComPolyObject](../atl/reference/ccompolyobject-class.md) всегда большинство производные классы в цепочке наследования.  Ответственность за их обработать все методы в **IUnknown**: `QueryInterface`, `AddRef` и **Выпуск**.  Кроме того, `CComAggObject` и `CComPolyObject` \(при использовании для агрегированных объектов\) обеспечивают специальную ссылку и семантику подсчета `QueryInterface` необходимы для внутреннего неизвестным.  
  
 Ли `CComObject`, `CComAggObject` или `CComPolyObject`, используемые зависит от не объявлен ли один \(или нет\) из из следующих макросов:  
  
|Макрос|Действие|  
|------------|--------------|  
|`DECLARE_NOT_AGGREGATABLE`|Всегда использует `CComObject`.|  
|`DECLARE_AGGREGATABLE`|Если используется `CComAggObject` агрегировать объект и `CComObject`, если он отсутствует.  `CComCoClass` содержащий этот макрос так, если ни одна из макросов **DECLARE\_\*\_AGGREGATABLE** объявляются в вашем классе, то это будет значение по умолчанию.|  
|`DECLARE_ONLY_AGGREGATABLE`|Всегда использует `CComAggObject`.  Возвращает ошибку, если объект не статистической обработки.|  
|`DECLARE_POLY_AGGREGATABLE`|Библиотеки ATL создает экземпляр **CComPolyObject\<CYourClass\>** при **IClassFactory::CreateInstance** вызываются.  Во время создания проверено значение внешнего неизвестным.  Если это **NULL**, то **IUnknown** реализуется для nonaggregated объекта.  Если внешний неизвестно не **NULL**, то **IUnknown** реализуется для статистически вычислениеого объекта.|  
  
 Преимущество использования `CComAggObject` и `CComObject`, что реализация **IUnknown** оптимизирована для типа, созданной объекта.  Например, nonaggregated объекту требуется только значение счетчика ссылок, пока статистическая обработка вычислениеому объекту требуется и счетчика ссылок для внутреннего неизвестным и указатель на внешний неизвестный тип.  
  
 Преимущество использования `CComPolyObject` что позволяет избежать `CComAggObject` и having и `CComObject` в модуле, чтобы настроить статистические и nonaggregated вариантов.  Один объект `CComPolyObject` обрабатывает оба варианта.  Это означает, что только одна копия vtable и одна копия функций существуют в модуле.  Если в таблице vtable велико, это может значительно снизить свой размер модуля.  Однако если в таблице vtable мало, то с помощью `CComPolyObject` могут вызвать несколько более большом размере модуля, поскольку оно не оптимизироватьо для статистически вычислениеого или nonaggregated объекта, например `CComAggObject` и `CComObject`.  
  
## См. также  
 [Fundamentals of ATL COM Objects](../atl/fundamentals-of-atl-com-objects.md)   
 [Aggregation and Class Factory Macros](../atl/reference/aggregation-and-class-factory-macros.md)