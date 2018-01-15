---
title: "Класс CMFCPopupMenuBar | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCPopupMenuBar
- AFXPOPUPMENUBAR/CMFCPopupMenuBar
- AFXPOPUPMENUBAR/CMFCPopupMenuBar::AdjustSizeImmediate
- AFXPOPUPMENUBAR/CMFCPopupMenuBar::BuildOrigItems
- AFXPOPUPMENUBAR/CMFCPopupMenuBar::CloseDelayedSubMenu
- AFXPOPUPMENUBAR/CMFCPopupMenuBar::ExportToMenu
- AFXPOPUPMENUBAR/CMFCPopupMenuBar::FindDestintationToolBar
- AFXPOPUPMENUBAR/CMFCPopupMenuBar::GetCurrentMenuImageSize
- AFXPOPUPMENUBAR/CMFCPopupMenuBar::GetDefaultMenuId
- AFXPOPUPMENUBAR/CMFCPopupMenuBar::GetLastCommandIndex
- AFXPOPUPMENUBAR/CMFCPopupMenuBar::GetOffset
- AFXPOPUPMENUBAR/CMFCPopupMenuBar::ImportFromMenu
- AFXPOPUPMENUBAR/CMFCPopupMenuBar::IsDropDownListMode
- AFXPOPUPMENUBAR/CMFCPopupMenuBar::IsPaletteMode
- AFXPOPUPMENUBAR/CMFCPopupMenuBar::IsRibbonPanel
- AFXPOPUPMENUBAR/CMFCPopupMenuBar::IsRibbonPanelInRegularMode
- AFXPOPUPMENUBAR/CMFCPopupMenuBar::LoadFromHash
- AFXPOPUPMENUBAR/CMFCPopupMenuBar::RestoreDelayedSubMenu
- AFXPOPUPMENUBAR/CMFCPopupMenuBar::SetButtonStyle
- AFXPOPUPMENUBAR/CMFCPopupMenuBar::SetOffset
- AFXPOPUPMENUBAR/CMFCPopupMenuBar::StartPopupMenuTimer
- AFXPOPUPMENUBAR/CMFCPopupMenuBar::m_bDisableSideBarInXPMode
dev_langs: C++
helpviewer_keywords:
- CMFCPopupMenuBar [MFC], AdjustSizeImmediate
- CMFCPopupMenuBar [MFC], BuildOrigItems
- CMFCPopupMenuBar [MFC], CloseDelayedSubMenu
- CMFCPopupMenuBar [MFC], ExportToMenu
- CMFCPopupMenuBar [MFC], FindDestintationToolBar
- CMFCPopupMenuBar [MFC], GetCurrentMenuImageSize
- CMFCPopupMenuBar [MFC], GetDefaultMenuId
- CMFCPopupMenuBar [MFC], GetLastCommandIndex
- CMFCPopupMenuBar [MFC], GetOffset
- CMFCPopupMenuBar [MFC], ImportFromMenu
- CMFCPopupMenuBar [MFC], IsDropDownListMode
- CMFCPopupMenuBar [MFC], IsPaletteMode
- CMFCPopupMenuBar [MFC], IsRibbonPanel
- CMFCPopupMenuBar [MFC], IsRibbonPanelInRegularMode
- CMFCPopupMenuBar [MFC], LoadFromHash
- CMFCPopupMenuBar [MFC], RestoreDelayedSubMenu
- CMFCPopupMenuBar [MFC], SetButtonStyle
- CMFCPopupMenuBar [MFC], SetOffset
- CMFCPopupMenuBar [MFC], StartPopupMenuTimer
- CMFCPopupMenuBar [MFC], m_bDisableSideBarInXPMode
ms.assetid: 4c93c459-7f70-4240-8c63-280bb811e374
caps.latest.revision: "32"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 002e059fd905930409cb5f2745628f8ac1dea103
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="cmfcpopupmenubar-class"></a>Класс CMFCPopupMenuBar
Строка меню, внедренная в контекстное меню.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CMFCPopupMenuBar : public CMFCToolBar  
```  
  
## <a name="members"></a>Участники  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CMFCPopupMenuBar::AdjustSizeImmediate](#adjustsizeimmediate)|Немедленно повторно вычисляет макет панели. (Переопределяет [CPane::AdjustSizeImmediate](../../mfc/reference/cpane-class.md#adjustsizeimmediate).)|  
|[CMFCPopupMenuBar::BuildOrigItems](#buildorigitems)|Загружает элементы всплывающего меню из меню указанного ресурса.|  
|[CMFCPopupMenuBar::CloseDelayedSubMenu](#closedelayedsubmenu)|Закрывает кнопки отложенной всплывающего меню.|  
|[CMFCPopupMenuBar::ExportToMenu](#exporttomenu)|Выводит на экран меню с помощью кнопок всплывающего меню.|  
|[CMFCPopupMenuBar::FindDestintationToolBar](#finddestintationtoolbar)|Находит панели инструментов, в которой находится указанная точка.|  
|[CMFCPopupMenuBar::GetCurrentMenuImageSize](#getcurrentmenuimagesize)|Указывает размер изображения кнопки меню.|  
|[CMFCPopupMenuBar::GetDefaultMenuId](#getdefaultmenuid)|Возвращает идентификатор элемента меню по умолчанию.|  
|[CMFCPopupMenuBar::GetLastCommandIndex](#getlastcommandindex)|Возвращает индекс наиболее недавно вызванной команды меню.|  
|[CMFCPopupMenuBar::GetOffset](#getoffset)|Возвращает смещение строки всплывающего меню.|  
|[CMFCPopupMenuBar::ImportFromMenu](#importfrommenu)|Импортирует всплывающее меню кнопки указанного меню.|  
|[CMFCPopupMenuBar::IsDropDownListMode](#isdropdownlistmode)|Указывает, является ли всплывающего меню в раскрывающемся списке режиме.|  
|[CMFCPopupMenuBar::IsPaletteMode](#ispalettemode)|Указывает, является ли всплывающего меню в режиме палитры.|  
|[CMFCPopupMenuBar::IsRibbonPanel](#isribbonpanel)|Указывает, является ли панель ленты ( `FALSE` по умолчанию).|  
|[CMFCPopupMenuBar::IsRibbonPanelInRegularMode](#isribbonpanelinregularmode)|Указывает, является ли панель ленты в обычном режиме ( `FALSE` по умолчанию).|  
|[CMFCPopupMenuBar::LoadFromHash](#loadfromhash)|Загружает архивированные меню.|  
|[CMFCPopupMenuBar::RestoreDelayedSubMenu](#restoredelayedsubmenu)|Восстанавливает отложенной меню кнопку для закрытия всплывающего меню.|  
|[CMFCPopupMenuBar::SetButtonStyle](#setbuttonstyle)|Задает стиль кнопки панели инструментов по указанному индексу. (Переопределяет [CMFCToolBar::SetButtonStyle](../../mfc/reference/cmfctoolbar-class.md#setbuttonstyle).)|  
|[CMFCPopupMenuBar::SetOffset](#setoffset)|Задает смещение строки всплывающего меню.|  
|[CMFCPopupMenuBar::StartPopupMenuTimer](#startpopupmenutimer)|Запускает таймер для указанной отложенной всплывающее меню кнопки.|  
  
### <a name="data-members"></a>Элементы данных  
  
|name|Описание:|  
|----------|-----------------|  
|[CMFCPopupMenuBar::m_bDisableSideBarInXPMode](#m_bdisablesidebarinxpmode)|Указывает, будет ли отображаться серую полосу, если приложение имеет вид Windows XP.|  
  
## <a name="remarks"></a>Примечания  
 `CMFCPopupMenuBar` Создается в то же время, как [CMFCPopupMenu класса](../../mfc/reference/cmfcpopupmenu-class.md) и внедренные внутри него. `CMFCPopupMenuBar` Охватывает всю клиентскую область `CMFCPopupMenu` объекта. Он поддерживает клавиатуру и мышь входных данных. Он взаимодействует, что входные данные `CMFCPopupMenu` и окно фрейма верхнего уровня.  
  
## <a name="example"></a>Пример  
 В следующем примере показано, как инициализировать `CMFCPopupMenuBar` объекта из `CMFCPopupMenu` объекта. Этот фрагмент кода входит в состав [примера Draw Client](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_DrawClient#7](../../mfc/reference/codesnippet/cpp/cmfcpopupmenubar-class_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CBasePane](../../mfc/reference/cbasepane-class.md)  
  
 [CPane](../../mfc/reference/cpane-class.md)  
  
 [CMFCBaseToolBar](../../mfc/reference/cmfcbasetoolbar-class.md)  
  
 [CMFCToolBar](../../mfc/reference/cmfctoolbar-class.md)  
  
 [CMFCPopupMenuBar](../../mfc/reference/cmfcpopupmenubar-class.md)  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxpopupmenubar.h  
  
##  <a name="adjustsizeimmediate"></a>CMFCPopupMenuBar::AdjustSizeImmediate  
 Немедленно повторно вычисляет макет панели всплывающее меню строки. (Переопределяет [CPane::AdjustSizeImmediate](../../mfc/reference/cpane-class.md#adjustsizeimmediate).  
  
```  
virtual void AdjustSizeImmediate(BOOL bRecalcLayout);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `bRecalcLayout`  
 `TRUE`автоматически пересчитать макета панели строки всплывающего меню; в противном случае `FALSE`.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="buildorigitems"></a>CMFCPopupMenuBar::BuildOrigItems  
 Загружает элементы всплывающего меню из меню указанного ресурса.  
  
