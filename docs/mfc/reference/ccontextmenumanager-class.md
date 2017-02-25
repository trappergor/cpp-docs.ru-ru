---
title: "CContextMenuManager Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CContextMenuManager"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CContextMenuManager class"
ms.assetid: 1de20640-243c-47e1-85de-1baa4153bc83
caps.latest.revision: 32
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 33
---
# CContextMenuManager Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Объект `CContextMenuManager` управляет контекстные меню, также известные как контекстных меню.  
  
## Синтаксис  
  
```  
class CContextMenuManager : public CObject  
```  
  
## Члены  
  
### Открытые конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|[CContextMenuManager::CContextMenuManager](../Topic/CContextMenuManager::CContextMenuManager.md)|Создает объект `CContextMenuManager`.|  
|`CContextMenuManager::~CContextMenuManager`|Деструктор.|  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[CContextMenuManager::AddMenu](../Topic/CContextMenuManager::AddMenu.md)|Добавляет новое контекстное меню.|  
|[CContextMenuManager::GetMenuById](../Topic/CContextMenuManager::GetMenuById.md)|Возвращает дескриптор меню, связанный с предоставленным идентификатором ресурса|  
|[CContextMenuManager::GetMenuByName](../Topic/CContextMenuManager::GetMenuByName.md)|Возвращает дескриптор меню, соответствующее предоставленному имени меню.|  
|[CContextMenuManager::GetMenuNames](../Topic/CContextMenuManager::GetMenuNames.md)|Возвращает список имен меню.|  
|[CContextMenuManager::LoadState](../Topic/CContextMenuManager::LoadState.md)|Загружает контекстные меню, хранящийся в реестре Windows.|  
|[CContextMenuManager::ResetState](../Topic/CContextMenuManager::ResetState.md)|Очищает контекстные меню из диспетчера контекстного меню.|  
|[CContextMenuManager::SaveState](../Topic/CContextMenuManager::SaveState.md)|Сохраняет контекстные меню в реестр Windows.|  
|[CContextMenuManager::SetDontCloseActiveMenu](../Topic/CContextMenuManager::SetDontCloseActiveMenu.md)|Элементы управления, закроет ли `CContextMenuManager` активное контекстное меню, когда он указывает новое контекстное меню.|  
|[CContextMenuManager::ShowPopupMenu](../Topic/CContextMenuManager::ShowPopupMenu.md)|Отображает указанное контекстное меню.|  
|[CContextMenuManager::TrackPopupMenu](../Topic/CContextMenuManager::TrackPopupMenu.md)|Отображает указанное контекстное меню.  Возвращает индекс выбранной команды меню.|  
  
## Заметки  
 `CContextMenuManager` управляет контекстных меню и убедитесь в том, что они имеют согласованный вид.  
  
 Не следует создать объект `CContextMenuManager` вручную.  Границы приложения создают объект `CContextMenuManager`.  Однако необходимо вызвать [CWinAppEx::InitContextMenuManager](../Topic/CWinAppEx::InitContextMenuManager.md) когда приложение инициализируется.  После инициализации диспетчера контекста, используйте метод [CWinAppEx::GetContextMenuManager](../Topic/CWinAppEx::GetContextMenuManager.md) для получения указателя на диспетчер контекста для приложения.  
  
 Можно создать контекстные меню во время выполнения путем вызова `AddMenu`.  Если необходимо отображать меню без первого получения введенных пользователем данных, вызовите `ShowPopupMenu`.  `TrackPopupMenu` используется, когда требуется создать меню и ожидании ввода пользователя.  Возвращает индекс `TrackPopupMenu` выбранных команды или значение 0, если пользователь остается без выбрать все.  
  
 `CContextMenuManager` также может сохранять и загружать свое состояние в реестр Windows.  
  
## Пример  
 В следующем примере показано добавление меню на объект `CContextMenuManager` и как закрыть активное всплывающее меню, когда объект `CContextMenuManager` указывает новое всплывающее меню.  Этот фрагмент кода является частью [Пользовательский образец страниц](../../top/visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_CustomPages#4](../../mfc/reference/codesnippet/CPP/ccontextmenumanager-class_1.cpp)]  
  
## Иерархия наследования  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CContextMenuManager](../../mfc/reference/ccontextmenumanager-class.md)  
  
## Требования  
 **заголовок:** afxcontextmenumanager.h  
  
## См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Классы](../Topic/MFC%20Classes.md)   
 [CWinAppEx Class](../../mfc/reference/cwinappex-class.md)   
 [CWinAppEx::InitContextMenuManager](../Topic/CWinAppEx::InitContextMenuManager.md)