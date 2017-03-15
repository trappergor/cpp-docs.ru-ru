---
title: "Класс CMFCPopupMenuBar | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCPopupMenuBar
dev_langs:
- C++
helpviewer_keywords:
- CMFCPopupMenuBar class
ms.assetid: 4c93c459-7f70-4240-8c63-280bb811e374
caps.latest.revision: 32
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 46f86035fecc16c45e01a1c70cdde610093d377b
ms.lasthandoff: 02/24/2017

---
# <a name="cmfcpopupmenubar-class"></a>Класс CMFCPopupMenuBar
Строка меню, внедренная в контекстное меню.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CMFCPopupMenuBar : public CMFCToolBar  
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CMFCPopupMenuBar::AdjustSizeImmediate](#adjustsizeimmediate)|Немедленно повторно вычисляет макет панели. (Переопределяет [CPane::AdjustSizeImmediate](../../mfc/reference/cpane-class.md#adjustsizeimmediate).)|  
|[CMFCPopupMenuBar::BuildOrigItems](#buildorigitems)|Загружает элементы всплывающего меню из меню указанного ресурса.|  
|[CMFCPopupMenuBar::CloseDelayedSubMenu](#closedelayedsubmenu)|Закрывает кнопку отложенной контекстного меню.|  
|[CMFCPopupMenuBar::ExportToMenu](#exporttomenu)|Выводит на экран меню с помощью кнопок всплывающее меню.|  
|[CMFCPopupMenuBar::FindDestintationToolBar](#finddestintationtoolbar)|Находит панели инструментов, в которой находится указанная точка.|  
|[CMFCPopupMenuBar::GetCurrentMenuImageSize](#getcurrentmenuimagesize)|Указывает размер изображения кнопки меню.|  
|[CMFCPopupMenuBar::GetDefaultMenuId](#getdefaultmenuid)|Возвращает идентификатор элемента меню по умолчанию.|  
|[CMFCPopupMenuBar::GetLastCommandIndex](#getlastcommandindex)|Возвращает индекс наиболее недавно вызванной команды меню.|  
|[CMFCPopupMenuBar::GetOffset](#getoffset)|Возвращает смещение строки всплывающее меню.|  
|[CMFCPopupMenuBar::ImportFromMenu](#importfrommenu)|Импортирует всплывающее меню кнопки указанного меню.|  
|[CMFCPopupMenuBar::IsDropDownListMode](#isdropdownlistmode)|Указывает, является ли всплывающее меню в раскрывающемся списке режиме.|  
|[CMFCPopupMenuBar::IsPaletteMode](#ispalettemode)|Указывает, является ли всплывающее меню в режиме палитры.|  
|[CMFCPopupMenuBar::IsRibbonPanel](#isribbonpanel)|Указывает, является ли панель ленты ( `FALSE` по умолчанию).|  
|[CMFCPopupMenuBar::IsRibbonPanelInRegularMode](#isribbonpanelinregularmode)|Указывает, является ли панель ленты в обычном режиме ( `FALSE` по умолчанию).|  
|[CMFCPopupMenuBar::LoadFromHash](#loadfromhash)|Загружает архивные меню.|  
|[CMFCPopupMenuBar::RestoreDelayedSubMenu](#restoredelayedsubmenu)|Восстанавливает отложенной меню кнопку для закрытия всплывающего меню.|  
|[CMFCPopupMenuBar::SetButtonStyle](#setbuttonstyle)|Задает стиль кнопки панели инструментов с указанным индексом. (Переопределяет [CMFCToolBar::SetButtonStyle](../../mfc/reference/cmfctoolbar-class.md#setbuttonstyle).)|  
|[CMFCPopupMenuBar::SetOffset](#setoffset)|Задает смещение строки всплывающее меню.|  
|[CMFCPopupMenuBar::StartPopupMenuTimer](#startpopupmenutimer)|Запускает таймер для указанной отложенной всплывающее меню кнопки.|  
  
### <a name="data-members"></a>Элементы данных  
  
|Имя|Описание|  
|----------|-----------------|  
|[CMFCPopupMenuBar::m_bDisableSideBarInXPMode](#m_bdisablesidebarinxpmode)|Указывает, могут ли серую полосу будет отображаться, когда приложение имеет внешний вид Windows XP.|  
  
## <a name="remarks"></a>Примечания  
 `CMFCPopupMenuBar` Создается в то же время, как [CMFCPopupMenu класса](../../mfc/reference/cmfcpopupmenu-class.md) и внедрение внутри него. `CMFCPopupMenuBar` Охватывает всю клиентскую область `CMFCPopupMenu` объекта. Он поддерживает клавиатуры и мыши. Он взаимодействует, что вход `CMFCPopupMenu` и в окно верхнего уровня кадра.  
  
## <a name="example"></a>Пример  
 Ниже приведен пример, как инициализировать `CMFCPopupMenuBar` объекта из `CMFCPopupMenu` объекта. Этот фрагмент кода является частью [пример рисования клиента](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_DrawClient&#7;](../../mfc/reference/codesnippet/cpp/cmfcpopupmenubar-class_1.cpp)]  
  
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
  
##  <a name="a-nameadjustsizeimmediatea--cmfcpopupmenubaradjustsizeimmediate"></a><a name="adjustsizeimmediate"></a>CMFCPopupMenuBar::AdjustSizeImmediate  
 Немедленно повторно вычисляет макет панели всплывающее меню строки. (Переопределяет [CPane::AdjustSizeImmediate](../../mfc/reference/cpane-class.md#adjustsizeimmediate).  
  
```  
virtual void AdjustSizeImmediate(BOOL bRecalcLayout);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `bRecalcLayout`  
 `TRUE`автоматически пересчитать макет области панели всплывающее меню. в противном случае — `FALSE`.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-namebuildorigitemsa--cmfcpopupmenubarbuildorigitems"></a><a name="buildorigitems"></a>CMFCPopupMenuBar::BuildOrigItems  
 Загружает элементы всплывающего меню из меню указанного ресурса.  
  
```  
BOOL BuildOrigItems(UINT uiMenuResID);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `uiMenuResID`  
 Указывает идентификатор ресурса меню меню загрузки.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает `TRUE` в случае успешного выполнения или `FALSE` Если нет.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-nameclosedelayedsubmenua--cmfcpopupmenubarclosedelayedsubmenu"></a><a name="closedelayedsubmenu"></a>CMFCPopupMenuBar::CloseDelayedSubMenu  
 Закрывает кнопку контекстного меню, которое было отложено.  
  
```  
virtual void CloseDelayedSubMenu();
```  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-nameexporttomenua--cmfcpopupmenubarexporttomenu"></a><a name="exporttomenu"></a>CMFCPopupMenuBar::ExportToMenu  
 Выводит на экран меню с помощью кнопок всплывающее меню.  
  
```  
virtual HMENU ExportToMenu() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает дескриптор новое меню.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-namefinddestintationtoolbara--cmfcpopupmenubarfinddestintationtoolbar"></a><a name="finddestintationtoolbar"></a>CMFCPopupMenuBar::FindDestintationToolBar  
 Находит панели инструментов, в которой находится указанная точка.  
  
```  
CMFCToolBar* FindDestintationToolBar(CPoint point);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `point`  
 Точка на экране.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает дескриптор панели инструментов где находится точка, если therei, или `NULL` Если нет.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-namegetcurrentmenuimagesizea--cmfcpopupmenubargetcurrentmenuimagesize"></a><a name="getcurrentmenuimagesize"></a>CMFCPopupMenuBar::GetCurrentMenuImageSize  
 Указывает размер изображения кнопки меню.  
  
```  
virtual CSize GetCurrentMenuImageSize() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает размер изображений кнопки меню на панели инструментов.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-namegetdefaultmenuida--cmfcpopupmenubargetdefaultmenuid"></a><a name="getdefaultmenuid"></a>CMFCPopupMenuBar::GetDefaultMenuId  
 Возвращает идентификатор элемента меню по умолчанию.  
  
```  
UINT GetDefaultMenuId() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает идентификатор элемента меню по умолчанию в всплывающем меню.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-namegetlastcommandindexa--cmfcpopupmenubargetlastcommandindex"></a><a name="getlastcommandindex"></a>CMFCPopupMenuBar::GetLastCommandIndex  
 Возвращает индекс наиболее недавно вызванной команды меню.  
  
```  
static int __stdcall GetLastCommandIndex();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает индекс последней команды меню, которая была вызвана.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-namegetoffseta--cmfcpopupmenubargetoffset"></a><a name="getoffset"></a>CMFCPopupMenuBar::GetOffset  
 Возвращает смещение строки всплывающее меню.  
  
```  
int GetOffset() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает смещение строки всплывающее меню.  
  
### <a name="remarks"></a>Примечания  
 Это значение задается с помощью [CMFCPopupMenuBar::SetOffset](#setoffset).  
  
##  <a name="a-nameimportfrommenua--cmfcpopupmenubarimportfrommenu"></a><a name="importfrommenu"></a>CMFCPopupMenuBar::ImportFromMenu  
 Импортирует всплывающее меню кнопки указанного меню.  
  
```  
virtual BOOL ImportFromMenu(
    HMENU hMenu,  
    BOOL bShowAllCommands = FALSE);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `hMenu`  
 Меню, из которого следует импортировать кнопок всплывающее меню.  
  
 [in] `bShowAllCommands`  
 `TRUE`Если необходимо импортировать все команды в меню или `FALSE` Если редко используемых может быть скрыт.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает `TRUE` Если кнопки меню успешно импортированы из меню или `FALSE` Если нет.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-nameisdropdownlistmodea--cmfcpopupmenubarisdropdownlistmode"></a><a name="isdropdownlistmode"></a>CMFCPopupMenuBar::IsDropDownListMode  
 Указывает, является ли всплывающее меню в раскрывающемся списке режиме.  
  
```  
BOOL IsDropDownListMode() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает `TRUE` если всплывающее меню в раскрывающемся списке режиме или `FALSE` Если нет.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-nameispalettemodea--cmfcpopupmenubarispalettemode"></a><a name="ispalettemode"></a>CMFCPopupMenuBar::IsPaletteMode  
 Указывает, является ли всплывающее меню в режиме палитры.  
  
```  
BOOL IsPaletteMode() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает `TRUE` при включении режима палитру или `FALSE` Если нет.  
  
### <a name="remarks"></a>Примечания  
 Если меню устанавливается режим палитру, элементы меню появляются в нескольких столбцах и ограниченное число строк.  
  
##  <a name="a-nameisribbonpanela--cmfcpopupmenubarisribbonpanel"></a><a name="isribbonpanel"></a>CMFCPopupMenuBar::IsRibbonPanel  
 Указывает, является ли панель ленты ( `FALSE` по умолчанию).  
  
```  
virtual BOOL IsRibbonPanel() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает `FALSE` по умолчанию, указывающее на то, что это не панель ленты.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-nameisribbonpanelinregularmodea--cmfcpopupmenubarisribbonpanelinregularmode"></a><a name="isribbonpanelinregularmode"></a>CMFCPopupMenuBar::IsRibbonPanelInRegularMode  
 Указывает, является ли панель ленты в обычном режиме ( `FALSE` по умолчанию).  
  
```  
virtual BOOL IsRibbonPanelInRegularMode() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает `FALSE` по умолчанию, указывающее на то, что это не панель ленты в обычном режиме.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-nameloadfromhasha--cmfcpopupmenubarloadfromhash"></a><a name="loadfromhash"></a>CMFCPopupMenuBar::LoadFromHash  
 Загружает архивные меню.  
  
```  
BOOL LoadFromHash(HMENU hMenu);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `hMenu`  
 Дескриптор архивные меню загрузки.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает `TRUE` меню загружается успешно, или `FALSE` Если нет.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-namembdisablesidebarinxpmodea--cmfcpopupmenubarmbdisablesidebarinxpmode"></a><a name="m_bdisablesidebarinxpmode"></a>CMFCPopupMenuBar::m_bDisableSideBarInXPMode  
 Параметр типа Boolean, указывающее, имеет ли приложение серую полосу, если он имеет вид Windows XP.  
  
```  
BOOL m_bDisableSideBarInXPMode;  
```  
  
### <a name="remarks"></a>Примечания  
 Если значение переменной-члена `FALSE` и приложение имеет внешний вид Windows XP, платформа строит серую полосу в приложении.  
  
 Значение по умолчанию — `FALSE`.  
  
##  <a name="a-namerestoredelayedsubmenua--cmfcpopupmenubarrestoredelayedsubmenu"></a><a name="restoredelayedsubmenu"></a>CMFCPopupMenuBar::RestoreDelayedSubMenu  
 Восстанавливает отложенной меню кнопку для закрытия всплывающего меню.  
  
```  
virtual void RestoreDelayedSubMenu();
```  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-namesetbuttonstylea--cmfcpopupmenubarsetbuttonstyle"></a><a name="setbuttonstyle"></a>CMFCPopupMenuBar::SetButtonStyle  
 Задает стиль кнопки панели инструментов с указанным индексом. (Переопределяет [CMFCToolBar::SetButtonStyle](../../mfc/reference/cmfctoolbar-class.md#setbuttonstyle).)  
  
```  
virtual void SetButtonStyle(
    int nIndex,  
    UINT nStyle);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `nIndex`  
 Отсчитываемый от нуля индекс кнопки панели инструментов, стиль которого требуется задать.  
  
 [in] `nStyle`  
 Стиль кнопки. В разделе [стили элемента управления панели инструментов](../../mfc/reference/toolbar-control-styles.md) список имеющихся на панели инструментов кнопку Стили.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-namesetoffseta--cmfcpopupmenubarsetoffset"></a><a name="setoffset"></a>CMFCPopupMenuBar::SetOffset  
 Задает смещение строки всплывающее меню.  
  
```  
void SetOffset(int iOffset);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `iOffset`  
 Число строк, что всплывающее меню быть смещены.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-namestartpopupmenutimera--cmfcpopupmenubarstartpopupmenutimer"></a><a name="startpopupmenutimer"></a>CMFCPopupMenuBar::StartPopupMenuTimer  
 Запускает таймер для указанной отложенной всплывающее меню кнопки.  
  
```  
void StartPopupMenuTimer(
    CMFCToolBarMenuButton* pMenuButton,  
    int nDelayFactor = 1);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pMenuButton`  
 Указатель на кнопке меню, для которого требуется задать таймер задержки.  
  
 [in] `nDelayFactor`  
 Задержка коэффициент, равное по крайней мере один, необходимо умножить время задержки стандартные меню (как правило, от половины секунды и пять секунд).  
  
### <a name="remarks"></a>Примечания  
  
## <a name="see-also"></a>См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Классы](../../mfc/reference/mfc-classes.md)   
 [Класс CMFCColorBar](../../mfc/reference/cmfccolorbar-class.md)   
 [Класс CMFCPopupMenu](../../mfc/reference/cmfcpopupmenu-class.md)

