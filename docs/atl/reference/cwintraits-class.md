---
title: "CWinTraits Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CWinTraits"
  - "CMDIChildWinTraits"
  - "ATL.CWinTraits"
  - "CFrameWinTraits"
  - "ATL::CWinTraits"
  - "CControlWinTraits"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CControlWinTraits class"
  - "CFrameWinTraits class"
  - "CMDIChildWinTraits class"
  - "CWinTraits class"
  - "window styles, default values for ATL"
ms.assetid: f78f486e-6d9c-42c6-8e86-371e05aa7e59
caps.latest.revision: 19
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 22
---
# CWinTraits Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Этот класс предоставляет метод для стандартизации, используемые стили создать объект окна.  
  
> [!IMPORTANT]
>  Этот класс и его члены нельзя использовать в приложениях, выполняемых в этой среде выполнения Windows.  
  
## Синтаксис  
  
```  
  
      template <  
DWORD t_dwStyle= 0,  
DWORD t_dwExStyle= 0  
>  
class CWinTraits  
```  
  
#### Параметры  
 `t_dwStyle`  
 По умолчанию стандартные стили окна.  
  
 `t_dwExStyle`  
 По умолчанию расширенные стили окна.  
  
## Члены  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[CWinTraits::GetWndExStyle](../Topic/CWinTraits::GetWndExStyle.md)|\(Статический\) Извлекает расширенные стили для объекта `CWinTraits`.|  
|[CWinTraits::GetWndStyle](../Topic/CWinTraits::GetWndStyle.md)|\(Статический\) Извлекает стандартные стили для объекта `CWinTraits`.|  
  
## Заметки  
 Этот класс [признаки окна](../../atl/understanding-window-traits.md) предоставляет простой метод для стандартизации стили, используемые для создания объекта окна библиотеки ATL.  Используйте специализацию этого класса в качестве параметра шаблона в [CWindowImpl](../Topic/CWindowImpl%20Class.md) или другой из классов окна библиотеки ATL для указания по умолчанию стандартные и расширенные стили, используемые для экземпляров этого класса окна.  
  
 Используйте этот шаблон, если необходимо предоставить по умолчанию стили окна, которые будут использоваться только при отсутствии других стилей не определены в вызове [CWindowImpl::Create](../Topic/CWindowImpl::Create.md).  
  
 Библиотеки ATL предоставляет 3 стандартных специализации этого шаблона для часто используемых стилей окна " сочетания:  
  
 `CControlWinTraits`  
 Разработанные для стандартного окна элемента управления.  Следующие стандартные стили используются: **WS\_CHILD**, **WS\_VISIBLE**, **WS\_CLIPCHILDREN** и **WS\_CLIPSIBLINGS**.  Нет расширенные стили.  
  
 `CFrameWinTraits`  
 Разработанные для стандартного фреймового окна.  Стандартные, используемые стили: **WS\_OVERLAPPEDWINDOW**, **WS\_CLIPCHILDREN** и **WS\_CLIPSIBLINGS**.  Расширенные, используемые стили: **WS\_EX\_APPWINDOW** и **WS\_EX\_WINDOWEDGE**.  
  
 `CMDIChildWinTraits`  
 Разработанные для стандартного дочернего окна MDI.  Стандартные, используемые стили: **WS\_OVERLAPPEDWINDOW**, **WS\_CHILD**, **WS\_VISIBLE**, **WS\_CLIPCHILDREN** и **WS\_CLIPSIBLINGS**.  Расширенные, используемые стили: **WS\_EX\_MDICHILD**.  
  
 Если необходимо убедиться, что некоторые стили для всех установленных экземпляров класса окна позволяя при этом другие стили быть установлен для каждого в\- экземпляра используется [CWinTraitsOR](../../atl/reference/cwintraitsor-class.md).  
  
## Требования  
 **Header:**  atlwin.h  
  
## См. также  
 [Class Members](http://msdn.microsoft.com/ru-ru/dbe6a147-3f01-4aea-a3fb-fe6ebadc31f8)   
 [Class Overview](../../atl/atl-class-overview.md)   
 [Understanding Window Traits](../../atl/understanding-window-traits.md)