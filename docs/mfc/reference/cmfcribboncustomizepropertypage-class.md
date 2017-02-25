---
title: "CMFCRibbonCustomizePropertyPage Class | Microsoft Docs"
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
  - "CMFCRibbonCustomizePropertyPage::CreateObject"
  - "CMFCRibbonCustomizePropertyPage"
  - "CMFCRibbonCustomizePropertyPage::~CMFCRibbonCustomizePropertyPage"
  - "CMFCRibbonCustomizePropertyPage.GetThisClass"
  - "CMFCRibbonCustomizePropertyPage.CreateObject"
  - "~CMFCRibbonCustomizePropertyPage"
  - "CreateObject"
  - "CMFCRibbonCustomizePropertyPage.~CMFCRibbonCustomizePropertyPage"
  - "CMFCRibbonCustomizePropertyPage::GetThisClass"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "~CMFCRibbonCustomizePropertyPage destructor"
  - "CMFCRibbonCustomizePropertyPage class"
  - "CMFCRibbonCustomizePropertyPage class, деструктор"
  - "CreateObject method"
  - "GetThisClass method"
ms.assetid: ea32a99a-dfbe-401e-8975-aa191552532f
caps.latest.revision: 26
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 28
---
# CMFCRibbonCustomizePropertyPage Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Реализует пользовательскую страницу для диалогового окна **Настроить** в приложениях, основанных Лента\-.  
  
## Синтаксис  
  
```  
class CMFCRibbonCustomizePropertyPage: public CMFCPropertyPage  
```  
  
## Члены  
  
### Открытые конструкторы  
  
|||  
|-|-|  
|Имя|Описание|  
|[CMFCRibbonCustomizePropertyPage::CMFCRibbonCustomizePropertyPage](../Topic/CMFCRibbonCustomizePropertyPage::CMFCRibbonCustomizePropertyPage.md)|Создает объект `CMFCRibbonCustomizePropertyPage`.|  
|`CMFCRibbonCustomizePropertyPage::~CMFCRibbonCustomizePropertyPage`|Деструктор.|  
  
### Открытые методы  
  
|||  
|-|-|  
|Имя|Описание|  
|[CMFCRibbonCustomizePropertyPage::AddCustomCategory](../Topic/CMFCRibbonCustomizePropertyPage::AddCustomCategory.md)|Добавляет пользовательскую категорию в поле со списком **Команды**.|  
|`CMFCRibbonCustomizePropertyPage::CreateObject`|Используемый платформой, чтобы создать динамический экземпляр этого типа класса.|  
|`CMFCRibbonCustomizePropertyPage::GetThisClass`|Используемый платформой для получения указателя на объект [CRuntimeClass](../Topic/CRuntimeClass%20Structure.md), который связан с этим типом класса.|  
|[CMFCRibbonCustomizePropertyPage::OnOK](../Topic/CMFCRibbonCustomizePropertyPage::OnOK.md)|Вызывается системой, когда пользователь щелкает **ОК** в диалоговом окне **Настроить**.|  
  
## Заметки  
 Если необходимо добавить пользовательские команды к компоненту **Настроить**, необходимо обработать сообщение AFX\_WM\_ON\_RIBBON\_CUSTOMIZE.  В обработчике сообщений, создайте объект `CMFCRibbonCustomizePropertyPage` в стеке.  Создайте список пользовательских команд, и затем вызовите `AddCustomCategory` чтобы добавить новую страницу в диалоговое окно **Настроить**.  
  
## Пример  
 В следующем примере показано, как создать объект `CMFCRibbonCustomizePropertyPage` и добавить пользовательскую категорию.  
  
 [!code-cpp[NVC_MFC_RibbonApp#22](../../mfc/reference/codesnippet/CPP/cmfcribboncustomizepropertypage-class_1.cpp)]  
  
## Иерархия наследования  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CCmdTarget](../Topic/CCmdTarget%20Class.md)  
  
 [CWnd](../Topic/CWnd%20Class.md)  
  
 [CDialog](../../mfc/reference/cdialog-class.md)  
  
 [CPropertyPage](../../mfc/reference/cpropertypage-class.md)  
  
 [CMFCPropertyPage](../../mfc/reference/cmfcpropertypage-class.md)  
  
 [CMFCRibbonCustomizePropertyPage](../../mfc/reference/cmfcribboncustomizepropertypage-class.md)  
  
## Требования  
 **заголовок:** afxribboncustomizedialog.h  
  
## См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Классы](../Topic/MFC%20Classes.md)