---
title: Класс CMFCBaseVisualManager | Документация Майкрософт
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
ms.openlocfilehash: ec48152b918fb43cf859377e64eeb64478ad15f3
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46374279"
---
# <a name="cmfcbasevisualmanager-class"></a>Класс CMFCBaseVisualManager

Уровень между производном диспетчеров визуального представления и интерфейс API темы оформления Windows.

`CMFCBaseVisualManager` загружает библиотеку UxTheme.dll, в том случае, если он доступен и управляет доступом к методам API темы Windows.

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
|[CMFCBaseVisualManager::DrawComboBorder](#drawcomboborder)|Рисует границу поле со списком, с помощью текущей темы Windows.|
|[CMFCBaseVisualManager::DrawComboDropButton](#drawcombodropbutton)|Рисует кнопку раскрывающегося списка поле со списком, с помощью текущей темы Windows.|
|[CMFCBaseVisualManager::DrawPushButton](#drawpushbutton)|Рисует кнопку Push-уведомлений с помощью текущей темы Windows.|
|[CMFCBaseVisualManager::DrawRadioButton](#drawradiobutton)|Рисует элемент управления переключателя с помощью текущей темы Windows.|
|[CMFCBaseVisualManager::DrawStatusBarProgress](#drawstatusbarprogress)|Рисует на элементе управления полосы состояния индикатор хода выполнения ( [класс CMFCStatusBar](../../mfc/reference/cmfcstatusbar-class.md)) с помощью текущей темы Windows.|
|[CMFCBaseVisualManager::FillReBarPane](#fillrebarpane)|Заполняет фона элемента управления "Главная панель", используя текущую тему Windows.|
|[CMFCBaseVisualManager::GetStandardWindowsTheme](#getstandardwindowstheme)|Получает текущую тему Windows.|

### <a name="protected-methods"></a>Защищенные методы

|||
|-|-|
|Имя|Описание|
|[CMFCBaseVisualManager::CleanUpThemes](#cleanupthemes)|Вызовы `CloseThemeData` для получить все дескрипторы в `UpdateSystemColors`.|
|[CMFCBaseVisualManager::UpdateSystemColors](#updatesystemcolors)|Вызовы `OpenThemeData` для получения дескрипторов для рисования различных элементов управления: windows, панелей инструментов, кнопок и т. д.|

## <a name="remarks"></a>Примечания

У вас нет непосредственно создать экземпляр объекта этого класса.

Так как он является базовым классом для всех диспетчеров визуального представления, можно просто вызвать [CMFCVisualManager::GetInstance](../../mfc/reference/cmfcvisualmanager-class.md#getinstance), получить указатель на текущий диспетчер Visual и получить доступ к методам для `CMFCBaseVisualManager` с помощью этого указателя. Тем не менее, если для отображения элемента управления с помощью текущей темы Windows, лучше использовать `CMFCVisualManagerWindows` интерфейс.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CMFCBaseVisualManager](../../mfc/reference/cmfcbasevisualmanager-class.md)

## <a name="requirements"></a>Требования

**Заголовок:** afxvisualmanager.h

##  <a name="cleanupthemes"></a>  CMFCBaseVisualManager::CleanUpThemes

Вызовы `CloseThemeData` для получить все дескрипторы в `UpdateSystemColors`.

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

*основного контроллера домена*<br/>
[in] Указатель на контекст устройства

*Rect*<br/>
[in] Ограничивающий прямоугольник поля с флажком.

*bHighlighted*<br/>
[in] Указывает, выделена ли флажок.

*nState*<br/>
[in] 0 для 1, этот флажок снят, для отмеченных normal

2 для смешанных normal.

*bEnabled*<br/>
[in] Указывает, включен ли флажок.

*bPressed*<br/>
[in] Указывает, нажата ли флажок.

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если включен интерфейс API темы оформления. в противном случае — значение FALSE.

### <a name="remarks"></a>Примечания

Значения *nState* соответствуют следующие стили "флажок".

|nState|Стиль "флажок"|
|------------|---------------------|
|0|CBS_UNCHECKEDNORMAL|
|1|CBS_CHECKEDNORMAL|
|2|CBS_MIXEDNORMAL|

##  <a name="drawcomboborder"></a>  CMFCBaseVisualManager::DrawComboBorder

Рисует границу поле со списком, с помощью текущей темы Windows.

```
virtual BOOL DrawComboBorder(
    CDC* pDC,
    CRect rect,
    BOOL bDisabled,
    BOOL bIsDropped,
    BOOL bIsHighlighted);
```

### <a name="parameters"></a>Параметры

*основного контроллера домена*<br/>
[in] Указатель на контекст устройства.

*Rect*<br/>
[in] Ограничивающий прямоугольник границы поля со списком.

*bDisabled*<br/>
[in] Указывает, отключен ли граница поля со списком.

*bIsDropped*<br/>
[in] Указывает, удаляется ли граница поля со списком.

*bIsHighlighted*<br/>
[in] Указывает, выделена ли граница поля со списком.

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если включен интерфейс API темы оформления. в противном случае — значение FALSE.

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
|*основного контроллера домена*|[in] Указатель на контекст устройства.|
|*Rect*|[in] Ограничивающий прямоугольник кнопки раскрывающегося списка поле со списком.|
|*bDisabled*|[in] Указывает, отключен ли кнопка раскрывающегося списка поле со списком.|
|*bIsDropped*|[in] Указывает, удаляется ли кнопка раскрывающегося списка поле со списком.|
|*bIsHighlighted*|[in] Указывает, выделена ли кнопка раскрывающегося списка поле со списком.|

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если включен интерфейс API темы оформления. в противном случае — значение FALSE.

##  <a name="drawpushbutton"></a>  CMFCBaseVisualManager::DrawPushButton

Рисует кнопку Push-уведомлений с помощью текущей темы Windows.

```
virtual BOOL DrawPushButton(
    CDC* pDC,
    CRect rect,
    CMFCButton* pButton,
    UINT uiState);
```

### <a name="parameters"></a>Параметры

*основного контроллера домена*<br/>
[in] Указатель на контекст устройства.

*Rect*<br/>
[in] Ограничивающий прямоугольник кнопки.

*pButton*<br/>
[in] Указатель на [класс CMFCButton](../../mfc/reference/cmfcbutton-class.md) для рисования.

*uiState*<br/>
[in] Игнорируется. Состояние берется из *pButton*.

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если включен интерфейс API темы оформления. в противном случае — значение FALSE.

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

*основного контроллера домена*<br/>
[in] Указатель на контекст устройства.

*Rect*<br/>
[in] Ограничивающий прямоугольник переключателя.

*bHighlighted*<br/>
[in] Указывает, выделена ли переключатель.

*bChecked*<br/>
[in] Указывает, установлен ли переключатель.

*bEnabled*<br/>
[in] Указывает, включен ли переключатель.

*bPressed*<br/>
[in] Указывает, нажата ли переключатель.

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если включен интерфейс API темы оформления. в противном случае — значение FALSE.

##  <a name="drawstatusbarprogress"></a>  CMFCBaseVisualManager::DrawStatusBarProgress

Выводит индикатор хода выполнения на строки состояния ( [класс CMFCStatusBar](../../mfc/reference/cmfcstatusbar-class.md)) с помощью текущей темы Windows.

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

*основного контроллера домена*<br/>
[in] Указатель на контекст устройства.

*pStatusBar*<br/>
[in] Указатель на строку состояния. Это значение игнорируется.

*rectProgress*<br/>
[in] Ограничивающий прямоугольник индикатора в *pDC* координаты.

*nProgressTotal*<br/>
[in] Значение общего хода выполнения.

*nProgressCurr*<br/>
[in] Текущее значение хода выполнения.

*clrBar*<br/>
[in] Начальный цвет. `CMFCBaseVisualManager` игнорирует это. Производные классы могут использовать его для цветовые градиенты.

*clrProgressBarDest*<br/>
[in] Конечный цвет. `CMFCBaseVisualManager` игнорирует это. Производные классы могут использовать его для цветовые градиенты.

*clrProgressText*<br/>
[in] Цвет текста хода выполнения. `CMFCBaseVisualManager` игнорирует это. Цвет текста определяется `afxGlobalData.clrBtnText`.

*bProgressText*<br/>
[in] Указывает, следует ли отображать текст хода выполнения.

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если включен интерфейс API темы оформления. в противном случае — значение FALSE.

##  <a name="fillrebarpane"></a>  CMFCBaseVisualManager::FillReBarPane

Заполняет фона элемента управления "Главная панель", используя текущую тему Windows.

```
virtual void FillReBarPane(
    CDC* pDC,
    CBasePane* pBar,
    CRect rectClient);
```

### <a name="parameters"></a>Параметры

*основного контроллера домена*<br/>
[in] Указатель на контекст устройства.

*pBar*<br/>
[in] Указатель на область, фон которого должно отображаться.

*rectClient*<br/>
[in] Ограничивающий прямоугольник для заполнения области.

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если включен интерфейс API темы оформления. в противном случае — значение FALSE.

##  <a name="getstandardwindowstheme"></a>  CMFCBaseVisualManager::GetStandardWindowsTheme

Получает текущую тему Windows.

```
virtual WinXpTheme GetStandardWindowsTheme();
```

### <a name="return-value"></a>Возвращаемое значение

Выбранный цвет темы Windows. Может принимать одно из следующих значений:

- `WinXpTheme_None` -Нет, тема не включена.

- `WinXpTheme_NonStandard` -нестандартное темы выбран (то есть темы установлен, но ни один из списка ниже).

- `WinXpTheme_Blue` -"(голубой" теме (Luna).

- `WinXpTheme_Olive` -станет оливковым темы.

- `WinXpTheme_Silver` -серебристая тема.

##  <a name="updatesystemcolors"></a>  CMFCBaseVisualManager::UpdateSystemColors

Вызовы `OpenThemeData` для получения дескрипторов для рисования различных элементов управления: windows, панелей инструментов, кнопок и т. д.

```
void UpdateSystemColors();
```

### <a name="remarks"></a>Примечания

Только для внутреннего использования.

## <a name="see-also"></a>См. также

[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Классы](../../mfc/reference/mfc-classes.md)
