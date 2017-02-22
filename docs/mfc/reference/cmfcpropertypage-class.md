---
title: "CMFCPropertyPage Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CMFCPropertyPage"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCPropertyPage class"
  - "CMFCPropertyPage::CreateObject method"
  - "CMFCPropertyPage::OnSetActive method"
  - "CMFCPropertyPage::PreTranslateMessage method"
ms.assetid: d279d7f2-2d81-418d-9f23-6147d6e8df09
caps.latest.revision: 30
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 32
---
# CMFCPropertyPage Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Класс `CMFCPropertyPage` поддерживает отображение всплывающих меню на странице свойств.  
  
## Синтаксис  
  
```  
class CMFCPropertyPage : public CPropertyPage  
```  
  
## Члены  
  
### Открытые конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|[CMFCPropertyPage::CMFCPropertyPage](../Topic/CMFCPropertyPage::CMFCPropertyPage.md)|Создает объект `CMFCPropertyPage`.|  
|`CMFCPropertyPage::~CMFCPropertyPage`|Деструктор.|  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|`CMFCPropertyPage::CreateObject`|Используемый платформой, чтобы создать динамический экземпляр этого типа класса.|  
|`CMFCPropertyPage::GetThisClass`|Используемый платформой для получения указателя на объект [CRuntimeClass](../Topic/CRuntimeClass%20Structure.md), который связан с этим типом класса.|  
|`CMFCPropertyPage::OnSetActive`|Функция\-член вызывается инфраструктурой при этом страница выбрана пользователем и становится текущей страницей.  \(Переопределяет [CPropertyPage::OnSetActive](../Topic/CPropertyPage::OnSetActive.md)\).|  
|`CMFCPropertyPage::PreTranslateMessage`|Преобразует сообщения окна до их посланы к функциям [TranslateMessage](http://msdn.microsoft.com/library/windows/desktop/ms644955) и [DispatchMessage](http://msdn.microsoft.com/library/windows/desktop/ms644934) Windows.  Дополнительные сведения и синтаксиса методов см. в разделе [CWnd::PreTranslateMessage](../Topic/CWnd::PreTranslateMessage.md).  \(Переопределяет `CPropertyPage::PreTranslateMessage`\).|  
  
## Заметки  
 Класс `CMFCPropertyPage` представляет отдельные страницы свойств, иначе называемых диалоговое окно вкладки.  
  
 Используйте класс `CMFCPropertyPage` вместе с классом [CMFCPropertySheet](../../mfc/reference/cmfcpropertysheet-class.md).  Для использования меню на странице свойств замените все вхождения класса `CPropertyPage` с классом `CMFCPropertyPage`.  
  
## Иерархия наследования  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CCmdTarget](../Topic/CCmdTarget%20Class.md)  
  
 [CWnd](../Topic/CWnd%20Class.md)  
  
 [CDialog](../../mfc/reference/cdialog-class.md)  
  
 [CPropertyPage](../../mfc/reference/cpropertypage-class.md)  
  
 [CMFCPropertyPage](../../mfc/reference/cmfcpropertypage-class.md)  
  
## Требования  
 **заголовок:** afxpropertypage.h  
  
## См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Классы](../Topic/MFC%20Classes.md)   
 [CMFCPropertySheet Class](../../mfc/reference/cmfcpropertysheet-class.md)