```  
BOOL BuildOrigItems(UINT uiMenuResID);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `uiMenuResID`  
 Указывает идентификатор меню ресурс меню загрузки.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает `TRUE` в случае успешного выполнения или `FALSE` в противном случае.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="closedelayedsubmenu"></a>CMFCPopupMenuBar::CloseDelayedSubMenu  
 Закрывает кнопку контекстного меню, которое было отложено.  
  
```  
virtual void CloseDelayedSubMenu();
```  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="exporttomenu"></a>CMFCPopupMenuBar::ExportToMenu  
 Выводит на экран меню с помощью кнопок всплывающего меню.  
  
```  
virtual HMENU ExportToMenu() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает дескриптор меню «Создать».  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="finddestintationtoolbar"></a>CMFCPopupMenuBar::FindDestintationToolBar  
 Находит панели инструментов, в которой находится указанная точка.  
  
```  
CMFCToolBar* FindDestintationToolBar(CPoint point);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `point`  
 Точка на экране.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает дескриптор для панели инструментов где находится точка, если therei является один, или `NULL` в противном случае.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="getcurrentmenuimagesize"></a>CMFCPopupMenuBar::GetCurrentMenuImageSize  
 Указывает размер изображения кнопки меню.  
  
```  
virtual CSize GetCurrentMenuImageSize() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает размер изображений кнопки меню на панели инструментов.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="getdefaultmenuid"></a>CMFCPopupMenuBar::GetDefaultMenuId  
 Возвращает идентификатор элемента меню по умолчанию.  
  
