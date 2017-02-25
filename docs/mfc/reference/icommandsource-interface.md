---
title: "ICommandSource Interface | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "ICommandSource"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ICommandSource interface"
ms.assetid: a4b1f698-c09f-4ba8-9b13-0e74a0a4967e
caps.latest.revision: 24
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 26
---
# ICommandSource Interface
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Команды элементов управления, отправленные из исходного объекта команды к пользовательскому элементу управления.  
  
## Синтаксис  
  
```  
interface class ICommandSource  
```  
  
## Члены  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[ICommandSource::AddCommandHandler](../Topic/ICommandSource::AddCommandHandler.md)|Добавляет обработчик команд на исходный объект команды.|  
|[ICommandSource::AddCommandRangeHandler](../Topic/ICommandSource::AddCommandRangeHandler.md)|Добавляет группу в составе обработчики команды к исходному объекту команды.|  
|[ICommandSource::AddCommandRangeUIHandler](../Topic/ICommandSource::AddCommandRangeUIHandler.md)|Добавляет группу в составе обработчиков сообщений команды пользовательского интерфейса к исходному объекту команды.|  
|[ICommandSource::AddCommandUIHandler](../Topic/ICommandSource::AddCommandUIHandler.md)|Добавляет обработчик сообщений команды пользовательского интерфейса к исходному объекту команды.|  
|[ICommandSource::PostCommand](../Topic/ICommandSource::PostCommand.md)|Создает сообщение, не ожидая его для обработки.|  
|[ICommandSource::RemoveCommandHandler](../Topic/ICommandSource::RemoveCommandHandler.md)|Удаляет обработчик команд из исходного объекта команды.|  
|[ICommandSource::RemoveCommandRangeHandler](../Topic/ICommandSource::RemoveCommandRangeHandler.md)|Удаляет группу в составе обработчиков команд из исходного объекта команды.|  
|[ICommandSource::RemoveCommandRangeUIHandler](../Topic/ICommandSource::RemoveCommandRangeUIHandler.md)|Удаляет группу в составе обработчиков сообщений команды пользовательского интерфейса из исходного объекта команды.|  
|[ICommandSource::RemoveCommandUIHandler](../Topic/ICommandSource::RemoveCommandUIHandler.md)|Удаляет обработчик сообщений команды пользовательского интерфейса из исходного объекта команды.|  
|[ICommandSource::SendCommand](../Topic/ICommandSource::SendCommand.md)|Отправляет сообщение и ждет, обрабатываемых перед возвратом.|  
  
## Заметки  
 При хозяйничаете пользовательский элемент управления в виде MFC, [CWinFormsView Class](../../mfc/reference/cwinformsview-class.md) направляет команды и сообщения пользовательского интерфейса команды обновления к пользовательскому элементу управления разрешить его для обработки команд MFC \(например, пункты меню и кнопки панели инструментов\).  Путем реализации [ICommandTarget Interface](../../mfc/reference/icommandtarget-interface.md), предоставляемые пользовательскому элементу управления ссылку на объект `ICommandSource`.  
  
 Пример использования `ICommandTarget` см. в разделе [Практическое руководство. Добавление маршрутизации команд в элемент управления Windows Forms](../../dotnet/how-to-add-command-routing-to-the-windows-forms-control.md).  
  
 Дополнительные сведения об использовании Windows Forms см. в разделе [Использование пользовательского элемента управления формы Windows Form в MFC](../../dotnet/using-a-windows-form-user-control-in-mfc.md).  
  
## Требования  
 **заголовок:** afxwinforms.h \(определенный в сборке atlmfc\\lib\\mfcmifc80.dll\)  
  
## См. также  
 [Практическое руководство. Добавление маршрутизации команд в элемент управления Windows Forms](../../dotnet/how-to-add-command-routing-to-the-windows-forms-control.md)   
 [ICommandTarget Interface](../../mfc/reference/icommandtarget-interface.md)