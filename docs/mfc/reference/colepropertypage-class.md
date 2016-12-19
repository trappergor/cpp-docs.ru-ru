---
title: "COlePropertyPage Class | Microsoft Docs"
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
  - "COlePropertyPage"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "COlePropertyPage class"
  - "пользовательские элементы управления [MFC], свойства"
  - "displaying properties"
  - "OLE property pages"
  - "свойства [C++], отображение"
  - "страницы свойств, OLE"
ms.assetid: e9972872-8e6b-4550-905e-d36a274d64dc
caps.latest.revision: 23
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# COlePropertyPage Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Используемый для отображения свойств пользовательского элемента управления в графическом интерфейсе, аналогично диалоговому окну.  
  
## Синтаксис  
  
```  
class AFX_NOVTABLE COlePropertyPage : public CDialog  
```  
  
## Члены  
  
### Открытые конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|[COlePropertyPage::COlePropertyPage](../Topic/COlePropertyPage::COlePropertyPage.md)|Создает объект `COlePropertyPage`.|  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[COlePropertyPage::GetControlStatus](../Topic/COlePropertyPage::GetControlStatus.md)|Указывает, может ли пользователь изменил значение в элементе управления.|  
|[COlePropertyPage::GetObjectArray](../Topic/COlePropertyPage::GetObjectArray.md)|Возвращает массив объектов редактируемого страницей свойств.|  
|[COlePropertyPage::GetPageSite](../Topic/COlePropertyPage::GetPageSite.md)|Получает указатель на интерфейс `IPropertyPageSite` страницы свойств.|  
|[COlePropertyPage::IgnoreApply](../Topic/COlePropertyPage::IgnoreApply.md)|Определяет, какие элементы управления не включают кнопку применить.|  
|[COlePropertyPage::IsModified](../Topic/COlePropertyPage::IsModified.md)|Указывает, может ли пользователь изменил страницу свойств.|  
|[COlePropertyPage::OnEditProperty](../Topic/COlePropertyPage::OnEditProperty.md)|Вызываемый платформой, когда пользователь изменяет свойство.|  
|[COlePropertyPage::OnHelp](../Topic/COlePropertyPage::OnHelp.md)|Вызываемый платформой, когда пользователь вызывает справки.|  
|[COlePropertyPage::OnInitDialog](../Topic/COlePropertyPage::OnInitDialog.md)|Вызываемый платформой, когда страница свойств будет инициализирована.|  
|[COlePropertyPage::OnObjectsChanged](../Topic/COlePropertyPage::OnObjectsChanged.md)|Вызываемый платформой, когда будет выбрать другой элемент OLE управления с новыми свойствами.|  
|[COlePropertyPage::OnSetPageSite](../Topic/COlePropertyPage::OnSetPageSite.md)|Вызываемый платформой, когда фрейм свойства обеспечит сайт страницы.|  
|[COlePropertyPage::SetControlStatus](../Topic/COlePropertyPage::SetControlStatus.md)|Устанавливает пометить указывающее, является ли пользователь изменил значение в элементе управления.|  
|[COlePropertyPage::SetDialogResource](../Topic/COlePropertyPage::SetDialogResource.md)|Задает ресурс диалогового окна страницы свойств.|  
|[COlePropertyPage::SetHelpInfo](../Topic/COlePropertyPage::SetHelpInfo.md)|Устанавливает текст справки для страницы свойств краткое имя его файла справки и его контекст справки.|  
|[COlePropertyPage::SetModifiedFlag](../Topic/COlePropertyPage::SetModifiedFlag.md)|Устанавливает пометить указывающее, является ли пользователь изменил страницу свойств.|  
|[COlePropertyPage::SetPageName](../Topic/COlePropertyPage::SetPageName.md)|Задает имя страницы свойств \(заголовок\).|  
  
## Заметки  
 Например, страница свойств может включать элемент управления "Поле ввода", который позволяет пользователю просматривать и изменять свойства заголовка элемента управления.  
  
 Каждое пользовательское свойство или проверки наличия может иметь элемент управления диалогового окна, которое позволяет пользователю элемента управления для просмотра значений свойства и изменить это значение, если необходимо.  
  
 Дополнительные сведения об использовании `COlePropertyPage` см. в статье [Элементы управления ActiveX. страницы свойств](../../mfc/mfc-activex-controls-property-pages.md).  
  
## Иерархия наследования  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CCmdTarget](../Topic/CCmdTarget%20Class.md)  
  
 [CWnd](../Topic/CWnd%20Class.md)  
  
 [CDialog](../../mfc/reference/cdialog-class.md)  
  
 `COlePropertyPage`  
  
## Требования  
 **Header:**  afxctl.h  
  
## См. также  
 [MFC просматривает CIRC3](../../top/visual-cpp-samples.md)   
 [Образец TESTHELP MFC](../../top/visual-cpp-samples.md)   
 [CDialog Class](../../mfc/reference/cdialog-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [CDialog Class](../../mfc/reference/cdialog-class.md)