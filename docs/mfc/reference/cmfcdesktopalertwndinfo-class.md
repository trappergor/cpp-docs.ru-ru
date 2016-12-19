---
title: "CMFCDesktopAlertWndInfo Class | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CMFCDesktopAlertWndInfo"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCDesktopAlertWndInfo class"
ms.assetid: 5c9bb84e-6c96-4748-8e74-6951b6ae8e84
caps.latest.revision: 26
caps.handback.revision: 14
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CMFCDesktopAlertWndInfo Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Класс `CMFCDesktopAlertWndInfo` используется с классом [CMFCDesktopAlertWnd Class](../../mfc/reference/cmfcdesktopalertwnd-class.md).  Он определяет элементы управления, которые отображаются, если окно предупреждения извлекает вверх.  
  
## Синтаксис  
  
```  
class CMFCDesktopAlertWndInfo  
```  
  
## Члены  
  
### Открытые конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|`CMFCDesktopAlertWndInfo::~CMFCDesktopAlertWndInfo`|Деструктор.|  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[CMFCDesktopAlertWndInfo::operator\=](../Topic/CMFCDesktopAlertWndInfo::operator=.md)||  
  
### Элементы данных  
  
|Имя|Описание|  
|---------|--------------|  
|[CMFCDesktopAlertWndInfo::m\_hIcon](../Topic/CMFCDesktopAlertWndInfo::m_hIcon.md)|Дескриптор для значка, который отображается.|  
|[CMFCDesktopAlertWndInfo::m\_nURLCmdID](../Topic/CMFCDesktopAlertWndInfo::m_nURLCmdID.md)|Идентификатор команды, связанное со ссылкой на поле предупреждения.|  
|[CMFCDesktopAlertWndInfo::m\_strText](../Topic/CMFCDesktopAlertWndInfo::m_strText.md)|Текст, отображаемый в окне предупреждения.|  
|[CMFCDesktopAlertWndInfo::m\_strURL](../Topic/CMFCDesktopAlertWndInfo::m_strURL.md)|Ссылку, которая отображается в окне предупреждения.|  
  
## Заметки  
 Класс `CMFCDesktopAlertWndInfo` передается методу [CMFCDesktopAlertWnd::Create](../Topic/CMFCDesktopAlertWnd::Create.md) для определения элементов, которые отображаются по умолчанию диалоговом окне предупреждения.  По умолчанию диалоговое окно может содержать 3 элемента:  
  
-   Значок, который устанавливается путем вызова [CMFCDesktopAlertWndInfo::m\_hIcon](../Topic/CMFCDesktopAlertWndInfo::m_hIcon.md).  
  
-   Метка или текст, устанавливаются путем вызова [CMFCDesktopAlertWndInfo::m\_strText](../Topic/CMFCDesktopAlertWndInfo::m_strText.md).  
  
-   Ссылка, которая устанавливается путем вызова [CMFCDesktopAlertWndInfo::m\_strURL](../Topic/CMFCDesktopAlertWndInfo::m_strURL.md).  Чтобы установить команду, которая исполнена когда ссылка нажата, вызовите [CMFCDesktopAlertWndInfo::m\_nURLCmdID](../Topic/CMFCDesktopAlertWndInfo::m_nURLCmdID.md).  
  
 По умолчанию если диалоговое окно недостаточно, можно создать пользовательское диалоговое окно, и передать его методу [CMFCDesktopAlertWnd::Create](../Topic/CMFCDesktopAlertWnd::Create.md) вместо этого класса.  Дополнительные сведения см. в разделе [CMFCDesktopAlertDialog Class](../../mfc/reference/cmfcdesktopalertdialog-class.md).  
  
## Пример  
 В следующем примере показано, как использовать различные члены в классе `CMFCDesktopAlertWndInfo`.  Примере показано, как установить дескриптор для значка, отображаемого, текст, отображаемый в окне предупреждения соединения, которая отображается в окне предупреждения и идентификатор команды, сопоставлено со ссылкой на поле предупреждения.  Данный пример является частью [Пример demo рабочего стола предупреждений](../../top/visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_DesktopAlertDemo#3](../../mfc/reference/codesnippet/CPP/cmfcdesktopalertwndinfo-class_1.cpp)]  
  
## Иерархия наследования  
 [CMFCDesktopAlertWndInfo](../../mfc/reference/cmfcdesktopalertwndinfo-class.md)  
  
## Требования  
 **заголовок:** afxDesktopAlertDialog.h  
  
## См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Классы](../Topic/MFC%20Classes.md)   
 [CMFCDesktopAlertWnd Class](../../mfc/reference/cmfcdesktopalertwnd-class.md)   
 [CMFCDesktopAlertWnd::Create](../Topic/CMFCDesktopAlertWnd::Create.md)   
 [CMFCDesktopAlertDialog Class](../../mfc/reference/cmfcdesktopalertdialog-class.md)