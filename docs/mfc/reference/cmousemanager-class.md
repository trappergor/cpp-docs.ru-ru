---
title: "CMouseManager Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CMouseManager"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMouseManager class"
ms.assetid: a4d05017-4e44-4a40-8b57-4ece0de20481
caps.latest.revision: 26
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 28
---
# CMouseManager Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Позволяет пользователю командам связать с другим заданным объектом [CView](../Topic/CView%20Class.md), когда пользователь дважды щелкает внутри, просматривающие.  
  
## Синтаксис  
  
```  
class CMouseManager : public CObject  
```  
  
## Члены  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[CMouseManager::AddView](../Topic/CMouseManager::AddView.md)|Добавляет объект `CView` к компоненту **Настройка**.  Диалоговое окно **Настройка** позволяет пользователю связать дважды щелкнуть с командой для каждого из перечисленных представлений.|  
|[CMouseManager::GetViewDblClickCommand](../Topic/CMouseManager::GetViewDblClickCommand.md)|Возвращает команду, которая исполнена, когда пользователь дважды щелкает внутри предоставленный представление.|  
|[CMouseManager::GetViewIconId](../Topic/CMouseManager::GetViewIconId.md)|Возвращает значок, связанный с предоставленным идентификатором представления|  
|[CMouseManager::GetViewIdByName](../Topic/CMouseManager::GetViewIdByName.md)|Возвращает идентификатор представления, связанное с заданным именем представления.|  
|[CMouseManager::GetViewNames](../Topic/CMouseManager::GetViewNames.md)|Извлекает список всех добавляемых имен представлений.|  
|[CMouseManager::LoadState](../Topic/CMouseManager::LoadState.md)|Загружает состояние `CMouseManager` из реестра Windows.|  
|[CMouseManager::SaveState](../Topic/CMouseManager::SaveState.md)|Записывает состояние `CMouseManager` в реестр Windows.|  
|[CMouseManager::SetCommandForDblClk](../Topic/CMouseManager::SetCommandForDblClk.md)|Связывает предоставленная команду и предоставленное представление.|  
  
## Заметки  
 Класс `CMouseManager` поддерживает коллекцию объектов `CView`.  Каждое представление определяется именем и идентификатором.  Эти представления отображаются в диалоговом окне **Настройка**.  Пользователь может изменить команда, сопоставлена с представлением через диалоговое окно **Настройка**.  Связанная команда исполнена, когда пользователь дважды щелкает в этом представлении.  Для поддержки это с точки зрения написания кода, необходимо обработать сообщение `WM_LBUTTONDBLCLK` и вызов функции [CWinAppEx::OnViewDoubleClick](../Topic/CWinAppEx::OnViewDoubleClick.md) в коде для этого объекта `CView`.  
  
 Не следует создать объект `CMouseManager` вручную.  Для создания платформой приложения.  Он также будет удален автоматически при оставить пользователя приложения.  Получить указатель на него указателя мыши для приложения, вызов [CWinAppEx::GetMouseManager](../Topic/CWinAppEx::GetMouseManager.md).  
  
## Иерархия наследования  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CMouseManager](../../mfc/reference/cmousemanager-class.md)  
  
## Требования  
 **заголовок:** afxmousemanager.h  
  
## См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Классы](../Topic/MFC%20Classes.md)   
 [CWinAppEx Class](../../mfc/reference/cwinappex-class.md)   
 [Настройка мыши и клавиатуры](../../mfc/keyboard-and-mouse-customization.md)