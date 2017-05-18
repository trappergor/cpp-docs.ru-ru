---
title: "Класс CMFCBaseVisualManager | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
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
- ~CMFCBaseVisualManager destructor
- CMFCBaseVisualManager class, destructor
- CMFCBaseVisualManager class
ms.assetid: d56f3afc-cdea-4de1-825a-a08999c571e0
caps.latest.revision: 24
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: 7c726fe71b7dcf26353fe0ce3a6b383eb5b578b9
ms.contentlocale: ru-ru
ms.lasthandoff: 02/24/2017

---
# <a name="cmfcbasevisualmanager-class"></a>Класс CMFCBaseVisualManager
Слой между производным API темы Windows и диспетчеров визуального представления.  
  
 `CMFCBaseVisualManager`загружает библиотеку UxTheme.dll, если он доступен и управляет доступом к методам API темы Windows.  
  
 Этот класс является только для внутреннего использования.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CMFCBaseVisualManager: public CObject  
```  
  
## <a name="members"></a>Члены  
  
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
|[CMFCBaseVisualManager::DrawCheckBox](#drawcheckbox)|Рисует элемент управления флажка с использованием текущей темы Windows.|  
|[CMFCBaseVisualManager::DrawComboBorder](#drawcomboborder)|Рисует границу поля со списком, с помощью текущей темы Windows.|  
|[CMFCBaseVisualManager::DrawComboDropButton](#drawcombodropbutton)|Рисует кнопку раскрывающегося списка поля со списком, с использованием текущей темы Windows.|  
|[CMFCBaseVisualManager::DrawPushButton](#drawpushbutton)|Рисует кнопку push с помощью текущей темы Windows.|  
|[CMFCBaseVisualManager::DrawRadioButton](#drawradiobutton)|Рисует элемент управления переключателя с помощью текущей темы Windows.|  
|[CMFCBaseVisualManager::DrawStatusBarProgress](#drawstatusbarprogress)|Выводит индикатор хода выполнения на элемент управления строки состояния ( [CMFCStatusBar класса](../../mfc/reference/cmfcstatusbar-class.md)) с использованием текущей темы Windows.|  
|[CMFCBaseVisualManager::FillReBarPane](#fillrebarpane)|Заполняет фон элемента управления главной панели с помощью текущей темы Windows.|  
|[CMFCBaseVisualManager::GetStandardWindowsTheme](#getstandardwindowstheme)|Возвращает текущую тему Windows.|  
  
### <a name="protected-methods"></a>Защищенные методы  
  
|||  
|-|-|  
|Имя|Описание|  
|[CMFCBaseVisualManager::CleanUpThemes](#cleanupthemes)|Вызовы `CloseThemeData` для получить все дескрипторы в `UpdateSystemColors`.|  
|[CMFCBaseVisualManager::UpdateSystemColors](#updatesystemcolors)|Вызывает `OpenThemeData` для получения дескрипторов для рисования различных элементов управления: windows, панели инструментов, кнопки и т. д.|  
  
## <a name="remarks"></a>Примечания  
 Необходимо непосредственно создать экземпляр объекта этого класса.  
  
 Поскольку базовый класс для всех диспетчеров визуального представления, можно просто вызвать [CMFCVisualManager::GetInstance](../../mfc/reference/cmfcvisualmanager-class.md#getinstance), получить указатель на текущий диспетчер Visual и методы для доступа к `CMFCBaseVisualManager` с помощью этого указателя. Однако, если для отображения элемента управления с помощью текущей темы Windows, лучше использовать `CMFCVisualManagerWindows` интерфейса.  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CMFCBaseVisualManager](../../mfc/reference/cmfcbasevisualmanager-class.md)  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxvisualmanager.h  
  
##  <a name="cleanupthemes"></a>CMFCBaseVisualManager::CleanUpThemes  
 Вызовы `CloseThemeData` для получить все дескрипторы в `UpdateSystemColors`.  
  
```  
void CleanUpThemes();
```  
  
### <a name="remarks"></a>Примечания  
 Только для внутреннего использования.  
  
##  <a name="cmfcbasevisualmanager"></a>CMFCBaseVisualManager::CMFCBaseVisualManager  
 Создает и инициализирует объект `CMFCBaseVisualManager`.  
  
```  
CMFCBaseVisualManager();
```  
  
##  <a name="drawcheckbox"></a>CMFCBaseVisualManager::DrawCheckBox  
 Рисует элемент управления флажка с использованием текущей темы Windows.  
  
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
 0 для флажок снят, 1 для отмеченных норм  
  
 2 для смешанных норм.  
  
 [in] `bEnabled`  
 Указывает, включен ли флажок.  
  
 [in] `bPressed`  
 Указывает, нажата ли флажок.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если тема API включено; в противном случае `FALSE`.  
  
### <a name="remarks"></a>Примечания  
 Значения `nState` соответствуют следующие стили флажок.  
  
|nState|Стиль флажка|  
|------------|---------------------|  
|0|CBS_UNCHECKEDNORMAL|  
|1|CBS_CHECKEDNORMAL|  
|2|CBS_MIXEDNORMAL|  
  
##  <a name="drawcomboborder"></a>CMFCBaseVisualManager::DrawComboBorder  
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
 Указывает, отключен ли граница поля со списком.  
  
 [in] `bIsDropped`  
 Указывает, удаляется ли граница поля со списком.  
  
 [in] `bIsHighlighted`  
 Указывает, выделяется ли граница поля со списком.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если тема API включено; в противном случае `FALSE`.  
  
##  <a name="drawcombodropbutton"></a>CMFCBaseVisualManager::DrawComboDropButton  
 Рисует кнопку раскрывающегося списка поля со списком, с использованием текущей темы Windows.  
  
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
|[in] `rect`|Ограничивающий прямоугольник кнопки раскрывающегося списка поля со списком.|  
|[in] `bDisabled`|Указывает, отключен ли кнопка раскрывающегося списка поля со списком.|  
|[in] `bIsDropped`|Указывает, удаляется ли кнопку раскрывающегося списка поля со списком.|  
|[in] `bIsHighlighted`|Указывает, выделяется ли кнопка раскрывающегося списка поля со списком.|  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если тема API включено; в противном случае `FALSE`.  
  
##  <a name="drawpushbutton"></a>CMFCBaseVisualManager::DrawPushButton  
 Рисует кнопку push с помощью текущей темы Windows.  
  
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
 `TRUE`Если тема API включено; в противном случае `FALSE`.  
  
##  <a name="drawradiobutton"></a>CMFCBaseVisualManager::DrawRadioButton  
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
 Ограничивающий прямоугольник переключатель.  
  
 [in] `bHighlighted`  
 Указывает, выделяется ли переключатель.  
  
 [in] `bChecked`  
 Указывает, установлен ли переключатель.  
  
 [in] `bEnabled`  
 Указывает, включен ли переключатель.  
  
 [in] `bPressed`  
 Указывает, нажата ли переключатель.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если тема API включено; в противном случае `FALSE`.  
  
##  <a name="drawstatusbarprogress"></a>CMFCBaseVisualManager::DrawStatusBarProgress  
 Выводит индикатор хода выполнения на элемент управления строки состояния ( [CMFCStatusBar класса](../../mfc/reference/cmfcstatusbar-class.md)) с использованием текущей темы Windows.  
  
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
 Ограничивающий прямоугольник индикатор `pDC` координаты.  
  
 [in] `nProgressTotal`  
 Значение общего хода выполнения.  
  
 [in] `nProgressCurr`  
 Текущее значение хода выполнения.  
  
 [in] `clrBar`  
 Начальный цвет. `CMFCBaseVisualManager`игнорирует это. Производные классы могут использовать его для цвета градиента.  
  
 [in] `clrProgressBarDest`  
 Конечный цвет. `CMFCBaseVisualManager`игнорирует это. Производные классы могут использовать его для цвета градиента.  
  
 [in] `clrProgressText`  
 Цвет текста хода выполнения. `CMFCBaseVisualManager`игнорирует это. Цвет текста определяется `afxGlobalData.clrBtnText`.  
  
 [in] `bProgressText`  
 Указывает, следует ли отображать сообщение о ходе выполнения.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если тема API включено; в противном случае `FALSE`.  
  
##  <a name="fillrebarpane"></a>CMFCBaseVisualManager::FillReBarPane  
 Заполняет фон элемента управления главной панели с помощью текущей темы Windows.  
  
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
 Указатель на область, фон должен быть нарисован.  
  
 [in] `rectClient`  
 Ограничивающий прямоугольник для заполнения области.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если тема API включено; в противном случае `FALSE`.  
  
##  <a name="getstandardwindowstheme"></a>CMFCBaseVisualManager::GetStandardWindowsTheme  
 Возвращает текущую тему Windows.  
  
```  
virtual WinXpTheme GetStandardWindowsTheme();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Выбранный цвет темы Windows. Может принимать одно из следующих значений:  
  
- `WinXpTheme_None`-Нет, тема не включена.  
  
- `WinXpTheme_NonStandard`-нестандартное темы выбран (то есть темы выбран, но нет в списке ниже).  
  
- `WinXpTheme_Blue`-Тема blue (Luna).  
  
- `WinXpTheme_Olive`-оливковым темы.  
  
- `WinXpTheme_Silver`-серебристая тема.  
  
##  <a name="updatesystemcolors"></a>CMFCBaseVisualManager::UpdateSystemColors  
 Вызывает `OpenThemeData` для получения дескрипторов для рисования различных элементов управления: windows, панели инструментов, кнопки и т. д.  
  
```  
void UpdateSystemColors();
```  
  
### <a name="remarks"></a>Примечания  
 Только для внутреннего использования.  
  
## <a name="see-also"></a>См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Классы](../../mfc/reference/mfc-classes.md)

