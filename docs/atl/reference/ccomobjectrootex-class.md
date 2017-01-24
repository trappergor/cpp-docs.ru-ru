---
title: "CComObjectRootEx Class | Microsoft Docs"
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
  - "ATL.CComObjectRootEx"
  - "ATL::CComObjectRootEx<ThreadModel>"
  - "CComObjectRootEx"
  - "ATL::CComObjectRootEx"
  - "ATL.CComObjectRootEx<ThreadModel>"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "reference counting"
ms.assetid: 894a3d7c-2daf-4fd0-8fa4-e6a05bcfb631
caps.latest.revision: 20
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CComObjectRootEx Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Этот класс предоставляет методы для управления count ссылки на объект и для nonaggregated и агрегированных объектов.  
  
## Синтаксис  
  
```  
  
      template<  
   class ThreadModel   
>  
class CComObjectRootEx : public CComObjectRootBase  
```  
  
#### Параметры  
 `ThreadModel`  
 Класс методы, реализующие нужную потоковую модель.  Можно явно задать потоковую модель с помощью `ThreadModel` к [CComSingleThreadModel](../../atl/reference/ccomsinglethreadmodel-class.md), [CComMultiThreadModel](../../atl/reference/ccommultithreadmodel-class.md) или [CComMultiThreadModelNoCS](../Topic/CComMultiThreadModelNoCS%20Class.md).  Можно принять модель потока сервера по умолчанию путем установки `ThreadModel` к [CComObjectThreadModel](../Topic/CComObjectThreadModel.md) или [CComGlobalsThreadModel](../Topic/CComGlobalsThreadModel.md).  
  
## Члены  
  
### Методы  
  
|||  
|-|-|  
|[CComObjectRootEx](../Topic/CComObjectRootEx::CComObjectRootEx.md)|Конструктор.|  
|[InternalAddRef](../Topic/CComObjectRootEx::InternalAddRef.md)|Увеличивает счетчик ссылок для nonaggregated объекта.|  
|[InternalRelease](../Topic/CComObjectRootEx::InternalRelease.md)|Уменьшает счетчик ссылок для nonaggregated объекта.|  
|[Блокировка](../Topic/CComObjectRootEx::Lock.md)|Если модель потоков многопоточного, то возвращает владельца объекта критической секции.|  
|[Unlock](../Topic/CComObjectRootEx::Unlock.md)|Если модель потоков многопоточного, освобождает владельца объекта критической секции.|  
  
### Методы CComObjectRootBase  
  
|||  
|-|-|  
|[FinalConstruct](../Topic/CComObjectRootEx::FinalConstruct.md)|Переопределение в классе для выполнения любой инициализации должен быть объектом.|  
|[FinalRelease](../Topic/CComObjectRootEx::FinalRelease.md)|Переопределение в классе для выполнения любой очистки должен быть объектом.|  
|[OuterAddRef](../Topic/CComObjectRootEx::OuterAddRef.md)|Увеличивает счетчик ссылок для статистически вычислениеого объекта.|  
|[OuterQueryInterface](../Topic/CComObjectRootEx::OuterQueryInterface.md)|Делегаты к внешнему **IUnknown** объединенного объекта.|  
|[OuterRelease](../Topic/CComObjectRootEx::OuterRelease.md)|Уменьшает счетчик ссылок для статистически вычислениеого объекта.|  
  
### Статические функции  
  
|||  
|-|-|  
|[InternalQueryInterface](../Topic/CComObjectRootEx::InternalQueryInterface.md)|Делегаты в **IUnknown** nonaggregated объекта.|  
|[ObjectMain](../Topic/CComObjectRootEx::ObjectMain.md)|Вызывается во время инициализации и завершения модуля для производных классов, перечисленных в сопоставлении объекта.|  
  
### Элементы данных  
  
