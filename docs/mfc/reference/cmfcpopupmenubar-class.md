---
title: Класс CMFCPopupMenuBar | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
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
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: b9dc88b6b4488115390f4e6be57fbba2caadcc01
ms.sourcegitcommit: 26fff80635bd1d51bc51899203fddfea8b29b530
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/05/2018
ms.locfileid: "37853638"
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
|[CMFCPopupMenuBar::AdjustSizeImmediate](#adjustsizeimmediate)|Сразу же повторно вычисляет макет области. (Переопределяет [CPane::AdjustSizeImmediate](../../mfc/reference/cpane-class.md#adjustsizeimmediate).)|  
|[CMFCPopupMenuBar::BuildOrigItems](#buildorigitems)|Загружает элементы всплывающего меню из меню указанного ресурса.|  
|[CMFCPopupMenuBar::CloseDelayedSubMenu](#closedelayedsubmenu)|Закрывает кнопки отложенной всплывающего меню.|  
|[CMFCPopupMenuBar::ExportToMenu](#exporttomenu)|Выполняет построение меню кнопки во всплывающем меню.|  
|[CMFCPopupMenuBar::FindDestintationToolBar](#finddestintationtoolbar)|Находит панели инструментов, в которой находится указанная точка.|  
|[CMFCPopupMenuBar::GetCurrentMenuImageSize](#getcurrentmenuimagesize)|Указывает размер изображения кнопки меню.|  
|[CMFCPopupMenuBar::GetDefaultMenuId](#getdefaultmenuid)|Возвращает идентификатор элемента меню по умолчанию.|  
|[CMFCPopupMenuBar::GetLastCommandIndex](#getlastcommandindex)|Получает индекс наиболее недавно вызванной команды меню.|  
|[CMFCPopupMenuBar::GetOffset](#getoffset)|Получает смещение в строке меню всплывающего окна.|  
|[CMFCPopupMenuBar::ImportFromMenu](#importfrommenu)|Импортирует всплывающего меню кнопки из указанного меню.|  
|[CMFCPopupMenuBar::IsDropDownListMode](#isdropdownlistmode)|Указывает, является ли всплывающее меню в раскрывающемся списке режиме.|  
|[CMFCPopupMenuBar::IsPaletteMode](#ispalettemode)|Указывает, является ли всплывающее меню в режиме палитры.|  
|[CMFCPopupMenuBar::IsRibbonPanel](#isribbonpanel)|Указывает, является ли это на панель ленты (по умолчанию — FALSE).|  
|[CMFCPopupMenuBar::IsRibbonPanelInRegularMode](#isribbonpanelinregularmode)|Указывает, является ли это на панель ленты в обычном режиме (по умолчанию — FALSE).|  
|[CMFCPopupMenuBar::LoadFromHash](#loadfromhash)|Загружает архивные меню.|  
|[CMFCPopupMenuBar::RestoreDelayedSubMenu](#restoredelayedsubmenu)|Восстанавливает отложенной меню кнопку для закрытия всплывающего меню.|  
|[CMFCPopupMenuBar::SetButtonStyle](#setbuttonstyle)|Задает стиль кнопки панели инструментов по указанному индексу. (Переопределяет [CMFCToolBar::SetButtonStyle](../../mfc/reference/cmfctoolbar-class.md#setbuttonstyle).)|  
|[CMFCPopupMenuBar::SetOffset](#setoffset)|Задает смещение в строке меню всплывающего окна.|  
|[CMFCPopupMenuBar::StartPopupMenuTimer](#startpopupmenutimer)|Запускает таймер для кнопки указанной отложенной всплывающего меню.|  
  
### <a name="data-members"></a>Элементы данных  
  
|name|Описание:|  
|----------|-----------------|  
|[CMFCPopupMenuBar::m_bDisableSideBarInXPMode](#m_bdisablesidebarinxpmode)|Указывает, будет ли отображаться серую полосу, когда приложение имеет внешний вид Windows XP.|  
  
## <a name="remarks"></a>Примечания  
 `CMFCPopupMenuBar` Создается в то же время, как [класс CMFCPopupMenu](../../mfc/reference/cmfcpopupmenu-class.md) и embedded внутри него. `CMFCPopupMenuBar` Включает всю клиентскую область `CMFCPopupMenu` объекта. Он поддерживает, клавиатуру и мышь. Он взаимодействует, что входные данные `CMFCPopupMenu` и окно фрейма верхнего уровня.  
  
## <a name="example"></a>Пример  
 Следующий пример демонстрирует способы инициализации `CMFCPopupMenuBar` объекта из `CMFCPopupMenu` объекта. Этот фрагмент кода входит в состав [примера Draw Client](../../visual-cpp-samples.md).  
  
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
  
##  <a name="adjustsizeimmediate"></a>  CMFCPopupMenuBar::AdjustSizeImmediate  
 Сразу же повторно вычисляет макет панели строки всплывающего меню. (Переопределяет [CPane::AdjustSizeImmediate](../../mfc/reference/cpane-class.md#adjustsizeimmediate).  
  
```  
virtual void AdjustSizeImmediate(BOOL bRecalcLayout);
```  
  
### <a name="parameters"></a>Параметры  
 [in] *bRecalcLayout*  
 Значение TRUE, чтобы автоматически повторно рассчитать макет панели строки всплывающего меню; в противном случае — значение FALSE.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="buildorigitems"></a>  CMFCPopupMenuBar::BuildOrigItems  
 Загружает элементы всплывающего меню из меню указанного ресурса.  
  
```  
BOOL BuildOrigItems(UINT uiMenuResID);
```  
  
### <a name="parameters"></a>Параметры  
 [in] *uiMenuResID*  
 Указывает идентификатор ресурса меню меню загрузки.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение TRUE, в случае успешного выполнения или значение FALSE, если это не так.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="closedelayedsubmenu"></a>  CMFCPopupMenuBar::CloseDelayedSubMenu  
 Закрывает кнопку контекстного меню, которое было отложено.  
  
```  
virtual void CloseDelayedSubMenu();
```  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="exporttomenu"></a>  CMFCPopupMenuBar::ExportToMenu  
 Выполняет построение меню кнопок всплывающего меню.  
  
```  
virtual HMENU ExportToMenu() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает дескриптор для меню «Создать».  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="finddestintationtoolbar"></a>  CMFCPopupMenuBar::FindDestintationToolBar  
 Находит панели инструментов, в которой находится указанная точка.  
  
```  
CMFCToolBar* FindDestintationToolBar(CPoint point);
```  
  
### <a name="parameters"></a>Параметры  
 [in] *точки*  
 Точка на экране.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает дескриптор для панели инструментов где находится точка, если таковой имеется, или значение NULL, если это не так.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="getcurrentmenuimagesize"></a>  CMFCPopupMenuBar::GetCurrentMenuImageSize  
 Указывает размер изображения кнопки меню.  
  
```  
virtual CSize GetCurrentMenuImageSize() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает размер изображений кнопки меню на панели инструментов.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="getdefaultmenuid"></a>  CMFCPopupMenuBar::GetDefaultMenuId  
 Возвращает идентификатор элемента меню по умолчанию.  
  
```  
UINT GetDefaultMenuId() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает идентификатор элемента по умолчанию меню в строке меню всплывающего окна.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="getlastcommandindex"></a>  CMFCPopupMenuBar::GetLastCommandIndex  
 Получает индекс наиболее недавно вызванной команды меню.  
  
```  
static int __stdcall GetLastCommandIndex();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает индекс последней команды меню, которая была вызвана.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="getoffset"></a>  CMFCPopupMenuBar::GetOffset  
 Получает смещение в строке меню всплывающего окна.  
  
```  
int GetOffset() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает смещение в строке меню всплывающего окна.  
  
### <a name="remarks"></a>Примечания  
 Это значение задается с помощью [CMFCPopupMenuBar::SetOffset](#setoffset).  
  
##  <a name="importfrommenu"></a>  CMFCPopupMenuBar::ImportFromMenu  
 Импортирует всплывающего меню кнопки из указанного меню.  
  
```  
virtual BOOL ImportFromMenu(
    HMENU hMenu,  
    BOOL bShowAllCommands = FALSE);
```  
  
### <a name="parameters"></a>Параметры  
 [in] *hMenu*  
 Меню, из которого импортируются кнопок всплывающего меню.  
  
 [in] *bShowAllCommands*  
 Значение TRUE, если все команды в меню должны быть импортированные или значение FALSE, если редко используемых могут быть скрыты.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение TRUE, если кнопки меню были успешно импортированы в меню, или значение FALSE, если не.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="isdropdownlistmode"></a>  CMFCPopupMenuBar::IsDropDownListMode  
 Указывает, является ли всплывающее меню в раскрывающемся списке режиме.  
  
```  
BOOL IsDropDownListMode() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение TRUE, если не в режиме раскрывающийся список, или значение FALSE, если всплывающей панели меню.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="ispalettemode"></a>  CMFCPopupMenuBar::IsPaletteMode  
 Указывает, является ли всплывающее меню в режиме палитры.  
  
```  
BOOL IsPaletteMode() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение TRUE, если включен режим палитре, или значение FALSE, если это не так.  
  
### <a name="remarks"></a>Примечания  
 Если меню будет переведена в режим палитры, пункты меню отображаются в нескольких столбцах и ограниченное число строк.  
  
##  <a name="isribbonpanel"></a>  CMFCPopupMenuBar::IsRibbonPanel  
 Указывает, является ли это на панель ленты (по умолчанию — FALSE).  
  
```  
virtual BOOL IsRibbonPanel() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение FALSE по умолчанию, указывая, что это не панель ленты.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="isribbonpanelinregularmode"></a>  CMFCPopupMenuBar::IsRibbonPanelInRegularMode  
 Указывает, является ли это на панель ленты в обычном режиме (по умолчанию — FALSE).  
  
```  
virtual BOOL IsRibbonPanelInRegularMode() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение FALSE по умолчанию, указывая, что это не панель ленты в обычном режиме.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="loadfromhash"></a>  CMFCPopupMenuBar::LoadFromHash  
 Загружает архивные меню.  
  
```  
BOOL LoadFromHash(HMENU hMenu);
```  
  
### <a name="parameters"></a>Параметры  
 [in] *hMenu*  
 Дескриптор меню архивные для загрузки.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение TRUE, если меню находится успешно загружен, или FALSE, если это не так.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="m_bdisablesidebarinxpmode"></a>  CMFCPopupMenuBar::m_bDisableSideBarInXPMode  
 Логический параметр, который указывает, имеет ли приложение серую полосу, когда он имеет вид Windows XP.  
  
```  
BOOL m_bDisableSideBarInXPMode;  
```  
  
### <a name="remarks"></a>Примечания  
 Если эта переменная-член имеет значение FALSE, и приложение имеет внешний вид Windows XP, framework рисует серую полосу в приложении.  
  
 Значение по умолчанию — FALSE.  
  
##  <a name="restoredelayedsubmenu"></a>  CMFCPopupMenuBar::RestoreDelayedSubMenu  
 Восстанавливает отложенной меню кнопку для закрытия всплывающего меню.  
  
```  
virtual void RestoreDelayedSubMenu();
```  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="setbuttonstyle"></a>  CMFCPopupMenuBar::SetButtonStyle  
 Задает стиль кнопки панели инструментов по указанному индексу. (Переопределяет [CMFCToolBar::SetButtonStyle](../../mfc/reference/cmfctoolbar-class.md#setbuttonstyle).)  
  
```  
virtual void SetButtonStyle(
    int nIndex,  
    UINT nStyle);
```  
  
### <a name="parameters"></a>Параметры  
 [in] *nIndex*  
 Отсчитываемый от нуля индекс для задается, стиль кнопки панели инструментов.  
  
 [in] *nStyle*  
 Стиль кнопки. См. в разделе [стили элемента управления панели инструментов](../../mfc/reference/toolbar-control-styles.md) список доступных инструментов стили кнопок.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="setoffset"></a>  CMFCPopupMenuBar::SetOffset  
 Задает смещение в строке меню всплывающего окна.  
  
```  
void SetOffset(int iOffset);
```  
  
### <a name="parameters"></a>Параметры  
 [in] *iOffset*  
 Количество строк, что должны быть смещены всплывающей панели меню.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="startpopupmenutimer"></a>  CMFCPopupMenuBar::StartPopupMenuTimer  
 Запускает таймер для кнопки указанной отложенной всплывающего меню.  
  
```  
void StartPopupMenuTimer(
    CMFCToolBarMenuButton* pMenuButton,  
    int nDelayFactor = 1);
```  
  
### <a name="parameters"></a>Параметры  
 [in] *pMenuButton*  
 Указатель на кнопке меню, для которого требуется задать таймер задержки.  
  
 [in] *nDelayFactor*  
 Фактор задержки, равным по крайней мере, необходимо умножить время задержки стандартное меню (как правило, от половины секунды и пять секунд).  
  
### <a name="remarks"></a>Примечания  
  
## <a name="see-also"></a>См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Классы](../../mfc/reference/mfc-classes.md)   
 [Класс CMFCColorBar](../../mfc/reference/cmfccolorbar-class.md)   
 [Класс CMFCPopupMenu](../../mfc/reference/cmfcpopupmenu-class.md)
