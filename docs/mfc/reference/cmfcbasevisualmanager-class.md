---
title: Класс CMFCBaseVisualManager | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CMFCBaseVisualManager
- AFXVISUALMANAGER/CMFCBaseVisualManager
- AFXVISUALMANAGER/CMFCBaseVisualManager::CMFCBaseVisualManager
- AFXVISUALMANAGER/CMFCBaseVisualManager::DrawCheckBox
- AFXVISUALMANAGER/CMFCBaseVisualManager::DrawComboBorder
- AFXVISUALMANAGER/CMFCBaseVisualManager::DrawComboDropButton
- AFXVISUALMANAGER/CMFCBaseVisualManager::DrawPushButton
- AFXVISUALMANAGER/CMFCBaseVisualManager::DrawRadioButton
- AFXVISUALMANAGER/CMFCBaseVisualManager::DrawStatusBarProgress
- AFXVISUALMANAGER/CMFCBaseVisualManager::FillReBarPane
- AFXVISUALMANAGER/CMFCBaseVisualManager::GetStandardWindowsTheme
- AFXVISUALMANAGER/CMFCBaseVisualManager::CleanUpThemes
- AFXVISUALMANAGER/CMFCBaseVisualManager::UpdateSystemColors
dev_langs:
- C++
helpviewer_keywords:
- CMFCBaseVisualManager [MFC], CMFCBaseVisualManager
- CMFCBaseVisualManager [MFC], DrawCheckBox
- CMFCBaseVisualManager [MFC], DrawComboBorder
- CMFCBaseVisualManager [MFC], DrawComboDropButton
- CMFCBaseVisualManager [MFC], DrawPushButton
- CMFCBaseVisualManager [MFC], DrawRadioButton
- CMFCBaseVisualManager [MFC], DrawStatusBarProgress
- CMFCBaseVisualManager [MFC], FillReBarPane
- CMFCBaseVisualManager [MFC], GetStandardWindowsTheme
- CMFCBaseVisualManager [MFC], CleanUpThemes
- CMFCBaseVisualManager [MFC], UpdateSystemColors
ms.assetid: d56f3afc-cdea-4de1-825a-a08999c571e0
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 496c6905276e789a72c55db1835187b0d4ab342a
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33369155"
---
# <a name="cmfcbasevisualmanager-class"></a>Класс CMFCBaseVisualManager
Логический уровень между производном визуальными диспетчерами и темы Windows API.  
  
 `CMFCBaseVisualManager` загружает библиотеку UxTheme.dll, если он доступен и управляет доступом к методам темы Windows API.  
  
 Этот класс является только для внутреннего использования.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CMFCBaseVisualManager: public CObject  
```  
  
## <a name="members"></a>Участники  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|||  
|-|-|  
|Имя|Описание|  
|[CMFCBaseVisualManager::CMFCBaseVisualManager](#cmfcbasevisualmanager)|Создает и инициализирует объект `CMFCBaseVisualManager`.|  
|`CMFCBaseVisualManager::~CMFCBaseVisualManager`|Деструктор.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|||  
|-|-|  
|Имя|Описание|  
|[CMFCBaseVisualManager::DrawCheckBox](#drawcheckbox)|Рисует элемент управления "флажок" с помощью текущей темы Windows.|  
|[CMFCBaseVisualManager::DrawComboBorder](#drawcomboborder)|Рисует границу поля со списком, с помощью текущей темы Windows.|  
|[CMFCBaseVisualManager::DrawComboDropButton](#drawcombodropbutton)|Рисует кнопку раскрывающегося списка поле со списком, с помощью текущей темы Windows.|  
|[CMFCBaseVisualManager::DrawPushButton](#drawpushbutton)|Рисует текущей темы Windows с помощью кнопки.|  
|[CMFCBaseVisualManager::DrawRadioButton](#drawradiobutton)|Рисует элемент управления переключателя с помощью текущей темы Windows.|  
|[CMFCBaseVisualManager::DrawStatusBarProgress](#drawstatusbarprogress)|Рисует индикатор хода выполнения в строке состояния ( [CMFCStatusBar класса](../../mfc/reference/cmfcstatusbar-class.md)) с помощью текущей темы Windows.|  
|[CMFCBaseVisualManager::FillReBarPane](#fillrebarpane)|Заполняет фон элемента управления главной панели, используя текущую тему Windows.|  
|[CMFCBaseVisualManager::GetStandardWindowsTheme](#getstandardwindowstheme)|Возвращает текущую тему Windows.|  
  
### <a name="protected-methods"></a>Защищенные методы  
  
|||  
|-|-|  
|Имя|Описание|  
|[CMFCBaseVisualManager::CleanUpThemes](#cleanupthemes)|Вызовы `CloseThemeData` для полученных все дескрипторы `UpdateSystemColors`.|  
|[CMFCBaseVisualManager::UpdateSystemColors](#updatesystemcolors)|Вызовы `OpenThemeData` для получения дескрипторов для рисования различных элементов: windows, панели инструментов, кнопки и т. д.|  
  
## <a name="remarks"></a>Примечания  
 Необходимо создать экземпляр объекта этого класса напрямую.  
  
 Так как это базовый класс для всех диспетчеров визуального представления может просто вызвать [CMFCVisualManager::GetInstance](../../mfc/reference/cmfcvisualmanager-class.md#getinstance), получить указатель на текущий диспетчер Visual и методы для доступа к `CMFCBaseVisualManager` с помощью этого указателя. Тем не менее, если для отображения элемента управления с помощью текущей темы Windows, лучше использовать `CMFCVisualManagerWindows` интерфейса.  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CMFCBaseVisualManager](../../mfc/reference/cmfcbasevisualmanager-class.md)  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxvisualmanager.h  
  
##  <a name="cleanupthemes"></a>  CMFCBaseVisualManager::CleanUpThemes  
 Вызовы `CloseThemeData` для полученных все дескрипторы `UpdateSystemColors`.  
  
```  
void CleanUpThemes();
```  
  
### <a name="remarks"></a>Примечания  
 Только для внутреннего использования.  
  
##  <a name="cmfcbasevisualmanager"></a>  CMFCBaseVisualManager::CMFCBaseVisualManager  
 Создает и инициализирует объект `CMFCBaseVisualManager`.  
  
```  
CMFCBaseVisualManager();
```  
  
##  <a name="drawcheckbox"></a>  CMFCBaseVisualManager::DrawCheckBox  
 Рисует элемент управления "флажок" с помощью текущей темы Windows.  
  
```  
virtual BOOL DrawCheckBox(
    CDC* pDC,   
    CRect rect,   
    BOOL bHighlighted,   
    int nState,   
    BOOL bEnabled,   
    BOOL bPressed);

);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pDC`  
 Указатель на контекст устройства  
  
 [in] `rect`  
 Ограничивающий прямоугольник флажок.  
  
 [in] `bHighlighted`  
 Указывает, выделяется ли флажок.  
  
 [in] `nState`  
 0 для флажок снят, 1 для отмеченных обычный  
  
 2 для смешанных normal.  
  
 [in] `bEnabled`  
 Указывает, включен ли флажок.  
  
 [in] `bPressed`  
 Указывает, нажата ли флажок.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE` Если включен API темы. в противном случае `FALSE`.  
  
