---
title: "CPropertySheet Class | Microsoft Docs"
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
  - "CPropertySheet"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CPropertySheet class"
  - "диалоговые окна, вкладки"
  - "страницы свойств, CPropertySheet class"
  - "диалоговые окна с вкладками"
ms.assetid: 8461ccff-d14f-46e0-a746-42ad642ef94e
caps.latest.revision: 30
caps.handback.revision: 19
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CPropertySheet Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Представляет страницы свойств, также известные как диалоговые окна " вкладки.  
  
## Синтаксис  
  
```  
class CPropertySheet : public CWnd  
```  
  
## Члены  
  
### Открытые конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|[CPropertySheet::CPropertySheet](../Topic/CPropertySheet::CPropertySheet.md)|Создает объект `CPropertySheet`.|  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[CPropertySheet::AddPage](../Topic/CPropertySheet::AddPage.md)|Добавляет страницу со страницей свойств.|  
|[CPropertySheet::Construct](../Topic/CPropertySheet::Construct.md)|Создает объект `CPropertySheet`.|  
|[CPropertySheet::Create](../Topic/CPropertySheet::Create.md)|Указывает страницу свойств modeless.|  
|[CPropertySheet::DoModal](../Topic/CPropertySheet::DoModal.md)|Указывает режимную страницу свойств.|  
|[CPropertySheet::EnableStackedTabs](../Topic/CPropertySheet::EnableStackedTabs.md)|Указывает, использует ли страница свойств вкладки с накоплением или прокрутки.|  
|[CPropertySheet::EndDialog](../Topic/CPropertySheet::EndDialog.md)|Завершает страница свойств.|  
|[CPropertySheet::GetActiveIndex](../Topic/CPropertySheet::GetActiveIndex.md)|Извлекает индекс текущей страницы свойств.|  
|[CPropertySheet::GetActivePage](../Topic/CPropertySheet::GetActivePage.md)|Возвращает объект текущей страницы.|  
|[CPropertySheet::GetPage](../Topic/CPropertySheet::GetPage.md)|Извлекает указатель на конкретной странице.|  
|[CPropertySheet::GetPageCount](../Topic/CPropertySheet::GetPageCount.md)|Возвращает количество страниц в странице свойств.|  
|[CPropertySheet::GetPageIndex](../Topic/CPropertySheet::GetPageIndex.md)|Возвращает индекс заданной страницы свойств.|  
|[CPropertySheet::GetTabControl](../Topic/CPropertySheet::GetTabControl.md)|Извлекает указатель на набор вкладок.|  
|[CPropertySheet::MapDialogRect](../Topic/CPropertySheet::MapDialogRect.md)|Преобразование единицы диалогового окна прямоугольника, чтобы экранировать единиц.|  
|[CPropertySheet::OnInitDialog](../Topic/CPropertySheet::OnInitDialog.md)|Переопределение, чтобы увеличить инициализации страницы свойств.|  
|[CPropertySheet::PressButton](../Topic/CPropertySheet::PressButton.md)|Имитирует выбор указанной кнопки на странице свойств.|  
|[CPropertySheet::RemovePage](../Topic/CPropertySheet::RemovePage.md)|Удаляет страницу из страницы свойств.|  
|[CPropertySheet::SetActivePage](../Topic/CPropertySheet::SetActivePage.md)|Программно задает объект текущей страницы.|  
|[CPropertySheet::SetFinishText](../Topic/CPropertySheet::SetFinishText.md)|Задает текст для кнопки готово.|  
|[CPropertySheet::SetTitle](../Topic/CPropertySheet::SetTitle.md)|Задает заголовок страницы свойств.|  
|[CPropertySheet::SetWizardButtons](../Topic/CPropertySheet::SetWizardButtons.md)|Включает кнопки мастера.|  
|[CPropertySheet::SetWizardMode](../Topic/CPropertySheet::SetWizardMode.md)|Включает режим работы мастера.|  
  
### Открытые члены данных  
  
