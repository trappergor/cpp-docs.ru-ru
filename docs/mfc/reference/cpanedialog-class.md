---
title: "CPaneDialog Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CPaneDialog"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CPaneDialog class"
  - "CPaneDialog constructor"
  - "CPaneDialog::CreateObject method"
  - "CPaneDialog::OnEraseBkgnd method"
  - "CPaneDialog::OnLButtonDblClk method"
  - "CPaneDialog::OnLButtonDown method"
  - "CPaneDialog::OnUpdateCmdUI method"
  - "CPaneDialog::OnWindowPosChanging method"
ms.assetid: 48a6bb91-4b92-40f5-8907-b3270b146cf6
caps.latest.revision: 27
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 28
---
# CPaneDialog Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Класс `CPaneDialog` поддерживает modeless, закрепляемая диалоговое окно.  
  
## Синтаксис  
  
```  
class CPaneDialog : public CDockablePane  
```  
  
## Члены  
  
### Открытые конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|`CPaneDialog::CPaneDialog`|Конструктор по умолчанию.|  
|`CPaneDialog::~CPaneDialog`|Деструктор.|  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[CPaneDialog::Create](../Topic/CPaneDialog::Create.md)|Создает вложение закрепляемая диалоговое окно и его к объекту `CPaneDialog`.|  
|`CPaneDialog::CreateObject`|Используемый платформой, чтобы создать динамический экземпляр этого типа класса.|  
|`CPaneDialog::GetThisClass`|Используемый платформой для получения указателя на объект [CRuntimeClass](../Topic/CRuntimeClass%20Structure.md), который связан с этим типом класса.|  
|[CPaneDialog::HandleInitDialog](../Topic/CPaneDialog::HandleInitDialog.md)|Обрабатывает сообщение [WM\_INITDIALOG](http://msdn.microsoft.com/library/windows/desktop/ms645428).  \(Переопределяет `CBasePane::HandleInitDialog`\).|  
|`CPaneDialog::OnEraseBkgnd`|Обрабатывает сообщение [WM\_ERASEBKGND](http://msdn.microsoft.com/library/windows/desktop/ms648055).  \(Переопределяет [CWnd::OnEraseBkgnd](../Topic/CWnd::OnEraseBkgnd.md)\).|  
|`CPaneDialog::OnLButtonDblClk`|Обрабатывает сообщение [WM\_LBUTTONDBLCLK](http://msdn.microsoft.com/library/windows/desktop/ms645606).  \(Переопределяет [CWnd::OnLButtonDblClk](../Topic/CWnd::OnLButtonDblClk.md)\).|  
|`CPaneDialog::OnLButtonDown`|Обрабатывает сообщение [WM\_LBUTTONDOWN](http://msdn.microsoft.com/library/windows/desktop/ms645607).  \(Переопределяет [CWnd::OnLButtonDown](../Topic/CWnd::OnLButtonDown.md)\).|  
|`CPaneDialog::OnUpdateCmdUI`|Вызываемый платформой для обновления диалоговое окно.  \(Переопределяет [CDockablePane::OnUpdateCmdUI](http://msdn.microsoft.com/ru-ru/5dd61606-1c12-40d4-b024-f3839aa5e2e0)\).|  
|`CPaneDialog::OnWindowPosChanging`|Обрабатывает сообщение [WM\_WINDOWPOSCHANGING](http://msdn.microsoft.com/library/windows/desktop/ms632653).  \(Переопределяет [CWnd::OnWindowPosChanging](../Topic/CWnd::OnWindowPosChanging.md)\).|  
|[CPaneDialog::SetOccDialogInfo](../Topic/CPaneDialog::SetOccDialogInfo.md)|Определяет шаблон для диалоговых окон, которое OLE контейнер элемента управления.|  
  
## Заметки  
 Создайте объект `CPaneDialog` в шаге 2.  Сначала создайте объект в коде.  Во\-вторых, вызов [CPaneDialog::Create](../Topic/CPaneDialog::Create.md).  Необходимо указать допустимый идентификатор имени шаблона ресурса или шаблона и передать указатель родительского окна.  В противном случае \- fail процесса создания.  Диалоговое окно должно определить стиль WS\_CHILD и WS\_VISIBLE.  Рекомендуется также указать стили WS\_CLIPCHILDREN и WS\_CLIPSIBLINGS.  Дополнительные сведения см. в разделе [Стили окна](../Topic/Window%20Styles.md).  
  
## Иерархия наследования  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CCmdTarget](../Topic/CCmdTarget%20Class.md)  
  
 [CWnd](../Topic/CWnd%20Class.md)  
  
 [CBasePane](../../mfc/reference/cbasepane-class.md)  
  
 [CPane](../../mfc/reference/cpane-class.md)  
  
 [CDockablePane](../Topic/CDockablePane%20Class.md)  
  
 [CPaneDialog](../../mfc/reference/cpanedialog-class.md)  
  
## Требования  
 **заголовок:** afxpanedialog.h  
  
## См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Классы](../Topic/MFC%20Classes.md)   
 [CDockablePane Class](../Topic/CDockablePane%20Class.md)   
 [Стили окна](../Topic/Window%20Styles.md)