### <a name="remarks"></a>Примечания  
 Значения `nState` соответствуют следующие стили флажок.  
  
|nState|Стиль флажка|  
|------------|---------------------|  
|0|CBS_UNCHECKEDNORMAL|  
|1|CBS_CHECKEDNORMAL|  
|2|CBS_MIXEDNORMAL|  
  
##  <a name="drawcomboborder"></a>  CMFCBaseVisualManager::DrawComboBorder  
 Рисует границу поля со списком, с помощью текущей темы Windows.  
  
```  
virtual BOOL DrawComboBorder(
    CDC* pDC,   
    CRect rect,   
    BOOL bDisabled,   
    BOOL bIsDropped,   
    BOOL bIsHighlighted);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pDC`  
 Указатель на контекст устройства.  
  
 [in] `rect`  
 Ограничивающий прямоугольник границы поля со списком.  
  
 [in] `bDisabled`  
 Указывает, отключен ли границы поля со списком.  
  
 [in] `bIsDropped`  
 Указывает, удаляется ли границы поля со списком.  
  
 [in] `bIsHighlighted`  
 Указывает, выделяется ли границы поля со списком.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE` Если включен API темы. в противном случае `FALSE`.  
  
##  <a name="drawcombodropbutton"></a>  CMFCBaseVisualManager::DrawComboDropButton  
 Рисует кнопку раскрывающегося списка поле со списком, с помощью текущей темы Windows.  
  
```  
virtual BOOL DrawComboDropButton(
    CDC* pDC,   
    CRect rect,   
    BOOL bDisabled,   
    BOOL bIsDropped,   
    BOOL bIsHighlighted);
```  
  
### <a name="parameters"></a>Параметры  
  
|Параметр|Описание|  
|---------------|-----------------|  
|[in] `pDC`|Указатель на контекст устройства.|  
|[in] `rect`|Ограничивающий прямоугольник кнопку раскрывающегося списка поля со списком.|  
|[in] `bDisabled`|Указывает, отключен ли кнопка раскрывающегося списка поля со списком.|  
|[in] `bIsDropped`|Указывает, удаляется ли кнопка раскрывающегося списка поля со списком.|  
|[in] `bIsHighlighted`|Указывает, выделяется ли кнопка раскрывающегося списка поля со списком.|  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE` Если включен API темы. в противном случае `FALSE`.  
  
##  <a name="drawpushbutton"></a>  CMFCBaseVisualManager::DrawPushButton  
 Рисует текущей темы Windows с помощью кнопки.  
  
