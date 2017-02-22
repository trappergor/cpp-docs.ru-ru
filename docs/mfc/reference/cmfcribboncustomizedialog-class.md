---
title: "CMFCRibbonCustomizeDialog Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "GetThisClass"
  - "CMFCRibbonCustomizeDialog"
  - "~CMFCRibbonCustomizeDialog"
  - "CMFCRibbonCustomizeDialog::GetThisClass"
  - "CMFCRibbonCustomizeDialog.~CMFCRibbonCustomizeDialog"
  - "CMFCRibbonCustomizeDialog.GetThisClass"
  - "CMFCRibbonCustomizeDialog::~CMFCRibbonCustomizeDialog"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "~CMFCRibbonCustomizeDialog destructor"
  - "CMFCRibbonCustomizeDialog class"
  - "CMFCRibbonCustomizeDialog class, деструктор"
  - "GetThisClass method"
ms.assetid: ce67de7f-5eaa-4c75-9b94-f290f36df073
caps.latest.revision: 22
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 24
---
# CMFCRibbonCustomizeDialog Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Отображает страницу **Настроить** ленты.  
  
## Синтаксис  
  
```  
class CMFCRibbonCustomizeDialog : public CMFCPropertySheet  
```  
  
## Члены  
  
### Открытые конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|[CMFCRibbonCustomizeDialog::CMFCRibbonCustomizeDialog](../Topic/CMFCRibbonCustomizeDialog::CMFCRibbonCustomizeDialog.md)|Создает объект `CMFCRibbonCustomizeDialog`.|  
|`CMFCRibbonCustomizeDialog::~CMFCRibbonCustomizeDialog`|Деструктор.|  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|`CMFCRibbonCustomizeDialog::GetThisClass`|Используемый платформой для получения указателя на объект [CRuntimeClass](../Topic/CRuntimeClass%20Structure.md), который связан с этим типом класса.|  
  
## Заметки  
 Создает MFC этот класс автоматически, если сообщение не обрабатывается AFX\_WM\_ON\_RIBBON\_CUSTOMIZE или если возвращается 0 из обработчика сообщений.  
  
 Если требуется использовать этот класс в приложении отобразить диалоговое окно **Настроить** ленты, как создать его экземпляр, и вызвать метод `DoModal`.  
  
 Поскольку этот класс является производным от [CMFCPropertySheet Class](../../mfc/reference/cmfcpropertysheet-class.md) можно добавить пользовательские страницы с помощью api\-интерфейса `CMFCPropertySheet`.  
  
## Иерархия наследования  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CCmdTarget](../Topic/CCmdTarget%20Class.md)  
  
 [CWnd](../Topic/CWnd%20Class.md)  
  
 [CPropertySheet](../../mfc/reference/cpropertysheet-class.md)  
  
 [CMFCPropertySheet](../../mfc/reference/cmfcpropertysheet-class.md)  
  
 [CMFCRibbonCustomizeDialog](../../mfc/reference/cmfcribboncustomizedialog-class.md)  
  
## Требования  
 **заголовок:** afxribboncustomizedialog.h  
  
## См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Классы](../Topic/MFC%20Classes.md)