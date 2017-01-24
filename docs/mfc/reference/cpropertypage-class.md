---
title: "CPropertyPage Class | Microsoft Docs"
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
  - "CPropertyPage"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CPropertyPage class"
  - "диалоговые окна, вкладки"
  - "страницы свойств, CPropertyPage class"
  - "диалоговые окна с вкладками"
ms.assetid: d9000a21-aa81-4530-85d9-f43432afb4dc
caps.latest.revision: 25
caps.handback.revision: 14
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CPropertyPage Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Представляет отдельные страницы свойств, иначе называемых диалоговое окно вкладки.  
  
## Синтаксис  
  
```  
class CPropertyPage : public CDialog  
```  
  
## Члены  
  
### Открытые конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|[CPropertyPage::CPropertyPage](../Topic/CPropertyPage::CPropertyPage.md)|Создает объект `CPropertyPage`.|  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[CPropertyPage::CancelToClose](../Topic/CPropertyPage::CancelToClose.md)|Изменяет кнопку ОК для чтения, и блокирует кнопку отмена, выберите неустранимая изменений на странице режимной страницы свойств.|  
|[CPropertyPage::Construct](../Topic/CPropertyPage::Construct.md)|Создает объект `CPropertyPage`.  Используйте `Construct` если требуется задать параметры во время выполнения или при использовании массивов.|  
|[CPropertyPage::GetPSP](../Topic/CPropertyPage::GetPSP.md)|Извлекает структуру Windows [PROPSHEETPAGE](http://msdn.microsoft.com/library/windows/desktop/bb774548), связанную с объектом `CPropertyPage`.|  
|[CPropertyPage::OnApply](../Topic/CPropertyPage::OnApply.md)|Вызываемый платформой, когда теперь застегивает нажмите кнопку применить.|  
|[CPropertyPage::OnCancel](../Topic/CPropertyPage::OnCancel.md)|Вызываемый платформой, если кнопка отмена будет нажата.|  
|[CPropertyPage::OnKillActive](../Topic/CPropertyPage::OnKillActive.md)|Вызываемый платформой, если текущая страница больше не является текущей страницы.  Выполните проверку данных.|  
|[CPropertyPage::OnOK](../Topic/CPropertyPage::OnOK.md)|Вызываемый платформой, когда ОК, применяется сейчас или кнопкой щелкните Закрыть.|  
|[CPropertyPage::OnQueryCancel](../Topic/CPropertyPage::OnQueryCancel.md)|Вызываемый платформой для кнопки отмена нажата и перед отменой выполняется.|  
|[CPropertyPage::OnReset](../Topic/CPropertyPage::OnReset.md)|Вызываемый платформой, если кнопка отмена будет нажата.|  
|[CPropertyPage::OnSetActive](../Topic/CPropertyPage::OnSetActive.md)|Вызываемый платформой, если страница будет сделана текущей страницей.|  
|[CPropertyPage::OnWizardBack](../Topic/CPropertyPage::OnWizardBack.md)|Вызываемый платформой, когда будет нажата кнопка назад во время использования страницы свойств мастер\- типа.|  
|[CPropertyPage::OnWizardFinish](../Topic/CPropertyPage::OnWizardFinish.md)|Вызываемый платформой, когда будет нажата кнопку готово при использовании страницу свойств мастер\- типа.|  
|[CPropertyPage::OnWizardNext](../Topic/CPropertyPage::OnWizardNext.md)|Вызываемый платформой, когда кнопка далее будет нажата при использовании страницу свойств мастер\- типа.|  
|[CPropertyPage::QuerySiblings](../Topic/CPropertyPage::QuerySiblings.md)|Переадресует сообщение на каждой странице страницы свойств.|  
|[CPropertyPage::SetModified](../Topic/CPropertyPage::SetModified.md)|Вызов, чтобы активировать применить сейчас или отключить застегивает.|  
  
### Открытые члены данных  
  
|Имя|Описание|  
|---------|--------------|  
|[CPropertyPage::m\_psp](../Topic/CPropertyPage::m_psp.md)|Структура Windows [PROPSHEETPAGE](http://msdn.microsoft.com/library/windows/desktop/bb774548).  Предоставляет доступ к основным параметры страницы свойств.|  
  
## Заметки  
 Как и в случае с стандартными диалоговыми окнами, необходимо создать производный класс от `CPropertyPage` для каждой страницы на странице свойств.  Для использования `CPropertyPage`\- производных объектов, сначала создайте объект [CPropertySheet](../../mfc/reference/cpropertysheet-class.md), а затем создайте объект для каждой страницы, которая переходит на страницу свойств.  Вызовите [CPropertySheet::AddPage](../Topic/CPropertySheet::AddPage.md) для каждой страницы на листе, а затем откройте страницу свойств путем вызова [CPropertySheet::DoModal](../Topic/CPropertySheet::DoModal.md) для режимной страницы свойств или немодального [CPropertySheet::Create](../Topic/CPropertySheet::Create.md) страницы свойств.  
  
 Можно создать тип диалогового окна " вкладки мастером, который состоит из страниц свойств с последовательностью страниц свойств, которые направляют пользователя через этапы операции, как настраивать устройство или создать газетную верстку.  В диалоговом окне страницы свойств вкладки мастер\- типа, не имеющих вкладки и только одна страница свойств видима одновременно.  Кроме того, вместо иметь ОК и применить сейчас кнопки " диалогового окна " вкладки мастер\- типа имеет кнопку назад или кнопку " отмена ", и завершения.  
  
 Дополнительные сведения об установке свойств см. страницу мастера. [CPropertySheet::SetWizardMode](../Topic/CPropertySheet::SetWizardMode.md).  Дополнительные сведения об использовании объектов `CPropertyPage` см. в статье [страницы свойств и страницы свойств](../../mfc/property-sheets-and-property-pages-in-mfc.md).  
  
## Иерархия наследования  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CCmdTarget](../Topic/CCmdTarget%20Class.md)  
  
 [CWnd](../Topic/CWnd%20Class.md)  
  
 [CDialog](../../mfc/reference/cdialog-class.md)  
  
 `CPropertyPage`  
  
## Требования  
 **Header:**  afxdlgs.h  
  
## См. также  
 [MFC просматривает CMNCTRL1](../../top/visual-cpp-samples.md)   
 [Образец CMNCTRL2 MFC](../../top/visual-cpp-samples.md)   
 [Образец PROPDLG MFC](../../top/visual-cpp-samples.md)   
 [Образец SNAPVW MFC](../../top/visual-cpp-samples.md)   
 [CDialog Class](../../mfc/reference/cdialog-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [CPropertySheet Class](../../mfc/reference/cpropertysheet-class.md)   
 [CDialog Class](../../mfc/reference/cdialog-class.md)   
 [CPropertySheet::SetWizardMode](../Topic/CPropertySheet::SetWizardMode.md)