---
title: "CMFCTabCtrl Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CMFCTabCtrl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCTabCtrl class"
  - "CMFCTabCtrl constructor"
  - "CMFCTabCtrl::GetTabFromPoint method"
  - "CMFCTabCtrl::IsPtInTabArea method"
  - "CMFCTabCtrl::MoveTab method"
  - "CMFCTabCtrl::PreTranslateMessage method"
  - "CMFCTabCtrl::RecalcLayout method"
  - "CMFCTabCtrl::SwapTabs method"
ms.assetid: d441385d-2c72-4203-96fa-deae2273da35
caps.latest.revision: 33
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 35
---
# CMFCTabCtrl Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Класс `CMFCTabCtrl` предоставляет функциональные возможности для набора вкладок.  Набор вкладок указывает закрепляемое окно с вкладками неструктурированными или трехмерными в его верхней или нижней части.  Вкладки могут отображать текст и изображение и могут изменить цвет, когда активны.  
  
## Синтаксис  
  
```  
class CMFCTabCtrl : public CMFCBaseTabCtrl  
```  
  
## Члены  
  
### Открытые конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|`CMFCTabCtrl::CMFCTabCtrl`|Конструктор по умолчанию.|  
|`CMFCTabCtrl::~CMFCTabCtrl`|Деструктор.|  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[CMFCTabCtrl::ActivateMDITab](../Topic/CMFCTabCtrl::ActivateMDITab.md)|Отображает указанную вкладку текущем наборе вкладок и устанавливает фокус на этой вкладке.|  
|[CMFCTabCtrl::AllowDestroyEmptyTabbedPane](../Topic/CMFCTabCtrl::AllowDestroyEmptyTabbedPane.md)||  
|[CMFCTabCtrl::AutoSizeWindow](../Topic/CMFCTabCtrl::AutoSizeWindow.md)|Определяет, является ли размер границы клиентской области всех окон набор вкладок, когда элемент пользовательского интерфейса изменений набора вкладок.|  
|[CMFCTabCtrl::CalcRectEdit](../Topic/CMFCTabCtrl::CalcRectEdit.md)|Выкачивает размер заданной области вкладок.  \(Переопределяет `CMFCBaseTabCtrl::CalcRectEdit`\).|  
|[CMFCTabCtrl::Create](../Topic/CMFCTabCtrl::Create.md)|Создает набор вкладок и вложение его к объекту `CMFCTabCtrl`.|  
|`CMFCTabCtrl::CreateObject`|Используемый платформой, чтобы создать динамический экземпляр этого типа класса.|  
|[CMFCTabCtrl::EnableActiveTabCloseButton](../Topic/CMFCTabCtrl::EnableActiveTabCloseButton.md)|Показывает или скрывает кнопку Закрыть \(**X**\) на активной вкладке.|  
|[CMFCTabCtrl::EnableInPlaceEdit](../Topic/CMFCTabCtrl::EnableInPlaceEdit.md)|Включение или отключение редактируемые метки вкладки.  \(Переопределяет [CMFCBaseTabCtrl::EnableInPlaceEdit](../Topic/CMFCBaseTabCtrl::EnableInPlaceEdit.md)\).|  
|[CMFCTabCtrl::EnableTabDocumentsMenu](../Topic/CMFCTabCtrl::EnableTabDocumentsMenu.md)|Заменяет 2 кнопки, прокручивают вкладки окна с кнопкой, открытие меню нашитых windows.|  
|[CMFCTabCtrl::EnsureVisible](../Topic/CMFCTabCtrl::EnsureVisible.md)|Гарантирует, что вкладка видима.|  
|[CMFCTabCtrl::GetDocumentIcon](../Topic/CMFCTabCtrl::GetDocumentIcon.md)|Получает символ, который связан с вкладкой в всплывающем меню нашитых windows.|  
|[CMFCTabCtrl::GetFirstVisibleTabNum](../Topic/CMFCTabCtrl::GetFirstVisibleTabNum.md)|Получает индекс первой вкладки, которая отображается в текущем наборе вкладок.|  
|[CMFCTabCtrl::GetResizeMode](../Topic/CMFCTabCtrl::GetResizeMode.md)|Извлекает значение, указывающее, как текущий набор вкладок возможность изменения размера.|  
|[CMFCTabCtrl::GetScrollBar](../Topic/CMFCTabCtrl::GetScrollBar.md)|Извлекает указатель на объект полосы прокрутки, который связан с набором вкладок.|  
|[CMFCTabCtrl::GetTabArea](../Topic/CMFCTabCtrl::GetTabArea.md)|Получает ограничивающий прямоугольник области метки вкладки в верхней или нижней части набора вкладок.  \(Переопределяет [CMFCBaseTabCtrl::GetTabArea](../Topic/CMFCBaseTabCtrl::GetTabArea.md)\).|  
|`CMFCTabCtrl::GetTabFromPoint`|Извлекает вкладку, которая содержит указанную точку.  \(Переопределяет [CMFCBaseTabCtrl::GetTabFromPoint](../Topic/CMFCBaseTabCtrl::GetTabFromPoint.md)\).|  
|[CMFCTabCtrl::GetTabMaxWidth](../Topic/CMFCTabCtrl::GetTabMaxWidth.md)|Получает максимальную ширину вкладок.|  
|[CMFCTabCtrl::GetTabsHeight](../Topic/CMFCTabCtrl::GetTabsHeight.md)|Получает высоту области вкладки текущего набора вкладок.|  
|[CMFCTabCtrl::GetTabsRect](../Topic/CMFCTabCtrl::GetTabsRect.md)|Получает прямоугольник, прыгает область вкладки текущего набора вкладок.  \(Переопределяет [CMFCBaseTabCtrl::GetTabsRect](../Topic/CMFCBaseTabCtrl::GetTabsRect.md)\).|  
|`CMFCTabCtrl::GetThisClass`|Используемый платформой для получения указателя на объект [CRuntimeClass](../Topic/CRuntimeClass%20Structure.md), который связан с этим типом класса.|  
|[CMFCTabCtrl::GetWndArea](../Topic/CMFCTabCtrl::GetWndArea.md)|Извлекает границей клиентской области текущего набора вкладок.|  
|[CMFCTabCtrl::HideActiveWindowHorzScrollBar](../Topic/CMFCTabCtrl::HideActiveWindowHorzScrollBar.md)|Скрывает горизонтальная полоса прокрутки, если таковые имеются, активного окна.|  
|[CMFCTabCtrl::HideInactiveWindow](../Topic/CMFCTabCtrl::HideInactiveWindow.md)|Указывает, следует ли отображать границы неактивные окна набора вкладок.|  
|[CMFCTabCtrl::HideNoTabs](../Topic/CMFCTabCtrl::HideNoTabs.md)|Включение или отключение отображения области вкладки если отсутствуют видимые вкладки.|  
|[CMFCTabCtrl::HideSingleTab](../Topic/CMFCTabCtrl::HideSingleTab.md)|Включение или отключение рисования вкладки, когда одно окно с вкладками.  \(Переопределяет [CMFCBaseTabCtrl::HideSingleTab](../Topic/CMFCBaseTabCtrl::HideSingleTab.md)\).|  
|[CMFCTabCtrl::IsActiveInMDITabGroup](../Topic/CMFCTabCtrl::IsActiveInMDITabGroup.md)|Показывает, является ли текущая вкладка набора вкладок активной вкладки в нескольких группе вкладок интерфейса документа.|  
|[CMFCTabCtrl::IsActiveTabBoldFont](../Topic/CMFCTabCtrl::IsActiveTabBoldFont.md)|Указывает, отображается ли текст активной вкладки использование полужирный шрифт.|  
|[CMFCTabCtrl::IsActiveTabCloseButton](../Topic/CMFCTabCtrl::IsActiveTabCloseButton.md)|Указывает, отображается ли кнопка "Закрыть" \(**X**\) на активной вкладке или верхн\- правом углу области вкладок.|  
|[CMFCTabCtrl::IsDrawFrame](../Topic/CMFCTabCtrl::IsDrawFrame.md)|Указывает, допускает ли прямоугольник с вкладками окно фрейма для внедренных панелей.|  
|[CMFCTabCtrl::IsFlatFrame](../Topic/CMFCTabCtrl::IsFlatFrame.md)|Указывает, является ли кадр вокруг области вкладки плосок или трехмерные.|  
|[CMFCTabCtrl::IsFlatTab](../Topic/CMFCTabCtrl::IsFlatTab.md)|Указывает, является ли внешний вид вкладок в текущем наборе вкладок плосок или нет.|  
|[CMFCTabCtrl::IsLeftRightRounded](../Topic/CMFCTabCtrl::IsLeftRightRounded.md)|Указывает, является ли округляется представление левого и правой части вкладки в текущем наборе вкладок.|  
|[CMFCTabCtrl::IsMDITabGroup](../Topic/CMFCTabCtrl::IsMDITabGroup.md)|Указывает, содержится ли текущий набор вкладок в клиентской области окна MDI.|  
|[CMFCTabCtrl::IsOneNoteStyle](../Topic/CMFCTabCtrl::IsOneNoteStyle.md)|Указывает, отображается ли текущий набор вкладок в стиле Майкрософт OneNote.|  
|`CMFCTabCtrl::IsPtInTabArea`|Определяет, если точка в области вкладок.  \(Переопределяет [CMFCBaseTabCtrl::IsPtInTabArea](../Topic/CMFCBaseTabCtrl::IsPtInTabArea.md)\).|  
|[CMFCTabCtrl::IsSharedScroll](../Topic/CMFCTabCtrl::IsSharedScroll.md)|Указывает, имеет ли текущий набор вкладок полосу прокрутки, которая может прокручиваться его вкладки, как группа.|  
|[CMFCTabCtrl::IsTabDocumentsMenu](../Topic/CMFCTabCtrl::IsTabDocumentsMenu.md)|Указывает, показывающее, является ли набор вкладок кнопки прокрутки или кнопку, которая отображает меню нашитых windows.|  
|[CMFCTabCtrl::IsVS2005Style](../Topic/CMFCTabCtrl::IsVS2005Style.md)|Указывает, отображаются ли вкладки в стиле Visual Studio .NET 2005.|  
|[CMFCTabCtrl::ModifyTabStyle](../Topic/CMFCTabCtrl::ModifyTabStyle.md)|Определяет внешний вид вкладок в текущем наборе вкладок.|  
|`CMFCTabCtrl::MoveTab`|Перемещает вкладку на другую вкладку.  \(Переопределяет [CMFCBaseTabCtrl::MoveTab](../Topic/CMFCBaseTabCtrl::MoveTab.md)\).|  
|[CMFCTabCtrl::OnDragEnter](../Topic/CMFCTabCtrl::OnDragEnter.md)|Вызываемый платформой, когда курсор сначала будет перетаскивать в поле набор вкладок.|  
|[CMFCTabCtrl::OnDragOver](../Topic/CMFCTabCtrl::OnDragOver.md)|Вызывается средой во время операции перетаскивания, когда указатель мыши над окном будет перемещено целевого объекта для удаления.  \(Переопределяет [CMFCBaseTabCtrl::OnDragOver](../Topic/CMFCBaseTabCtrl::OnDragOver.md)\).|  
|[CMFCTabCtrl::OnShowTabDocumentsMenu](../Topic/CMFCTabCtrl::OnShowTabDocumentsMenu.md)|Отображает контекстное меню меню нашитых windows, ждет, пока пользователь не сможет выбрать вкладку и делает выбранной вкладкой активную вкладку.|  
|`CMFCTabCtrl::PreTranslateMessage`|Преобразует сообщения окна до их посланы к функциям [TranslateMessage](http://msdn.microsoft.com/library/windows/desktop/ms644955) и [DispatchMessage](http://msdn.microsoft.com/library/windows/desktop/ms644934) Windows.  \(Переопределяет [CMFCBaseTabCtrl::PreTranslateMessage](../Topic/CMFCBaseTabCtrl::PreTranslateMessage.md)\).|  
|`CMFCTabCtrl::RecalcLayout`|Повторно вычисляет внутреннюю структуру набора вкладок.  \(Переопределяет [CMFCBaseTabCtrl::RecalcLayout](../Topic/CMFCBaseTabCtrl::RecalcLayout.md)\).|  
|[CMFCTabCtrl::SetActiveInMDITabGroup](../Topic/CMFCTabCtrl::SetActiveInMDITabGroup.md)|Устанавливает текущей вкладкой набора вкладок как активной вкладки в нескольких группе вкладок интерфейса документа.|  
|[CMFCTabCtrl::SetActiveTab](../Topic/CMFCTabCtrl::SetActiveTab.md)|Активировать вкладку.  \(Переопределяет [CMFCBaseTabCtrl::SetActiveTab](../Topic/CMFCBaseTabCtrl::SetActiveTab.md)\).|  
|[CMFCTabCtrl::SetActiveTabBoldFont](../Topic/CMFCTabCtrl::SetActiveTabBoldFont.md)|Включение или отключение использование полужирный шрифт на активных вкладках.|  
|[CMFCTabCtrl::SetDrawFrame](../Topic/CMFCTabCtrl::SetDrawFrame.md)|Включение или отключение прямоугольник кадра drawinga вокруг встроенной панели.|  
|[CMFCTabCtrl::SetFlatFrame](../Topic/CMFCTabCtrl::SetFlatFrame.md)|Указывает, следует ли нарисовать плоский или фрейм трехмерного вокруг области вкладок.|  
|[CMFCTabCtrl::SetImageList](../Topic/CMFCTabCtrl::SetImageList.md)|Определяет список образа.  \(Переопределяет [CMFCBaseTabCtrl::SetImageList](../Topic/CMFCBaseTabCtrl::SetImageList.md)\).|  
|[CMFCTabCtrl::SetResizeMode](../Topic/CMFCTabCtrl::SetResizeMode.md)|Указывает, что и текущий набор вкладок возможность изменения размера, а затем redisplays элемент управления.|  
|[CMFCTabCtrl::SetTabMaxWidth](../Topic/CMFCTabCtrl::SetTabMaxWidth.md)|Указывает максимальную ширину вкладок в окне с вкладками.|  
|[CMFCTabCtrl::StopResize](../Topic/CMFCTabCtrl::StopResize.md)|Завершает текущую операцию изменения размера в наборе вкладок.|  
|`CMFCTabCtrl::SwapTabs`|Передает пара вкладок.  \(Переопределяет [CMFCBaseTabCtrl::SwapTabs](../Topic/CMFCBaseTabCtrl::SwapTabs.md)\).|  
|[CMFCTabCtrl::SynchronizeScrollBar](../Topic/CMFCTabCtrl::SynchronizeScrollBar.md)|Рисует горизонтальная полоса прокрутки в наборе вкладок этой вкладки отображает плоские.|  
  
### Элементы данных  
  
|Имя|Описание|  
|---------|--------------|  
|[CMFCTabCtrl::m\_bEnableActivate](../Topic/CMFCTabCtrl::m_bEnableActivate.md)|Предотвращает активное представление фокуса от потери при вставке и включена новая вкладка.|  
  
## Заметки  
 Поддержка класса `CMFCTabCtrl`:  
  
-   Стили набор вкладок, которые включают эффекты, квартиру и плоский, с общей горизонтальной полосой прокрутки.  
  
-   Вкладки, расположенные в верхней или нижней части окна.  
  
-   Вкладки, которые отображают текст, изображений или текста и изображений.  
  
-   Вкладки, изменяющие цвет, когда вкладка активна.  
  
-   Размер границы изменения для регулируемых вкладок.  
  
-   Отделяемые окна со вкладками.  
  
 Класс `CMFCTabCtrl` можно использовать с диалоговым окном, но предназначен для приложений, использующих закрепление панели элементов управления, как [!INCLUDE[ofprexcel](../Token/ofprexcel_md.md)] и [!INCLUDE[vsprvs](../../assembler/masm/includes/vsprvs_md.md)].  Дополнительные сведения см. в разделе [CDockablePane Class](../Topic/CDockablePane%20Class.md).  
  
 Выполните следующие действия, чтобы добавить изменяемого размера, закрепление набор вкладок в приложении:  
  
1.  Создайте экземпляр класса [CTabbedPane Class](../../mfc/reference/ctabbedpane-class.md).  
  
2.  Вызов метода [CDockablePane::Create](../Topic/CDockablePane::Create.md).  
  
3.  Используйте [CBaseTabbedPane::AddTab](../Topic/CBaseTabbedPane::AddTab.md) или [CMFCBaseTabCtrl::InsertTab](../Topic/CMFCBaseTabCtrl::InsertTab.md) для добавления новых вкладок.  
  
4.  Вызовите [CBasePane::EnableDocking](../Topic/CBasePane::EnableDocking.md), что текущий набор вкладок закрепления сможет закрепляться в главном окне фреймовом.  
  
5.  Вызовите [CFrameWndEx::DockPane](../Topic/CFrameWndEx::DockPane.md) чтобы закрепить окно с вкладками, на главного фрейма.  
  
 Пример создания окно с вкладками, как закрепляющего панель элементов управления см. в разделе [CTabbedPane Class](../../mfc/reference/ctabbedpane-class.md).  Для использования `CMFCTabCtrl` как элемент управления, отличный от закрепления создайте объект `CMFCTabCtrl` и затем вызовите [CMFCTabCtrl::Create](../Topic/CMFCTabCtrl::Create.md).  
  
## Иерархия наследования  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CCmdTarget](../Topic/CCmdTarget%20Class.md)  
  
 [CWnd](../Topic/CWnd%20Class.md)  
  
 [CMFCBaseTabCtrl](../../mfc/reference/cmfcbasetabctrl-class.md)  
  
 [CMFCTabCtrl](../../mfc/reference/cmfctabctrl-class.md)  
  
## Пример  
 В следующем примере показано, как использовать различные методы класса `CMFCTabCtrl` для настройки объект `CMFCTabCtrl`.  В этом примере объясняется, как добавить вкладку, чтобы отобразить кнопку Закрыть на активной вкладке, чтобы включить редактируемые метки вкладки и отобразить контекстное меню меню нашитых меток окна.  Данный пример является частью [Образец коллекции состояния](../../top/visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_StateCollection#1](../../mfc/reference/codesnippet/CPP/cmfctabctrl-class_1.h)]  
[!code-cpp[NVC_MFC_StateCollection#3](../../mfc/reference/codesnippet/CPP/cmfctabctrl-class_2.cpp)]  
  
## Требования  
 **заголовок:** afxtabctrl.h  
  
## См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Классы](../Topic/MFC%20Classes.md)   
 [CDockablePane Class](../Topic/CDockablePane%20Class.md)   
 [CDockablePane Class](../Topic/CDockablePane%20Class.md)   
 [CMFCBaseTabCtrl Class](../../mfc/reference/cmfcbasetabctrl-class.md)