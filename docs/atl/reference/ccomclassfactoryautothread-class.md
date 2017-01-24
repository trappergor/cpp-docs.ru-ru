---
title: "CComClassFactoryAutoThread Class | Microsoft Docs"
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
  - "ATL::CComClassFactoryAutoThread"
  - "ATL.CComClassFactoryAutoThread"
  - "CComClassFactoryAutoThread"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CComClassFactoryAutoThread class"
ms.assetid: 22008042-533f-4dd9-bf7e-191ee571f9a1
caps.latest.revision: 21
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CComClassFactoryAutoThread Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Этот класс реализует интерфейс [IClassFactory](http://msdn.microsoft.com/library/windows/desktop/ms694364) и позволяет объектам, которые будут созданы в нескольких подразделениях.  
  
> [!IMPORTANT]
>  Этот класс и его члены нельзя использовать в приложениях, выполняемых в этой среде выполнения Windows.  
  
## Синтаксис  
  
```  
  
      class CComClassFactoryAutoThread : public IClassFactory,   
public CComObjectRootEx< CComGlobalsThreadModel >  
```  
  
## Члены  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[CComClassFactoryAutoThread::CreateInstance](../Topic/CComClassFactoryAutoThread::CreateInstance.md)|Создает объект указанного идентификатора CLSID.|  
|[CComClassFactoryAutoThread::LockServer](../Topic/CComClassFactoryAutoThread::LockServer.md)|Блокирует фабрика класса в памяти.|  
  
## Заметки  
 `CComClassFactoryAutoThread` аналогично [CComClassFactory](../../atl/reference/ccomclassfactory-class.md), но позволяет объектам, которые будут созданы в нескольких подразделениях.  Чтобы воспользоваться преимуществами этой поддержки, создайте класс, производный от [CComAutoThreadModule](../../atl/reference/ccomautothreadmodule-class.md) модуль EXE.  
  
 Обычно объекты библиотеки ATL безо фабрику класса, производного от [CComCoClass](../Topic/CComCoClass%20Class.md).  Этот класс содержит макрос [DECLARE\_CLASSFACTORY](../Topic/DECLARE_CLASSFACTORY.md), который объявляет [CComClassFactory](../../atl/reference/ccomclassfactory-class.md) по умолчанию как фабрика класса.  Для использования `CComClassFactoryAutoThread` укажите макрос [DECLARE\_CLASSFACTORY\_AUTO\_THREAD](../Topic/DECLARE_CLASSFACTORY_AUTO_THREAD.md) в определении класса объекта.  Примеры.  
  
 [!code-cpp[NVC_ATL_COM#9](../../atl/codesnippet/CPP/ccomclassfactoryautothread-class_1.h)]  
  
## Иерархия наследования  
 `CComObjectRootBase`  
  
 [CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md)  
  
 `IClassFactory`  
  
 `CComClassFactoryAutoThread`  
  
## Требования  
 **Header:**  atlcom.h  
  
## См. также  
 [IClassFactory](http://msdn.microsoft.com/library/windows/desktop/ms694364)   
 [CComClassFactory2 Class](../Topic/CComClassFactory2%20Class.md)   
 [CComClassFactorySingleton Class](../../atl/reference/ccomclassfactorysingleton-class.md)   
 [CComObjectRootEx Class](../../atl/reference/ccomobjectrootex-class.md)   
 [CComGlobalsThreadModel](../Topic/CComGlobalsThreadModel.md)   
 [Class Overview](../../atl/atl-class-overview.md)