```  
UINT GetDefaultMenuId() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает идентификатор элемента меню по умолчанию всплывающее меню.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="getlastcommandindex"></a>CMFCPopupMenuBar::GetLastCommandIndex  
 Возвращает индекс наиболее недавно вызванной команды меню.  
  
```  
static int __stdcall GetLastCommandIndex();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает индекс последней команды меню, который был вызван.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="getoffset"></a>CMFCPopupMenuBar::GetOffset  
 Возвращает смещение строки всплывающего меню.  
  
```  
int GetOffset() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает смещение строки всплывающего меню.  
  
### <a name="remarks"></a>Примечания  
 Это значение задается с помощью [CMFCPopupMenuBar::SetOffset](#setoffset).  
  
##  <a name="importfrommenu"></a>CMFCPopupMenuBar::ImportFromMenu  
 Импортирует всплывающее меню кнопки указанного меню.  
  
```  
virtual BOOL ImportFromMenu(
    HMENU hMenu,  
    BOOL bShowAllCommands = FALSE);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `hMenu`  
 Меню, из которого импортируются кнопок всплывающего меню.  
  
 [in] `bShowAllCommands`  
 `TRUE`Если необходимо импортировать все команды в меню или `FALSE` Если редко используемые из них может быть скрыт.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает `TRUE` Если кнопок меню успешно импортированы в меню или `FALSE` в противном случае.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="isdropdownlistmode"></a>CMFCPopupMenuBar::IsDropDownListMode  
 Указывает, является ли всплывающего меню в раскрывающемся списке режиме.  
  
