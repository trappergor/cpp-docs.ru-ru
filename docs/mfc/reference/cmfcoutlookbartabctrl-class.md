---
title: "CMFCOutlookBarTabCtrl Class | Microsoft Docs"
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
  - "CMFCOutlookBarTabCtrl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCOutlookBarTabCtrl class"
ms.assetid: b1f2b3f7-cc59-49a3-99d8-7ff9b37c044b
caps.latest.revision: 26
caps.handback.revision: 15
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CMFCOutlookBarTabCtrl Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Набор вкладок, имеющий визуальное представление **Область переходов** в Microsoft Outlook.  
  
## Синтаксис  
  
```  
class CMFCOutlookBarTabCtrl : public CMFCBaseTabCtrl  
```  
  
## Члены  
  
### Открытые конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|`CMFCOutlookBarTabCtrl::CMFCOutlookBarTabCtrl`|Конструктор по умолчанию.|  
|`CMFCOutlookBarTabCtrl::~CMFCOutlookBarTabCtrl`|Деструктор.|  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[CMFCOutlookBarTabCtrl::AddControl](../Topic/CMFCOutlookBarTabCtrl::AddControl.md)|Добавляет элемент управления Windows в виде новой вкладки на панели outlook.|  
|`CMFCOutlookBarTabCtrl::CalcRectEdit`|Вызываемый платформой для определения измерения поля ввода, которое отображается, когда пользователь переименовать вкладку.  \(Переопределяет `CMFCBaseTabCtrl::CalcRectEdit`\).|  
|[CMFCOutlookBarTabCtrl::CanShowFewerPageButtons](../Topic/CMFCOutlookBarTabCtrl::CanShowFewerPageButtons.md)|Вызывается средой во время размер операции, чтобы определить, меньше кнопок страниц вкладок панели outlook можно отобразить меньше видима в настоящий момент.|  
|[CMFCOutlookBarTabCtrl::CanShowMorePageButtons](../Topic/CMFCOutlookBarTabCtrl::CanShowMorePageButtons.md)|Вызывается средой во время размер операции, чтобы определить наличие нескольких кнопок страниц вкладок панели outlook можно отобразить меньше видима в настоящий момент.|  
|[CMFCOutlookBarTabCtrl::Create](../Topic/CMFCOutlookBarTabCtrl::Create.md)|Создает набор вкладок панели outlook.|  
|`CMFCOutlookBarTabCtrl::CreateObject`|Используемый платформой, чтобы создать динамический экземпляр этого типа класса.|  
|[CMFCOutlookBarTabCtrl::EnableAnimation](../Topic/CMFCOutlookBarTabCtrl::EnableAnimation.md)|Указывает, включена ли анимация, которая происходит во время переключения между активными вкладками.|  
|[CMFCOutlookBarTabCtrl::EnableInPlaceEdit](../Topic/CMFCOutlookBarTabCtrl::EnableInPlaceEdit.md)|Указывает, может ли пользователь изменять текст подписи на кнопках вкладки панели outlook.  \(Переопределяет [CMFCBaseTabCtrl::EnableInPlaceEdit](../Topic/CMFCBaseTabCtrl::EnableInPlaceEdit.md)\).|  
|[CMFCOutlookBarTabCtrl::EnableScrollButtons](../Topic/CMFCOutlookBarTabCtrl::EnableScrollButtons.md)|Вызываемый платформой для включения кнопки, которые позволяют пользователю для прокрутки с помощью кнопки на панели outlook.|  
|`CMFCOutlookBarTabCtrl::FindTargetWnd`|Определяет область, которая содержит указанную точку.  \(Переопределяет [CMFCBaseTabCtrl::FindTargetWnd](../Topic/CMFCBaseTabCtrl::FindTargetWnd.md)\).|  
|[CMFCOutlookBarTabCtrl::GetBorderSize](../Topic/CMFCOutlookBarTabCtrl::GetBorderSize.md)|Возвращает размер границы набора вкладок outlook.|  
|`CMFCOutlookBarTabCtrl::GetTabArea`|Получает размер и положение панели вкладки набор вкладок.  \(Переопределяет [CMFCBaseTabCtrl::GetTabArea](../Topic/CMFCBaseTabCtrl::GetTabArea.md)\).|  
|`CMFCOutlookBarTabCtrl::GetThisClass`|Используемый платформой для получения указателя на объект [CRuntimeClass](../Topic/CRuntimeClass%20Structure.md), который связан с этим типом класса.|  
|[CMFCOutlookBarTabCtrl::GetVisiblePageButtons](../Topic/CMFCOutlookBarTabCtrl::GetVisiblePageButtons.md)||  
|[CMFCOutlookBarTabCtrl::IsAnimation](../Topic/CMFCOutlookBarTabCtrl::IsAnimation.md)|Указывает, включена ли анимация, которая происходит во время переключения между активными вкладками.|  
|[CMFCOutlookBarTabCtrl::IsMode2003](../Topic/CMFCOutlookBarTabCtrl::IsMode2003.md)|Определяет, является ли набор вкладок панели outlook находится в режиме, который эмулируется Microsoft Outlook 2003.|  
|`CMFCOutlookBarTabCtrl::IsPtInTabArea`|Определяет, если точка в области вкладок.  \(Переопределяет [CMFCBaseTabCtrl::IsPtInTabArea](../Topic/CMFCBaseTabCtrl::IsPtInTabArea.md)\).|  
|`CMFCOutlookBarTabCtrl::IsTabDetachable`|Определяет, является ли на вкладку отделяема.  \(Переопределяет [CMFCBaseTabCtrl::IsTabDetachable](../Topic/CMFCBaseTabCtrl::IsTabDetachable.md)\).|  
|`CMFCOutlookBarTabCtrl::OnChangeTabs`|Вызываемый платформой, когда будет вставлена или удалена вкладку.  \(Переопределяет `CMFCBaseTabCtrl::OnChangeTabs`\).|  
|[CMFCOutlookBarTabCtrl::OnShowFewerPageButtons](../Topic/CMFCOutlookBarTabCtrl::OnShowFewerPageButtons.md)|Вызываемый платформой, чтобы уменьшить число кнопок страниц вкладок, которые являются видимыми.|  
|[CMFCOutlookBarTabCtrl::OnShowMorePageButtons](../Topic/CMFCOutlookBarTabCtrl::OnShowMorePageButtons.md)|Вызываемый платформой, чтобы увеличить количество кнопок страниц вкладок, которые являются видимыми.|  
|[CMFCOutlookBarTabCtrl::OnShowOptions](../Topic/CMFCOutlookBarTabCtrl::OnShowOptions.md)|Отображает диалоговое окно **Параметры области навигации**.|  
|`CMFCOutlookBarTabCtrl::RecalcLayout`|Повторно вычисляет внутреннюю структуру набора вкладок.  \(Переопределяет [CMFCBaseTabCtrl::RecalcLayout](../Topic/CMFCBaseTabCtrl::RecalcLayout.md)\).|  
|[CMFCOutlookBarTabCtrl::SetActiveTab](../Topic/CMFCOutlookBarTabCtrl::SetActiveTab.md)|Задает активную вкладку.  \(Переопределяет [CMFCBaseTabCtrl::SetActiveTab](../Topic/CMFCBaseTabCtrl::SetActiveTab.md)\).|  
|[CMFCOutlookBarTabCtrl::SetBorderSize](../Topic/CMFCOutlookBarTabCtrl::SetBorderSize.md)|Задает размер границы набора вкладок outlook.|  
|[CMFCOutlookBarTabCtrl::SetPageButtonTextAlign](../Topic/CMFCOutlookBarTabCtrl::SetPageButtonTextAlign.md)|Задает выравнивание текстовых подписей на кнопках вкладки панели outlook.|  
|[CMFCOutlookBarTabCtrl::SetToolbarImageList](../Topic/CMFCOutlookBarTabCtrl::SetToolbarImageList.md)|Задает растровое изображение, которая содержит значки, которые отображаются на нижней части панели outlook находится в режиме outlook 2003 \(см. [Класс CMFCOutlookBar](../../mfc/reference/cmfcoutlookbar-class.md)\).|  
|[CMFCOutlookBarTabCtrl::SetVisiblePageButtons](../Topic/CMFCOutlookBarTabCtrl::SetVisiblePageButtons.md)||  
  
