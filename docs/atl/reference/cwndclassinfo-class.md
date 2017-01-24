---
title: "CWndClassInfo Class | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CWndClassInfo"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CWndClassInfo class"
ms.assetid: c36fe7e1-75f1-4cf5-a06f-9f59c43fe6fb
caps.latest.revision: 22
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CWndClassInfo Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Этот класс содержит методы для регистрации сведений для класса окна.  
  
> [!IMPORTANT]
>  Этот класс и его члены нельзя использовать в приложениях, выполняемых в этой среде выполнения Windows.  
  
## Синтаксис  
  
```  
  
class CWndClassInfo  
  
```  
  
## Члены  
  
### Открытые методы  
  
|||  
|-|-|  
|[Регистрация](../Topic/CWndClassInfo::Register.md)|регистрирует класс окна.|  
  
### Элементы данных  
  
|||  
|-|-|  
|[m\_atom](../Topic/CWndClassInfo::m_atom.md)|Однозначно определяющее зарегистрированный класса окна.|  
|[m\_bSystemCursor](../Topic/CWndClassInfo::m_bSystemCursor.md)|Определяет, относится ли ресурс курсора до курсора системы или до курсора, содержащихся в ресурсе модуля.|  
|[m\_lpszCursorID](../Topic/CWndClassInfo::m_lpszCursorID.md)|Указывает имя ресурса курсора.|  
|[m\_lpszOrigName](../Topic/CWndClassInfo::m_lpszOrigName.md)|Содержит имя существующего класса окна.|  
|[m\_szAutoName](../Topic/CWndClassInfo::m_szAutoName.md)|Содержит библиотеку ATL\- созданное имя класса окна.|  
|[m\_wc](../Topic/CWndClassInfo::m_wc.md)|Хранит сведения о класса окна в структуре **WNDCLASSEX**.|  
|[pWndProc](../Topic/CWndClassInfo::pWndProc.md)|Указывает на процедуру окна существующего окна классифицируют.|  
  
## Заметки  
 `CWndClassInfo` управляет сведения класса окна.  Обычно используется `CWndClassInfo` через один из 3 макросов, `DECLARE_WND_CLASS`, `DECLARE_WND_CLASS_EX` или `DECLARE_WND_SUPERCLASS`, как описано в следующей таблице:  
  
|Макрос|Описание|  
|------------|--------------|  
|[DECLARE\_WND\_CLASS](../Topic/DECLARE_WND_CLASS.md)|`CWndClassInfo` регистрирует сведения для класса нового окна.|  
|[DECLARE\_WND\_CLASS\_EX](../Topic/DECLARE_WND_CLASS_EX.md)|Данные регистров `CWndClassInfo` для класса нового окна, включая параметры класса.|  
|[DECLARE\_WND\_SUPERCLASS](../Topic/DECLARE_WND_SUPERCLASS.md)|Данные регистров `CWndClassInfo` для класса окна, основанный на существующем классе, но используют другую процедуру окна.  Вызов этого метода superclassing.|  
  
 По умолчанию [CWindowImpl](../Topic/CWindowImpl%20Class.md) содержит макрос `DECLARE_WND_CLASS`, чтобы создать поле, основанную на классе нового окна.  DECLARE\_WND\_CLASS предоставляет стили по умолчанию и цвет фона для элемента управления.  Если необходимо самостоятельно определить стиль и цвет фона, наследуйте класс от `CWindowImpl` и включить макрос `DECLARE_WND_CLASS_EX` в определении класса.  
  
 Если требуется создать поле, основанный на существующем классе окна, наследуйте класс от `CWindowImpl` и включить макрос `DECLARE_WND_SUPERCLASS` в определении класса.  Примеры.  
  
 [!code-cpp[NVC_ATL_Windowing#43](../../atl/codesnippet/CPP/cwndclassinfo-class_1.h)]  
  
 Дополнительные сведения о классах окна см. в подразделе [классы окна](http://msdn.microsoft.com/library/windows/desktop/ms632596) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 Дополнительные сведения об использовании окон в библиотеке ATL см. в статье [Классы окна библиотеки ATL](../Topic/ATL%20Window%20Classes.md).  
  
## Требования  
 **Header:**  atlwin.h  
  
## См. также  
 [CComControl Class](../../atl/reference/ccomcontrol-class.md)   
 [Class Overview](../../atl/atl-class-overview.md)