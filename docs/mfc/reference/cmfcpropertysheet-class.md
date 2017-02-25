---
title: "CMFCPropertySheet Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CMFCPropertySheet"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCPropertySheet class"
  - "CMFCPropertySheet::OnInitDialog method"
  - "CMFCPropertySheet::PreTranslateMessage method"
ms.assetid: 01d93573-9698-440f-a6a4-5bebbee879dc
caps.latest.revision: 35
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 37
---
# CMFCPropertySheet Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Класс `CMFCPropertySheet` поддерживает таблицу свойств, каждая страница свойств в которой обозначается вкладкой, кнопкой панели инструментов, узлом элемента управления «Дерево» или элементом списка.  
  
## Синтаксис  
  
```  
class CMFCPropertySheet : public CPropertySheet  
```  
  
## Участники  
  
### Открытые конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|[CMFCPropertySheet::CMFCPropertySheet](../Topic/CMFCPropertySheet::CMFCPropertySheet.md)|Создает объект `CMFCPropertySheet`.|  
|`CMFCPropertySheet::~CMFCPropertySheet`|Деструктор.|  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[CMFCPropertySheet::AddPage](../Topic/CMFCPropertySheet::AddPage.md)|Добавляет страницу в таблицу свойств.|  
|[CMFCPropertySheet::AddPageToTree](../Topic/CMFCPropertySheet::AddPageToTree.md)|Добавляет новую страницу свойств в элемент управления «Дерево».|  
|[CMFCPropertySheet::AddTreeCategory](../Topic/CMFCPropertySheet::AddTreeCategory.md)|Добавляет новый узел в элемент управления «Дерево».|  
|[CMFCPropertySheet::EnablePageHeader](../Topic/CMFCPropertySheet::EnablePageHeader.md)|Резервирует место в верхней части каждой страницы для отрисовки пользовательского заголовка.|  
|[CMFCPropertySheet::GetHeaderHeight](../Topic/CMFCPropertySheet::GetHeaderHeight.md)|Получает высоту текущего заголовка.|  
|[CMFCPropertySheet::GetLook](../Topic/CMFCPropertySheet::GetLook.md)|Получает значение перечисления, указывающее внешний вид текущей таблицы свойств.|  
|[CMFCPropertySheet::GetNavBarWidth](../Topic/CMFCPropertySheet::GetNavBarWidth.md)|Получает ширину панели навигации в пикселях.|  
|[CMFCPropertySheet::GetTab](../Topic/CMFCPropertySheet::GetTab.md)|Получает внутренний объект набора вкладок, который поддерживает текущий элемент управления «Страница свойств».|  
|`CMFCPropertySheet::GetThisClass`|Используется платформой для получения указателя на объект [CRuntimeClass](../Topic/CRuntimeClass%20Structure.md), связанный с этим типом класса.|  
|[CMFCPropertySheet::InitNavigationControl](../Topic/CMFCPropertySheet::InitNavigationControl.md)|Инициализирует появление текущего элемента управления «Страница свойств».|  
|[CMFCPropertySheet::OnActivatePage](../Topic/CMFCPropertySheet::OnActivatePage.md)|Вызывается платформой при включении страницы свойств.|  
|[CMFCPropertySheet::OnDrawPageHeader](../Topic/CMFCPropertySheet::OnDrawPageHeader.md)|Вызывается платформой для отрисовки пользовательского заголовка страницы свойств.|  
|`CMFCPropertySheet::OnInitDialog`|Обрабатывает сообщение [WM\_INITDIALOG](http://msdn.microsoft.com/library/windows/desktop/ms645428).  \(Переопределяет [CPropertySheet::OnInitDialog](../Topic/CPropertySheet::OnInitDialog.md).\)|  
|[CMFCPropertySheet::OnRemoveTreePage](../Topic/CMFCPropertySheet::OnRemoveTreePage.md)|Вызывается платформой для удаления страницы свойств из элемента управления «Дерево».|  
|`CMFCPropertySheet::PreTranslateMessage`|Преобразует сообщения окна перед их диспетчеризацией в функции [TranslateMessage](http://msdn.microsoft.com/library/windows/desktop/ms644955) и [DispatchMessage](http://msdn.microsoft.com/library/windows/desktop/ms644934) Windows.  \(Переопределяет `CPropertySheet::PreTranslateMessage`.\)|  
|[CMFCPropertySheet::RemoveCategory](../Topic/CMFCPropertySheet::RemoveCategory.md)|Удаляет узел из элемента управления «Дерево».|  
|[CMFCPropertySheet::RemovePage](../Topic/CMFCPropertySheet::RemovePage.md)|Удаляет страницу свойств из таблицы свойств.|  
|[CMFCPropertySheet::SetIconsList](../Topic/CMFCPropertySheet::SetIconsList.md)|Указывает список изображений, используемых в элементе управления навигации панели Outlook.|  
|[CMFCPropertySheet::SetLook](../Topic/CMFCPropertySheet::SetLook.md)|Задает внешний вид таблицы свойств.|  
  
## Заметки  
 Класс `CMFCPropertySheet` представляет таблицы свойств, также называемые диалоговыми окнами с вкладками.  Класс `CMFCPropertySheet` может отображать страницу свойств различными способами.  
  
 Чтобы использовать класс `CMFCPropertySheet` в приложении, выполните следующие действия.  
  
1.  Создайте класс из класса `CMFCPropertySheet` и дайте ему имя, например CMyPropertySheet.  
  
2.  Постройте объект [CMFCPropertyPage](../../mfc/reference/cmfcpropertypage-class.md) для каждой страницы свойств.  
  
3.  Вызовите метод [CMFCPropertySheet::SetLook](../Topic/CMFCPropertySheet::SetLook.md) в конструкторе CMyPropertySheet.  Параметр этого метода указывает, что страницы свойств должны отображаться как вкладки вдоль верхней или левой стороны таблицы свойств, как вкладки в стиле таблицы свойств Microsoft OneNote свойств, как кнопки в элементе управления «Панель инструментов» Microsoft Outlook, как узлы дерева или как список элементов с левой стороны таблицы свойств.  
  
4.  Если вы создаете таблицу свойств в стиле панели инструментов Microsoft Outlook, вызовите метод [CMFCPropertySheet::SetIconsList](../Topic/CMFCPropertySheet::SetIconsList.md) для связывания списка изображений со страницами свойств.  
  
5.  Вызовите метод [CMFCPropertySheet::AddPage](../Topic/CMFCPropertySheet::AddPage.md) для каждой страницы свойств.  
  
6.  Создайте элемент управления `CMFCPropertySheet` и вызовите его метод `DoModal`.  
  
## Рисунки  
 На следующем рисунке показана таблица свойств в стиле встроенной панели инструментов Microsoft Outlook.  Панель инструментов Outlook отображается с левой стороны таблицы свойств.  
  
 ![Элементы управления цветов CMFCPropertySheet](../../mfc/reference/media/cmfcpropertysheet_color.png "cmfcpropertysheet\_color")  
  
 На следующем рисунке показана таблица свойств, которая содержит объект [CMFCPropertyGridCtrl Class](../../mfc/reference/cmfcpropertygridctrl-class.md).  Этот объект является таблицей свойств в стиле стандартной страницы свойств общих элементов управления.  
  
 ![Элементы управления свойств и списков CMFCPropertySheet](../../mfc/reference/media/cmfcpropertysheet_list.png "cmfcpropertysheet\_list")  
  
 На следующем рисунке показана таблица свойств в стиле элемента управления «Дерево».  
  
 ![Дерево свойства](../../mfc/reference/media/proptree.png "PropTree")  
  
## Иерархия наследования  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CCmdTarget](../Topic/CCmdTarget%20Class.md)  
  
 [CWnd](../Topic/CWnd%20Class.md)  
  
 [CPropertySheet](../../mfc/reference/cpropertysheet-class.md)  
  
 [CMFCPropertySheet](../../mfc/reference/cmfcpropertysheet-class.md)  
  
## Требования  
 **Заголовок:** afxpropertysheet.h  
  
## См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Классы](../Topic/MFC%20Classes.md)   
 [CMFCPropertyPage Class](../../mfc/reference/cmfcpropertypage-class.md)   
 [Класс CMFCOutlookBar](../../mfc/reference/cmfcoutlookbar-class.md)