|||  
|-|-|  
|[m\_dwRef](../Topic/CComObjectRootEx::m_dwRef.md)|С `m_pOuterUnknown` часть соединения.  Используемый, когда объект не статистической обработки для хранения счетчика ссылок `AddRef` и **Выпуск**.|  
|[m\_pOuterUnknown](../Topic/CComObjectRootEx::m_pOuterUnknown.md)|С `m_dwRef` часть соединения.  Используемый, когда объект статистической обработки для хранения указатель на внешний неизвестный тип.|  
  
## Заметки  
 Элемент управления обрабатывает `CComObjectRootEx` count ссылки на объект и для nonaggregated и агрегированных объектов.  Он содержит счетчик ссылок на объект если объект не статистической обработки, и сохраняет указатель на внешний неизвестный, если объект статистической обработки.  Для агрегированных объектов, методы `CComObjectRootEx` могут быть использованы для обработки ошибка внутреннего объекта для проектирования и защитить внешний объект из удаления, если внутренние интерфейсы освобождены или внутренний объект удаляется.  
  
 Класс, реализующий сервер модели COM должен наследовать от `CComObjectRootEx` или [CComObjectRoot](../../atl/reference/ccomobjectroot-class.md).  
  
 Если определение класса определяет макрос [DECLARE\_POLY\_AGGREGATABLE](../Topic/DECLARE_POLY_AGGREGATABLE.md), то библиотеки ATL создает экземпляр **CComPolyObject\<CYourClass\>** при **IClassFactory::CreateInstance** вызываются.  Во время создания проверено значение внешнего неизвестным.  Если это **NULL**, то **IUnknown** реализуется для nonaggregated объекта.  Если внешний неизвестно не **NULL**, то **IUnknown** реализуется для статистически вычислениеого объекта.  
  
 Если класс не определяет макрос `DECLARE_POLY_AGGREGATABLE`, то библиотеки ATL создает экземпляр **CAggComObject\<CYourClass\>**, агрегированных объектов или экземпляр **CComObject\<CYourClass\>** для nonaggregated объектов.  
  
 Преимущество использования `CComPolyObject` что позволяет избежать `CComAggObject` и having и `CComObject` в модуле, чтобы настроить статистические и nonaggregated вариантов.  Один объект `CComPolyObject` обрабатывает оба варианта.  Поэтому только одна копия vtable и одна копия функций существуют в модуле.  Если в таблице vtable велико, это может значительно снизить свой размер модуля.  Однако если в таблице vtable мало, то с помощью `CComPolyObject` могут вызвать несколько более большом размере модуля, поскольку оно не оптимизироватьо для статистически вычислениеого или nonaggregated объекта, например `CComAggObject` и `CComObject`.  
  
 Если объект статистической обработки, то [IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509) реализуется `CComAggObject` или `CComPolyObject`.  Эти классы делегируют вызовы `QueryInterface`, `AddRef` и **Release** к `CComObjectRootEx``OuterQueryInterface`, `OuterAddRef` и `OuterRelease` для переадресации к внешнему неизвестному типу.  Обычно переопределяется `CComObjectRootEx::FinalConstruct` в вашем классе, чтобы создать все статистические объекты, и переопределите `CComObjectRootEx::FinalRelease`, чтобы освободить все статистические объекты.  
  
 Если объект не статистической обработки, то **IUnknown** реализуется `CComObject` или `CComPolyObject`.  В этом случае вызовы к `QueryInterface`, `AddRef` и **Release** делегируются к `CComObjectRootEx``InternalQueryInterface`, `InternalAddRef` и `InternalRelease` для выполнения фактических операций.  
  
## Требования  
 **Header:**  atlcom.h  
  
## См. также  
 [CComAggObject Class](../../atl/reference/ccomaggobject-class.md)   
 [CComObject Class](../../atl/reference/ccomobject-class.md)   
 [CComPolyObject Class](../../atl/reference/ccompolyobject-class.md)   
 [Class Overview](../../atl/atl-class-overview.md)