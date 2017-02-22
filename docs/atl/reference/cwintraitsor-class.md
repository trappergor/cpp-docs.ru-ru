---
title: "CWinTraitsOR Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "ATL.CWinTraitsOR"
  - "ATL::CWinTraitsOR"
  - "CWinTraitsOR"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CWinTraitsOR class"
  - "window styles, default values for ATL"
ms.assetid: 1eb7b1e8-a9bd-411b-a30a-35a8a10af989
caps.latest.revision: 20
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 23
---
# CWinTraitsOR Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Этот класс предоставляет метод для стандартизации, используемые стили создать объект окна.  
  
> [!IMPORTANT]
>  Этот класс и его члены нельзя использовать в приложениях, выполняемых в этой среде выполнения Windows.  
  
## Синтаксис  
  
```  
  
      template <  
DWORD t_dwStyle= 0,  
DWORDt_dwExStyle= 0,  
class TWinTraits = CControlWinTraits   
>  
class CWinTraitsOR  
```  
  
#### Параметры  
 `t_dwStyle`  
 По умолчанию стили окна.  
  
 `t_dwExStyle`  
 По умолчанию расширенные стили окна.  
  
## Члены  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[CWinTraitsOR::GetWndExStyle](../Topic/CWinTraitsOR::GetWndExStyle.md)|Получает расширенные стили для объекта `CWinTraitsOR`.|  
|[CWinTraitsOR::GetWndStyle](../Topic/CWinTraitsOR::GetWndStyle.md)|Получает стандартные стили для объекта `CWinTraitsOR`.|  
  
## Заметки  
 Этот класс [признаки окна](../../atl/understanding-window-traits.md) предоставляет простой метод для стандартизации стили, используемые для создания объекта окна библиотеки ATL.  Используйте специализацию этого класса в качестве параметра шаблона в [CWindowImpl](../Topic/CWindowImpl%20Class.md) или другой из классов окна библиотеки ATL для указания минимального набора стандартных и расширенных стилей, используемый для экземпляров этого класса окна.  
  
 Используйте специализацию данного шаблона, если требуется обеспечить, чтобы некоторые стили для всех установленных экземпляров класса окна позволяя при этом другие стили устанавливаться отдельно для в\- экземпляра в вызове [CWindowImpl::Create](../Topic/CWindowImpl::Create.md).  
  
 Если нужно обеспечить стили по умолчанию, то окна, которые будут использоваться, только если не заданы никакие другие стили в вызове `CWindowImpl::Create` используйте вместо [CWinTraits](../../atl/reference/cwintraits-class.md).  
  
## Требования  
 **Header:**  atlwin.h  
  
## См. также  
 [Class Overview](../../atl/atl-class-overview.md)   
 [Understanding Window Traits](../../atl/understanding-window-traits.md)