## Заметки  
 Чтобы создать внешний вид заприте с поддержкой закрепления используйте объект `CMFCOutlookBar` для размещения набор вкладок панели outlook.  Дополнительные сведения см. в разделе [Класс CMFCOutlookBar](../../mfc/reference/cmfcoutlookbar-class.md).  
  
## Пример  
 В следующем примере показано, как инициализировать объект `CMFCOutlookBarTabCtrl` и использовать различные методы в `CMFCOutlookBarTabCtrl` классифицируйте.  Примере показано, как включить редактирование локально текстовой подписи в кнопках страницы вкладки панели outlook, включает анимации, разрешает маркеры прокрутки, позволяющие пользователю выполнить с помощью кнопки на панели outlook, устанавливать размер границы набора вкладок outlook, и устанавливает выравнивание текстовых подписей на кнопках вкладки панели outlook.  Этот фрагмент кода является частью [Пример demo outlook](../../top/visual-cpp-samples.md).  
  
 [!CODE [NVC_MFC_OutlookDemo#1](../CodeSnippet/VS_Snippets_Misc/NVC_MFC_OutlookDemo#1)]  
[!CODE [NVC_MFC_OutlookDemo#2](../CodeSnippet/VS_Snippets_Misc/NVC_MFC_OutlookDemo#2)]  
  
## Иерархия наследования  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CCmdTarget](../Topic/CCmdTarget%20Class.md)  
  
 [CWnd](../Topic/CWnd%20Class.md)  
  
 [CMFCBaseTabCtrl](../../mfc/reference/cmfcbasetabctrl-class.md)  
  
 [CMFCOutlookBarTabCtrl](../../mfc/reference/cmfcoutlookbartabctrl-class.md)  
  
## Требования  
 **заголовок:** afxoutlookbartabctrl.h  
  
## См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Классы](../Topic/MFC%20Classes.md)   
 [CMFCBaseTabCtrl Class](../../mfc/reference/cmfcbasetabctrl-class.md)   
 [Класс CMFCOutlookBar](../../mfc/reference/cmfcoutlookbar-class.md)   
 [CMFCOutlookBarPane Class](../../mfc/reference/cmfcoutlookbarpane-class.md)