---
title: "COleBusyDialog Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "COleBusyDialog"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "COleBusyDialog class"
  - "Server Busy dialog box"
  - "Server Not Responding dialog box"
ms.assetid: c881a532-9672-4c41-b51b-5ce4a7246a6b
caps.latest.revision: 22
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 24
---
# COleBusyDialog Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Общий для OLE\-сервер не отвечать или диалоговые окна занята сервера.  
  
## Синтаксис  
  
```  
class COleBusyDialog : public COleDialog  
```  
  
## Члены  
  
### Открытые конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|[COleBusyDialog::COleBusyDialog](../Topic/COleBusyDialog::COleBusyDialog.md)|Создает объект `COleBusyDialog`.|  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[COleBusyDialog::DoModal](../Topic/COleBusyDialog::DoModal.md)|Отображает диалоговое окно занята OLE\-сервер.|  
|[COleBusyDialog::GetSelectionType](../Topic/COleBusyDialog::GetSelectionType.md)|Определяет возможность завершивший в диалоговом окне.|  
  
### Открытые члены данных  
  
|Имя|Описание|  
|---------|--------------|  
|[COleBusyDialog::m\_bz](../Topic/COleBusyDialog::m_bz.md)|Структура типа **OLEUIBUSY**, который контролирует поведение диалогового окна.|  
  
## Заметки  
 Создайте объект класса `COleBusyDialog`, если нужно вызывать эти диалоговые окна.  После того как объект `COleBusyDialog` построен, можно использовать структуру [m\_bz](../Topic/COleBusyDialog::m_bz.md) для инициализации значений или состояния элементов управления в диалоговом окне.  Структура `m_bz` типа **OLEUIBUSY**.  Дополнительные сведения об использовании этого класса см. в описании функции\-члена диалогового окна [DoModal](../Topic/COleBusyDialog::DoModal.md).  
  
> [!NOTE]
>  Мастер\-, созданный приложением код контейнера использует этот класс.  
  
 Дополнительные сведения см. в разделе макет [OLEUIBUSY](http://msdn.microsoft.com/library/windows/desktop/ms682493) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 Дополнительные сведения о специальных диалоговых окнах OLE\- см. в статье [диалоговые окна в OLE](../../mfc/dialog-boxes-in-ole.md).  
  
## Иерархия наследования  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CCmdTarget](../Topic/CCmdTarget%20Class.md)  
  
 [CWnd](../Topic/CWnd%20Class.md)  
  
 [CDialog](../../mfc/reference/cdialog-class.md)  
  
 [CCommonDialog](../Topic/CCommonDialog%20Class.md)  
  
 [COleDialog](../../mfc/reference/coledialog-class.md)  
  
 `COleBusyDialog`  
  
## Требования  
 **Header:**  afxodlgs.h  
  
## См. также  
 [COleDialog Class](../../mfc/reference/coledialog-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [COleDialog Class](../../mfc/reference/coledialog-class.md)