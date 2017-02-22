---
title: "CComClassFactory Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "ATL.CComClassFactory"
  - "CComClassFactory"
  - "ATL::CComClassFactory"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CComClassFactory class"
ms.assetid: e56dacf7-d5c4-4c42-aef4-a86d91981a1b
caps.latest.revision: 20
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 23
---
# CComClassFactory Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Этот класс реализует интерфейс [IClassFactory](http://msdn.microsoft.com/library/windows/desktop/ms694364).  
  
## Синтаксис  
  
```  
  
   class CComClassFactory : public IClassFactory,   
public CComObjectRootEx< CComGlobalsThreadModel >  
```  
  
## Члены  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[CComClassFactory::CreateInstance](../Topic/CComClassFactory::CreateInstance.md)|Создает объект указанного идентификатора CLSID.|  
|[CComClassFactory::LockServer](../Topic/CComClassFactory::LockServer.md)|Блокирует фабрика класса в памяти.|  
  
## Заметки  
 `CComClassFactory` реализует интерфейс [IClassFactory](http://msdn.microsoft.com/library/windows/desktop/ms694364), содержащий методы для создания объекта заданного идентификатора CLSID, а также блокирует фабрика класса в памяти для новых объектов для создания быстрее.  **IClassFactory** должен быть реализован для каждого класса, который регистрируется в системном реестре и к которому можно присвоить CLSID.  
  
 Обычно объекты библиотеки ATL безо фабрику класса, производного от [CComCoClass](../Topic/CComCoClass%20Class.md).  Этот класс содержит макрос [DECLARE\_CLASSFACTORY](../Topic/DECLARE_CLASSFACTORY.md), который объявляет `CComClassFactory` по умолчанию как фабрика класса.  Чтобы переопределить это значение по умолчанию, укажите один из макросов `DECLARE_CLASSFACTORY`*XXX* в определении класса.  Например, макрос [DECLARE\_CLASSFACTORY\_EX](../Topic/DECLARE_CLASSFACTORY_EX.md) использует указанный класс для фабрики классов:  
  
 [!code-cpp[NVC_ATL_COM#8](../../atl/codesnippet/CPP/ccomclassfactory-class_1.h)]  
  
 Приведенное выше определение класса указывает, что **CMyClassFactory** будет использоваться как фабрика класса объекта по умолчанию.  **CMyClassFactory** должно быть производным от `CComClassFactory`, и переопределить `CreateInstance`.  
  
 Библиотеки ATL предоставляет 3 остальных макросов, объявляются фабрику класса:  
  
-   [DECLARE\_CLASSFACTORY2](../Topic/DECLARE_CLASSFACTORY2.md) использует [CComClassFactory2](../Topic/CComClassFactory2%20Class.md), который контролирует создание с помощью лицензию.  
  
-   [DECLARE\_CLASSFACTORY\_AUTO\_THREAD](../Topic/DECLARE_CLASSFACTORY_AUTO_THREAD.md) использует [CComClassFactoryAutoThread](../../atl/reference/ccomclassfactoryautothread-class.md), который создает объекты в нескольких подразделениях.  
  
-   [DECLARE\_CLASSFACTORY\_SINGLETON](../Topic/DECLARE_CLASSFACTORY_SINGLETON.md) использует [CComClassFactorySingleton](../../atl/reference/ccomclassfactorysingleton-class.md), который создает единственный объект [CComObjectGlobal](../../atl/reference/ccomobjectglobal-class.md).  
  
## Требования  
 **Header:**  atlcom.h  
  
## См. также  
 [CComObjectRootEx Class](../../atl/reference/ccomobjectrootex-class.md)   
 [CComGlobalsThreadModel](../Topic/CComGlobalsThreadModel.md)   
 [Class Overview](../../atl/atl-class-overview.md)