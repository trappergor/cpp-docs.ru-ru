---
title: "IAtlAutoThreadModule Class | Microsoft Docs"
ms.custom: ""
ms.date: "12/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "IAtlAutoThreadModule"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "IAtlAutoThreadModule class"
ms.assetid: fcb58cf9-a427-4be9-89eb-04e1ab5cc3a1
caps.latest.revision: 18
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# IAtlAutoThreadModule Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Этот класс представляет интерфейс методу `CreateInstance`.  
  
> [!IMPORTANT]
>  Этот класс и его члены нельзя использовать в приложениях, выполняемых в [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)].  
  
## Синтаксис  
  
```  
  
__interface IAtlAutoThreadModule  
  
```  
  
## Заметки  
 Класс [CAtlAutoThreadModuleT](../../atl/reference/catlautothreadmodulet-class.md) является производным от `IAtlAutoThreadModule`, используя его, чтобы предоставить код для создания объекта и получения указателя интерфейса.  
  
## Требования  
 **Header:** atlbase.h  
  
## См. также  
 [Class Overview](../../atl/atl-class-overview.md)