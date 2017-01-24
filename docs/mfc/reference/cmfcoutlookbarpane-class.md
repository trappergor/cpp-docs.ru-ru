---
title: "CMFCOutlookBarPane Class | Microsoft Docs"
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
  - "CMFCOutlookBarPane"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CanBeRestored method"
  - "CMFCOutlookBarPane class"
  - "Dock method"
  - "IsChangeState method"
  - "OnBeforeFloat method"
  - "RestoreOriginalstate method"
  - "SmartUpdate method"
ms.assetid: 094e2ef3-a118-487e-a4cc-27626108fe08
caps.latest.revision: 30
caps.handback.revision: 18
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CMFCOutlookBarPane Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

[!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
 Элемент управления, производный от [CMFCToolBar Class](../../mfc/reference/cmfctoolbar-class.md), которое можно вставить на панели outlook \([Класс CMFCOutlookBar](../../mfc/reference/cmfcoutlookbar-class.md)\).  Область панели outlook содержит столбец больших кнопок.  Пользователь может выполнить прокрутку вверх и вниз список кнопок, если он больше панели.  Наконец, когда пользователь удаляет область панели outlook из панели outlook, он может плыть или закрепить фреймовом в главном окне.  
  
## Синтаксис  
  
```  
class CMFCOutlookBarPane : public CMFCToolBar  
```  
  
## Члены  
  
### Открытые конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|`CMFCOutlookBarPane::CMFCOutlookBarPane`|Конструктор по умолчанию.|  
|`CMFCOutlookBarPane::~CMFCOutlookBarPane`|Деструктор.|  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[CMFCOutlookBarPane::AddButton](../Topic/CMFCOutlookBarPane::AddButton.md)|Добавьте кнопку на панели outlook.|  
|[CMFCOutlookBarPane::CanBeAttached](../Topic/CMFCOutlookBarPane::CanBeAttached.md)|Определяет, является ли панель можно закрепить в другой области или фреймовому окно.  \(Переопределяет [CBasePane::CanBeAttached](../Topic/CBasePane::CanBeAttached.md)\).|  
|`CMFCOutlookBarPane::CanBeRestored`|Определяет, может ли система получить панели инструментов в исходное состояние после настройки.  \(Переопределяет [CMFCToolBar::CanBeRestored](../Topic/CMFCToolBar::CanBeRestored.md)\).|  
|[CMFCOutlookBarPane::ClearAll](../Topic/CMFCOutlookBarPane::ClearAll.md)|Освобождает ресурсы, используемые образами на панели outlook.|  
|[CMFCOutlookBarPane::Create](../Topic/CMFCOutlookBarPane::Create.md)|Создает область панели outlook.|  
|`CMFCOutlookBarPane::CreateObject`|Используемый платформой, чтобы создать динамический экземпляр этого типа класса.|  
|`CMFCOutlookBarPane::Dock`|Вызываемый платформой, чтобы закрепить панель outlook. \(Переопределяет `CPane::Dock`\).|  
|[CMFCOutlookBarPane::EnablePageScrollMode](../Topic/CMFCOutlookBarPane::EnablePageScrollMode.md)|Определяет, является ли выдвигают прокрутки обращена на панели outlook список кнопок страницей или кнопкой.|  
|[CMFCOutlookBarPane::GetRegularColor](../Topic/CMFCOutlookBarPane::GetRegularColor.md)|Возвращает обычный \(\), выбранный цвет текста панели outlook.|  
|`CMFCOutlookBarPane::GetThisClass`|Используемый платформой для получения указателя на объект [CRuntimeClass](../Topic/CRuntimeClass%20Structure.md), который связан с этим типом класса.|  
|[CMFCOutlookBarPane::IsBackgroundTexture](../Topic/CMFCOutlookBarPane::IsBackgroundTexture.md)|Определяет, является ли образом фоновое изображение, загруженное для панели outlook.|  
|`CMFCOutlookBarPane::IsChangeState`|Определяет, может ли быть закреплена панель плавающей запятой.  \(Переопределяет `CPane::IsChangeState`\).|  
|[CMFCOutlookBarPane::IsDrawShadedHighlight](../Topic/CMFCOutlookBarPane::IsDrawShadedHighlight.md)|Определяет границы кнопки, когда затенена ли кнопка выделена и образом фоновое изображение.|  
|`CMFCOutlookBarPane::OnBeforeFloat`|Если панель с границами рядом с плыть.  \(Переопределяет [CPane::OnBeforeFloat](../Topic/CPane::OnBeforeFloat.md)\).|  
|[CMFCOutlookBarPane::RemoveButton](../Topic/CMFCOutlookBarPane::RemoveButton.md)|Удаляет кнопка, которая имеет указанный идентификатор команды.|  
|`CMFCOutlookBarPane::RestoreOriginalstate`|Получает исходное состояние панели инструментов.  \(Переопределяет [CMFCToolBar::RestoreOriginalState](../Topic/CMFCToolBar::RestoreOriginalState.md)\).|  
|[CMFCOutlookBarPane::SetBackColor](../Topic/CMFCOutlookBarPane::SetBackColor.md)|Устанавливает цвет фона.|  
|[CMFCOutlookBarPane::SetBackImage](../Topic/CMFCOutlookBarPane::SetBackImage.md)|Устанавливает образом фоновое изображение.|  
|[CMFCOutlookBarPane::SetDefaultState](../Topic/CMFCOutlookBarPane::SetDefaultState.md)|Сбросить панель outlook к исходному набору кнопок.|  
|[CMFCOutlookBarPane::SetExtraSpace](../Topic/CMFCOutlookBarPane::SetExtraSpace.md)|Устанавливает количество пикселей, используемых для заполнения кнопок на панели outlook.|  
|[CMFCOutlookBarPane::SetTextColor](../Topic/CMFCOutlookBarPane::SetTextColor.md)|Устанавливает обычных и цвета выделенного текста на панели outlook.|  
|[CMFCOutlookBarPane::SetTransparentColor](../Topic/CMFCOutlookBarPane::SetTransparentColor.md)|Устанавливает прозрачный цвет панели outlook.|  
|`CMFCOutlookBarPane::SmartUpdate`|Внутренне используемый для обновления панели outlook.  \(Переопределяет `CMFCToolBar::SmartUpdate`\).|  
  
### Защищенные методы  
  
|Имя|Описание|  
|---------|--------------|  
|[CMFCOutlookBarPane::EnableContextMenuItems](../Topic/CMFCOutlookBarPane::EnableContextMenuItems.md)|Определяет, какие элементы контекстного меню, отображаемых в режиме настройки.|  
|[CMFCOutlookBarPane::RemoveAllButtons](../Topic/CMFCOutlookBarPane::RemoveAllButtons.md)|Удаляет все кнопки на панели outlook.  \(Переопределяет [CMFCToolBar::RemoveAllButtons](../Topic/CMFCToolBar::RemoveAllButtons.md)\).|  
  
## Заметки  
 Дополнительные сведения о реализации панели outlook см. в разделе [Класс CMFCOutlookBar](../../mfc/reference/cmfcoutlookbar-class.md).  
  
 Пример панели outlook см. образец OutlookDemo проектов.  
  
## Пример  
 В следующем примере показано, как использовать различные методы класса `CMFCOutlookBarPane`.  Примере показано, как создать область панели outlook включается режим прокрутки страницы, включает закрепления и укажите цвет фона панели outlook.  Этот фрагмент кода является частью [Пример типов outlook Multi](../../top/visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_OutlookMultiViews#3](../../mfc/reference/codesnippet/CPP/cmfcoutlookbarpane-class_1.h)]  
[!code-cpp[NVC_MFC_OutlookMultiViews#4](../../mfc/reference/codesnippet/CPP/cmfcoutlookbarpane-class_2.cpp)]  
  
## Иерархия наследования  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CCmdTarget](../Topic/CCmdTarget%20Class.md)  
  
 [CWnd](../Topic/CWnd%20Class.md)  
  
 [CBasePane](../../mfc/reference/cbasepane-class.md)  
  
 [CPane](../../mfc/reference/cpane-class.md)  
  
 [CMFCBaseToolBar](../../mfc/reference/cmfcbasetoolbar-class.md)  
  
 [CMFCToolBar](../../mfc/reference/cmfctoolbar-class.md)  
  
 [CMFCOutlookBarPane](../../mfc/reference/cmfcoutlookbarpane-class.md)  
  
## Требования  
 **заголовок:** afxoutlookbarpane.h  
  
## См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Классы](../Topic/MFC%20Classes.md)   
 [CMFCToolBar Class](../../mfc/reference/cmfctoolbar-class.md)   
 [Класс CMFCOutlookBar](../../mfc/reference/cmfcoutlookbar-class.md)   
 [CMFCOutlookBarTabCtrl Class](../../mfc/reference/cmfcoutlookbartabctrl-class.md)