```  
BOOL IsDropDownListMode() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает `TRUE` если всплывающее меню находится в режиме раскрывающемся списке, или `FALSE` в противном случае.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="ispalettemode"></a>CMFCPopupMenuBar::IsPaletteMode  
 Указывает, является ли всплывающего меню в режиме палитры.  
  
```  
BOOL IsPaletteMode() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает `TRUE` при включенной палитры или `FALSE` в противном случае.  
  
### <a name="remarks"></a>Примечания  
 Когда меню устанавливается режим палитру, пункты меню отображаются в нескольких столбцах и ограниченного количества строк.  
  
##  <a name="isribbonpanel"></a>CMFCPopupMenuBar::IsRibbonPanel  
 Указывает, является ли панель ленты ( `FALSE` по умолчанию).  
  
```  
virtual BOOL IsRibbonPanel() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает `FALSE` по умолчанию, указывая, что это не панель ленты.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="isribbonpanelinregularmode"></a>CMFCPopupMenuBar::IsRibbonPanelInRegularMode  
 Указывает, является ли панель ленты в обычном режиме ( `FALSE` по умолчанию).  
  
```  
virtual BOOL IsRibbonPanelInRegularMode() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает `FALSE` по умолчанию, указывая, что это не панель ленты в обычном режиме.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="loadfromhash"></a>CMFCPopupMenuBar::LoadFromHash  
 Загружает архивированные меню.  
  
```  
BOOL LoadFromHash(HMENU hMenu);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `hMenu`  
 Дескриптор архивированные меню загрузки.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает `TRUE` Если меню загружен успешно, или `FALSE` в противном случае.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="m_bdisablesidebarinxpmode"></a>CMFCPopupMenuBar::m_bDisableSideBarInXPMode  
 Параметр типа Boolean, указывающее, имеет ли приложение серую полосу, если он имеет вид Windows XP.  
  
```  
BOOL m_bDisableSideBarInXPMode;  
```  
  
### <a name="remarks"></a>Примечания  
 Если имеет значение этой переменной-члена `FALSE` и ваше приложение имеет вид Windows XP, платформа рисует серую полосу в приложении.  
  
 Значение по умолчанию — `FALSE`.  
  
##  <a name="restoredelayedsubmenu"></a>CMFCPopupMenuBar::RestoreDelayedSubMenu  
 Восстанавливает отложенной меню кнопку для закрытия всплывающего меню.  
  
```  
virtual void RestoreDelayedSubMenu();
```  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="setbuttonstyle"></a>CMFCPopupMenuBar::SetButtonStyle  
 Задает стиль кнопки панели инструментов по указанному индексу. (Переопределяет [CMFCToolBar::SetButtonStyle](../../mfc/reference/cmfctoolbar-class.md#setbuttonstyle).)  
  
```  
virtual void SetButtonStyle(
    int nIndex,  
    UINT nStyle);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `nIndex`  
 Отсчитываемый от нуля индекс кнопки на панели инструментов стиль которого требуется задать.  
  
 [in] `nStyle`  
 Стиль кнопки. В разделе [стили элемента управления панель инструментов](../../mfc/reference/toolbar-control-styles.md) список стилей кнопок панели инструментов доступны.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="setoffset"></a>CMFCPopupMenuBar::SetOffset  
 Задает смещение строки всплывающего меню.  
  
```  
void SetOffset(int iOffset);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `iOffset`  
 Число строк, всплывающее меню должен быть смещены.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="startpopupmenutimer"></a>CMFCPopupMenuBar::StartPopupMenuTimer  
 Запускает таймер для указанной отложенной всплывающее меню кнопки.  
  
```  
void StartPopupMenuTimer(
    CMFCToolBarMenuButton* pMenuButton,  
    int nDelayFactor = 1);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pMenuButton`  
 Указатель на кнопку меню, для которого требуется задать таймер задержки.  
  
 [in] `nDelayFactor`  
 Фактор задержки, равным по крайней мере один умножение на время задержки стандартные меню (как правило, от полсекунды и пять секунд).  
  
### <a name="remarks"></a>Примечания  
  
## <a name="see-also"></a>См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Классы](../../mfc/reference/mfc-classes.md)   
 [Класс CMFCColorBar](../../mfc/reference/cmfccolorbar-class.md)   
 [Класс CMFCPopupMenu](../../mfc/reference/cmfcpopupmenu-class.md)