```  
virtual BOOL DrawPushButton(
    CDC* pDC,   
    CRect rect,   
    CMFCButton* pButton,   
    UINT uiState);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pDC`  
 Указатель на контекст устройства.  
  
 [in] `rect`  
 Ограничивающий прямоугольник кнопки.  
  
 [in] `pButton`  
 Указатель на [CMFCButton класса](../../mfc/reference/cmfcbutton-class.md) для рисования.  
  
 [in] `uiState`  
 Не обрабатывается. Состояние берется из `pButton`.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE` Если включен API темы. в противном случае `FALSE`.  
  
##  <a name="drawradiobutton"></a>  CMFCBaseVisualManager::DrawRadioButton  
 Рисует элемент управления переключателя с помощью текущей темы Windows.  
  
```  
virtual BOOL DrawRadioButton(
    CDC* pDC,   
    CRect rect,   
    BOOL bHighlighted,   
    BOOL bChecked,   
    BOOL bEnabled,   
    BOOL bPressed);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pDC`  
 Указатель на контекст устройства.  
  
 [in] `rect`  
 Ограничивающий прямоугольник "переключатель".  
  
 [in] `bHighlighted`  
 Указывает, выделяется ли переключатель.  
  
 [in] `bChecked`  
 Указывает, установлен ли переключатель.  
  
 [in] `bEnabled`  
 Указывает, включен ли переключатель.  
  
 [in] `bPressed`  
 Указывает, нажата ли переключатель.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE` Если включен API темы. в противном случае `FALSE`.  
  
##  <a name="drawstatusbarprogress"></a>  CMFCBaseVisualManager::DrawStatusBarProgress  
 Рисует индикатор хода выполнения в строке состояния ( [CMFCStatusBar класса](../../mfc/reference/cmfcstatusbar-class.md)) с помощью текущей темы Windows.  
  
```  
virtual BOOL DrawStatusBarProgress(
    CDC* pDC,   
    CMFCStatusBar* pStatusBar,   
    CRect rectProgress,   
    int nProgressTotal,   
    int nProgressCurr,  
    COLORREF clrBar,   
    COLORREF clrProgressBarDest,   
    COLORREF clrProgressText,   
    BOOL bProgressText);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pDC`  
 Указатель на контекст устройства.  
  
 [in] `pStatusBar`  
 Указатель на строку состояния. Это значение игнорируется.  
  
 [in] `rectProgress`  
 Ограничивающий прямоугольник индикатор выполнения `pDC` координаты.  
  
 [in] `nProgressTotal`  
 Значение общего хода выполнения.  
  
 [in] `nProgressCurr`  
 Текущее значение хода выполнения.  
  
 [in] `clrBar`  
 Начальный цвет. `CMFCBaseVisualManager` игнорирует это. Производные классы могут использовать его для цветовые градиенты.  
  
 [in] `clrProgressBarDest`  
 Конечный цвет. `CMFCBaseVisualManager` игнорирует это. Производные классы могут использовать его для цветовые градиенты.  
  
 [in] `clrProgressText`  
 Цвет текста хода выполнения. `CMFCBaseVisualManager` игнорирует это. Цвет текста определяется `afxGlobalData.clrBtnText`.  
  
 [in] `bProgressText`  
 Указывает, следует ли отображать сообщение о ходе выполнения.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE` Если включен API темы. в противном случае `FALSE`.  
  
##  <a name="fillrebarpane"></a>  CMFCBaseVisualManager::FillReBarPane  
 Заполняет фон элемента управления главной панели, используя текущую тему Windows.  
  
```  
virtual void FillReBarPane(
    CDC* pDC,   
    CBasePane* pBar,   
    CRect rectClient);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pDC`  
 Указатель на контекст устройства.  
  
 [in] `pBar`  
 Указатель на панель, фон должно отображаться.  
  
 [in] `rectClient`  
 Ограничивающий прямоугольник для заполнения области.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE` Если включен API темы. в противном случае `FALSE`.  
  
##  <a name="getstandardwindowstheme"></a>  CMFCBaseVisualManager::GetStandardWindowsTheme  
 Возвращает текущую тему Windows.  
  
```  
virtual WinXpTheme GetStandardWindowsTheme();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Выбранный цвет темы Windows. Может принимать одно из следующих значений:  
  
- `WinXpTheme_None` -Нет тема не включена.  
  
- `WinXpTheme_NonStandard` -нестандартное темы выбран (то есть тема установлен, но ни один из списка ниже).  
  
- `WinXpTheme_Blue` -Тема blue (Luna).  
  
- `WinXpTheme_Olive` -оливковым темы.  
  
- `WinXpTheme_Silver` -серебристая тема.  
  
##  <a name="updatesystemcolors"></a>  CMFCBaseVisualManager::UpdateSystemColors  
 Вызовы `OpenThemeData` для получения дескрипторов для рисования различных элементов: windows, панели инструментов, кнопки и т. д.  
  
```  
void UpdateSystemColors();
```  
  
### <a name="remarks"></a>Примечания  
 Только для внутреннего использования.  
  
## <a name="see-also"></a>См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Классы](../../mfc/reference/mfc-classes.md)
