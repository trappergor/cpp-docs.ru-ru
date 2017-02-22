---
title: "ICommandUI Interface | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "ICommandUI"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ICommandUI interface"
ms.assetid: 134afe8d-dcdf-47ca-857a-a166a6b665dd
caps.latest.revision: 24
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 26
---
# ICommandUI Interface
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Управляет команды пользовательского интерфейса.  
  
## Синтаксис  
  
```  
interface class ICommandUI  
```  
  
## Члены  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[ICommandUI::Check](../Topic/ICommandUI::Check.md)|Задает элемент пользовательского интерфейса для этой команды соответствующее состояние флажка.|  
|[ICommandUI::ContinueRouting](../Topic/ICommandUI::ContinueRouting.md)|Заставляет механизм маршрутизации команда\- продолжает перенаправления текущее сообщение на цепочки обработчиков.|  
|[ICommandUI::Enabled](../Topic/ICommandUI::Enabled.md)|Включение или отключение элемент пользовательского интерфейса для этой команды.|  
|[ICommandUI::ID](../Topic/ICommandUI::ID.md)|Возвращает идентификатор объекта пользовательского интерфейса, представленного объектом `ICommandUI`.|  
|[ICommandUI::Index](../Topic/ICommandUI::Index.md)|Возвращает индекс объекта пользовательского интерфейса, представленного объектом `ICommandUI`.|  
|[ICommandUI::Radio](../Topic/ICommandUI::Radio.md)|Задает элемент пользовательского интерфейса для этой команды соответствующее состояние флажка.|  
|[ICommandUI::Text](../Topic/ICommandUI::Text.md)|Задает текст элемента пользовательского интерфейса для этой команды.|  
  
## Заметки  
 Этот интерфейс предоставляет методы и свойства, которые управляют команды пользовательского интерфейса.  `ICommandUI` аналогично [CCmdUI Class](../Topic/CCmdUI%20Class.md), за исключением того, что `ICommandUI` используется для приложений MFC, которые взаимодействуют с компонентами .NET.  
  
 `ICommandUI` используется внутри обработчика в [ICommandTarget](../../mfc/reference/icommandtarget-interface.md)\- производный класс `ON_UPDATE_COMMAND_UI`.  Когда пользователь выбирает пункт, чтобы активировать приложения \(или\) меню, каждый пункт меню отображается как включать или отключен.  Целевой объект каждой команды меню предоставляет эти сведения с помощью реализации обработчика `ON_UPDATE_COMMAND_UI`.  Для каждого из объектов пользовательского интерфейса в приложении, используйте окно свойств, чтобы создать местозаполнитель записи и функции сообщение\- сопоставления для каждого обработчика.  
  
 Дополнительные сведения о том, как интерфейс `ICommandUI` используется для маршрутизации команд см. в разделе [Практическое руководство. Добавление маршрутизации команд в элемент управления Windows Forms](../../dotnet/how-to-add-command-routing-to-the-windows-forms-control.md).  
  
 Дополнительные сведения об использовании Windows Forms см. в разделе [Использование пользовательского элемента управления формы Windows Form в MFC](../../dotnet/using-a-windows-form-user-control-in-mfc.md).  
  
 Дополнительные сведения о том, как команды пользовательского интерфейса управляются в MFC см. в разделе [CCmdUI Class](../Topic/CCmdUI%20Class.md).  
  
## Требования  
 **заголовок:** afxwinforms.h \(определенный в сборке atlmfc\\lib\\mfcmifc80.dll\)  
  
## См. также  
 [CCmdUI Class](../Topic/CCmdUI%20Class.md)