|Имя|Описание|  
|---------|--------------|  
|[CPropertySheet::m\_psh](../Topic/CPropertySheet::m_psh.md)|Структура Windows [PROPSHEETHEADER](http://msdn.microsoft.com/library/windows/desktop/bb774546).  Предоставляет доступ к основным параметры страницы свойств.|  
  
## Заметки  
 Страница свойств состоит из объекта `CPropertySheet` и одного или нескольких объектов [CPropertyPage](../../mfc/reference/cpropertypage-class.md).  Границы отображаются как окно страницы свойств с параметром индекса табуляции и области, которая содержит выбранную в данный момент страницу.  Пользователь перемещается к определенной странице с помощью соответствующей вкладки.  
  
 `CPropertySheet` обеспечивает поддержку структуры развернутой [PROPSHEETHEADER](http://msdn.microsoft.com/library/windows/desktop/bb774546) появившейся в [!INCLUDE[Win98](../../mfc/reference/includes/win98_md.md)] и Windows NT 2000.  Структура содержит дополнительные флаги и члены, которые поддерживают использование растровое изображение фона "предела".  
  
 Для отображения этих новых образов автоматического в объекте страницы свойств, передайте допустимые значения для образов растрового изображения и цветов в вызове [CPropertySheet::Construct](../Topic/CPropertySheet::Construct.md) или [CPropertySheet::CPropertySheet](../Topic/CPropertySheet::CPropertySheet.md).  
  
 Даже если `CPropertySheet` не является производным от [CDialog](../../mfc/reference/cdialog-class.md), управлять объект `CPropertySheet` управлении объект `CDialog`.  Например, создание страницы свойств требует двухраздельной конструкции: вызовите конструктор, и затем вызовите [DoModal](../Topic/CPropertySheet::DoModal.md) для режимной страницы свойств или немодального [Создание](../Topic/CPropertySheet::Create.md) страницы свойств.  `CPropertySheet` существует 2 типа конструкторов: [CPropertySheet::Construct](../Topic/CPropertySheet::Construct.md) и [CPropertySheet::CPropertySheet](../Topic/CPropertySheet::CPropertySheet.md).  
  
 При создании объекта `CPropertySheet` некоторые [Стили окна](../Topic/Window%20Styles.md) может вызвать исключение перв\- вероятность произойти.  Это приводит к из системы при попытке изменить стиль страницы свойств, прежде чем его создания.  Чтобы избежать этого исключения, убедитесь, что установлено следующие стили при создании `CPropertySheet`:  
  
-   DS\_3DLOOK  
  
-   DS\_CONTROL  
  
-   WS\_CHILD  
  
-   WS\_TABSTOP  
  
 Следующие стили являются необязательными и не приведут к перв\- вероятность исключения:  
  
-   DS\_SHELLFONT  
  
-   DS\_LOCALEDIT  
  
-   WS\_CLIPCHILDREN  
  
 Любое другое `Window Styles` запрещено, а не следует включать их.  
  
 Обмен данными между объектом `CPropertySheet` и внешним объектом похожи на обмене данными с объектом `CDialog`.  Важное отличие заключается в том, что параметры страницы свойств обычно переменные\-члены объектов `CPropertyPage` вместо самого объекта `CPropertySheet`.  
  
 Можно создать тип диалогового окна " вкладки мастером, который состоит из страниц свойств с последовательностью страниц свойств, которые направляют пользователя через этапы операции, как настраивать устройство или создать газетную верстку.  В диалоговом окне страницы свойств вкладки мастер\- типа, не имеющих вкладки и только одна страница свойств видима одновременно.  Кроме того, вместо иметь **ОК** и кнопки **Применить** " диалогового окна " вкладки мастер\- типа имеется кнопка **Назад**, кнопку **Далее** или **Готово**, кнопку **Отмена** и кнопку **Справка**.  
  
 Чтобы создать диалоговое окно мастер\- типа, выполните те же шаги, которые необходимо выполнить, чтобы создать стандартную страница свойств только при вызове [SetWizardMode](../Topic/CPropertySheet::SetWizardMode.md) перед вызовом [DoModal](../Topic/CPropertySheet::DoModal.md).  Включение кнопки мастера, вызов [SetWizardButtons](../Topic/CPropertySheet::SetWizardButtons.md), используя флаги настраивать их функции и представления.  Включить кнопку **Готово**, вызов [SetFinishText](../Topic/CPropertySheet::SetFinishText.md) после того, как пользователь принимает действие на последней странице мастера.  
  
 Дополнительные сведения о том, как использовать объекты `CPropertySheet` см. в статье [страницы свойств и страницы свойств](../../mfc/property-sheets-and-property-pages-in-mfc.md).  Кроме того, Q146916 см. в статье базы знаний Майкрософт: Практическое руководство: Создайте modeless CPropertySheet со стандартными кнопками и статьей Q300606: Практическое руководство: Создание изменяемого размера страницы свойств MFC.  
  
## Иерархия наследования  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CCmdTarget](../Topic/CCmdTarget%20Class.md)  
  
 [CWnd](../Topic/CWnd%20Class.md)  
  
 `CPropertySheet`  
  
## Требования  
 **заголовок:** afxdlgs.h  
  
## См. также  
 [MFC просматривает CMNCTRL1](../../top/visual-cpp-samples.md)   
 [Образец CMNCTRL2 MFC](../../top/visual-cpp-samples.md)   
 [Образец PROPDLG MFC](../../top/visual-cpp-samples.md)   
 [Образец SNAPVW MFC](../../top/visual-cpp-samples.md)   
 [Класс CWnd](../Topic/CWnd%20Class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)