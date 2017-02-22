---
title: "CAtlAutoThreadModule Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "ATL.CAtlAutoThreadModule"
  - "CAtlAutoThreadModule"
  - "ATL::CAtlAutoThreadModule"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CAtlAutoThreadModule class"
ms.assetid: 3be834aa-55ef-403e-94ae-41979691b15f
caps.latest.revision: 19
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 22
---
# CAtlAutoThreadModule Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Этот класс реализует поток\- пул, сервер модели COM модели изоляции.  
  
> [!IMPORTANT]
>  Этот класс и его члены нельзя использовать в приложениях, выполняемых в этой среде выполнения Windows.  
  
## Синтаксис  
  
```  
  
      class CAtlAutoThreadModule :  
public CAtlAutoThreadModuleT< CAtlAutoThreadModule >  
```  
  
## Заметки  
 `CAtlAutoThreadModule` является производным от [CAtlAutoThreadModuleT](../../atl/reference/catlautothreadmodulet-class.md) и реализует поток\- пул, сервер модели COM модели изоляции.  `CAtlAutoThreadModule` использует [CComApartment](../../atl/reference/ccomapartment-class.md) для управления подразделение для каждого потока в модуле.  
  
 Необходимо использовать макрос [DECLARE\_CLASSFACTORY\_AUTO\_THREAD](../Topic/DECLARE_CLASSFACTORY_AUTO_THREAD.md) в определении класса объекта, чтобы определить [CComClassFactoryAutoThread](../../atl/reference/ccomclassfactoryautothread-class.md) как фабрика класса.  Затем необходимо добавить один экземпляр класса, производного от `CAtlAutoThreadModuleT` как `CAtlAutoThreadModule`.  Примеры.  
  
 `CAtlAutoThreadModule _AtlAutoModule; // name is immaterial.`  
  
> [!NOTE]
>  Этот класс заменяет класс [CComAutoThreadModule](../../atl/reference/ccomautothreadmodule-class.md) устарел.  
  
## Иерархия наследования  
 `IAtlAutoThreadModule`  
  
 [CAtlAutoThreadModuleT](../../atl/reference/catlautothreadmodulet-class.md)  
  
 `CAtlAutoThreadModule`  
  
## Требования  
 **Header:** atlbase.h  
  
## См. также  
 [CAtlAutoThreadModuleT Class](../../atl/reference/catlautothreadmodulet-class.md)   
 [IAtlAutoThreadModule Class](../../atl/reference/iatlautothreadmodule-class.md)   
 [Class Overview](../../atl/atl-class-overview.md)   
 [Модульные классы](../Topic/ATL%20Module%20Classes.md)