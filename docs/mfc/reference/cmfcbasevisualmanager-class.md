---
title: CmFCBaseВизуальныйменеджер Класс
ms.date: 11/04/2016
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
ms.openlocfilehash: ac64a3feac5d124c2bfa67fc857dad5045c2dd28
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2020
ms.locfileid: "81754891"
---
# <a name="cmfcbasevisualmanager-class"></a>CmFCBaseВизуальныйменеджер Класс

Слой между визуальными менеджерами и API темы Windows.

`CMFCBaseVisualManager`загружает UxTheme.dll, если он доступен, и управляет доступом к методам API Windows Theme.

Этот класс предназначен только для внутреннего использования.

## <a name="syntax"></a>Синтаксис

```
class CMFCBaseVisualManager: public CObject
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|||
|-|-|
|Имя|Описание|
|[CMFCBaseВизуальныйМенеджер::CMFCBaseВизуальныйМенеджер](#cmfcbasevisualmanager)|Создает и инициализирует объект `CMFCBaseVisualManager`.|
|`CMFCBaseVisualManager::~CMFCBaseVisualManager`|Деструктор.|

### <a name="public-methods"></a>Открытые методы

|||
|-|-|
|Имя|Описание|
|[CMFCBaseВизуальныйМенеджер::DrawCheckBox](#drawcheckbox)|Рисует управление флажком, используя текущую тему Windows.|
|[CMFCBaseVisualManager::DrawComboBorder](#drawcomboborder)|Рисует границу комбо-коробки с помощью текущей темы Windows.|
|[CMFCBaseVisualManager::DrawComboDropButton](#drawcombodropbutton)|Рисует кнопку выпадения комбо-окна с использованием текущей темы Windows.|
|[CMFCBaseВизуальныйМенеджер::DrawPushButton](#drawpushbutton)|Рисует кнопку с использованием текущей темы Windows.|
|[CMFCBaseВизуальныйМенеджер::DrawRadioButton](#drawradiobutton)|Рисует управление кнопкой радио, используя текущую тему Windows.|
|[CMFCBaseВизуальныйменеджер::DрауостамастБарПрогресс](#drawstatusbarprogress)|Рисует панель прогресса на элементе управления статусом [(класс CMFCStatusBar)](../../mfc/reference/cmfcstatusbar-class.md)с использованием текущей темы Windows.|
|[CMFCBaseВизуальныйМенеджер::FillReBarPane](#fillrebarpane)|Заполняет фон управления арматом с помощью текущей темы Windows.|
|[CMFCBaseVisualManager::GetStandardWindowsTheme](#getstandardwindowstheme)|Получает текущую тему Windows.|

### <a name="protected-methods"></a>Защищенные методы

|||
|-|-|
|Имя|Описание|
|[CMFCBaseВизуальныйМенеджер::ОчисткаТемы](#cleanupthemes)|Звонки `CloseThemeData` для всех ручек, полученных в `UpdateSystemColors`.|
|[CMFCBaseВизуальныйМенеджер::ОбновлениеСистемныеЦвета](#updatesystemcolors)|Призывы `OpenThemeData` к получению ручек для рисования различных элементов управления: окна, панели инструментов, кнопки и так далее.|

## <a name="remarks"></a>Remarks

Вам не нужно мгновенно объекты этого класса напрямую.

Поскольку это базовый класс для всех визуальных менеджеров, вы можете просто позвонить [CMFCVisualManager::GetInstance](../../mfc/reference/cmfcvisualmanager-class.md#getinstance), `CMFCBaseVisualManager` получить указатель на текущий визуальный менеджер, и получить доступ к методам использования этого указателя. Однако, если вам нужно отобразить элемент управления с помощью `CMFCVisualManagerWindows` текущей темы Windows, лучше использовать интерфейс.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CMFCBaseВизуальныйМенеджер](../../mfc/reference/cmfcbasevisualmanager-class.md)

## <a name="requirements"></a>Требования

**Заголовок:** afxvisualmanager.h

## <a name="cmfcbasevisualmanagercleanupthemes"></a><a name="cleanupthemes"></a>CMFCBaseВизуальныйМенеджер::ОчисткаТемы

Звонки `CloseThemeData` для всех ручек, полученных в `UpdateSystemColors`.

```cpp
void CleanUpThemes();
```

### <a name="remarks"></a>Remarks

Только для внутреннего использования.

## <a name="cmfcbasevisualmanagercmfcbasevisualmanager"></a><a name="cmfcbasevisualmanager"></a>CMFCBaseВизуальныйМенеджер::CMFCBaseВизуальныйМенеджер

Создает и инициализирует объект `CMFCBaseVisualManager`.

```
CMFCBaseVisualManager();
```

## <a name="cmfcbasevisualmanagerdrawcheckbox"></a><a name="drawcheckbox"></a>CMFCBaseВизуальныйМенеджер::DrawCheckBox

Рисует управление флажком, используя текущую тему Windows.

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

*pDC*<br/>
(в) Указатель на контекст устройства

*rect*<br/>
(в) Ограничивающий прямоугольник флажка.

*bНазалион*<br/>
(в) Определяет, выделен ли флажок.

*nState*<br/>
0 для бесконтрольного, 1 для проверенного нормального,

2 для смешанного нормального.

*bВСтои*<br/>
(в) Определяет, включен ли флажок.

*bPressed*<br/>
(в) Определяет, нажата ли флажок.

### <a name="return-value"></a>Возвращаемое значение

TRUE, если Тема API включен; в противном случае FALSE.

### <a name="remarks"></a>Remarks

Значения *nState* соответствуют следующим стилям флажок.

|nState|Проверить стиль коробки|
|------------|---------------------|
|0|CBS_UNCHECKEDNORMAL|
|1|CBS_CHECKEDNORMAL|
|2|CBS_MIXEDNORMAL|

## <a name="cmfcbasevisualmanagerdrawcomboborder"></a><a name="drawcomboborder"></a>CMFCBaseVisualManager::DrawComboBorder

Рисует границу комбо-коробки, используя текущую тему Windows.

```
virtual BOOL DrawComboBorder(
    CDC* pDC,
    CRect rect,
    BOOL bDisabled,
    BOOL bIsDropped,
    BOOL bIsHighlighted);
```

### <a name="parameters"></a>Параметры

*pDC*<br/>
(в) Указатель на контекст устройства.

*rect*<br/>
(в) Связанный прямоугольник границы комбо-коробки.

*bDisabled*<br/>
(в) Определяет, отключена ли граница комбо-бокса.

*bIsDropped*<br/>
(в) Определяет, сбрасываетли ли граница комбо-бокса.

*bIsHighlighted*<br/>
(в) Определяет, выделяется ли граница комбо-бокса.

### <a name="return-value"></a>Возвращаемое значение

TRUE, если Тема API включен; в противном случае FALSE.

## <a name="cmfcbasevisualmanagerdrawcombodropbutton"></a><a name="drawcombodropbutton"></a>CMFCBaseVisualManager::DrawComboDropButton

Рисует кнопку выпадения комбо-окна с использованием текущей темы Windows.

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
|*pDC*|(в) Указатель на контекст устройства.|
|*rect*|(в) Ограничивающий прямоугольник кнопки выпадения комбо-коробки.|
|*bDisabled*|(в) Определяет, отключена ли кнопка выпадения комбо-окна.|
|*bIsDropped*|(в) Определяет, является ли комбо окно выпадения кнопку упал.|
|*bIsHighlighted*|(в) Определяет, выделяется ли кнопка выпадения комбо-окна.|

### <a name="return-value"></a>Возвращаемое значение

TRUE, если Тема API включен; в противном случае FALSE.

## <a name="cmfcbasevisualmanagerdrawpushbutton"></a><a name="drawpushbutton"></a>CMFCBaseВизуальныйМенеджер::DrawPushButton

Рисует кнопку с использованием текущей темы Windows.

```
virtual BOOL DrawPushButton(
    CDC* pDC,
    CRect rect,
    CMFCButton* pButton,
    UINT uiState);
```

### <a name="parameters"></a>Параметры

*pDC*<br/>
(в) Указатель на контекст устройства.

*rect*<br/>
(в) Ограничивающий прямоугольник кнопки.

*pButton*<br/>
(в) Указатель на объект [класса CMFCButton](../../mfc/reference/cmfcbutton-class.md) для рисования.

*uiState*<br/>
(в) Игнорировать. Состояние взято из *pButton*.

### <a name="return-value"></a>Возвращаемое значение

TRUE, если Тема API включен; в противном случае FALSE.

## <a name="cmfcbasevisualmanagerdrawradiobutton"></a><a name="drawradiobutton"></a>CMFCBaseВизуальныйМенеджер::DrawRadioButton

Рисует управление кнопкой радио, используя текущую тему Windows.

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

*pDC*<br/>
(в) Указатель на контекст устройства.

*rect*<br/>
(в) Ограничивающий прямоугольник радиокнопки.

*bНазалион*<br/>
(в) Определяет, выделена ли кнопка радио.

*bChecked*<br/>
(в) Определяет, проверяется ли радиокнопка.

*bВСтои*<br/>
(в) Определяет, включена ли радиокнопка.

*bPressed*<br/>
(в) Определяет, нажата ли радиокнопка.

### <a name="return-value"></a>Возвращаемое значение

TRUE, если Тема API включен; в противном случае FALSE.

## <a name="cmfcbasevisualmanagerdrawstatusbarprogress"></a><a name="drawstatusbarprogress"></a>CMFCBaseВизуальныйменеджер::DрауостамастБарПрогресс

Рисует панель прогресса на элементе управления статусом [(класс CMFCStatusBar)](../../mfc/reference/cmfcstatusbar-class.md)с использованием текущей темы Windows.

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

*pDC*<br/>
(в) Указатель на контекст устройства.

*pStatusBar*<br/>
(в) Указатель на бар статуса. Это значение игнорируется.

*rectProgress*<br/>
(в) Ограничивающий прямоугольник панели прогресса в координатах *pDC.*

*nProgressTotal*<br/>
(в) Общее значение прогресса.

*nProgressCurr*<br/>
(в) Текущее значение прогресса.

*clrBar*<br/>
(в) Стартовый цвет. `CMFCBaseVisualManager`игнорирует это. Выведенные классы могут использовать его для градиентов цвета.

*clrProgressBarDest*<br/>
(в) Конечный цвет. `CMFCBaseVisualManager`игнорирует это. Выведенные классы могут использовать его для градиентов цвета.

*clrProgressText*<br/>
(в) Цвет текста прогресса. `CMFCBaseVisualManager`игнорирует это. Цвет текста определяется `afxGlobalData.clrBtnText`.

*bProgressText*<br/>
(в) Определяет, следует ли отображать текст прогресса.

### <a name="return-value"></a>Возвращаемое значение

TRUE, если Тема API включен; в противном случае FALSE.

## <a name="cmfcbasevisualmanagerfillrebarpane"></a><a name="fillrebarpane"></a>CMFCBaseВизуальныйМенеджер::FillReBarPane

Заполняет фон управления арматом с помощью текущей темы Windows.

```
virtual void FillReBarPane(
    CDC* pDC,
    CBasePane* pBar,
    CRect rectClient);
```

### <a name="parameters"></a>Параметры

*pDC*<br/>
(в) Указатель на контекст устройства.

*pBar*<br/>
(в) Указатель на панель, фон которой должен быть нарисован.

*rectClient*<br/>
(в) Ограничивающий прямоугольник области, которая должна быть заполнена.

### <a name="return-value"></a>Возвращаемое значение

TRUE, если Тема API включен; в противном случае FALSE.

## <a name="cmfcbasevisualmanagergetstandardwindowstheme"></a><a name="getstandardwindowstheme"></a>CMFCBaseVisualManager::GetStandardWindowsTheme

Получает текущую тему Windows.

```
virtual WinXpTheme GetStandardWindowsTheme();
```

### <a name="return-value"></a>Возвращаемое значение

В настоящее время выбран цвет темы Windows. Может быть одним из следующих перечисленных значений:

- `WinXpTheme_None`- нет включенной темы.

- `WinXpTheme_NonStandard`- выбрана нестандартная тема (имеется в виду тема выбрана, но ни одна из списка ниже).

- `WinXpTheme_Blue`- синяя тема (Луна).

- `WinXpTheme_Olive`- оливковая тема.

- `WinXpTheme_Silver`- серебряная тема.

## <a name="cmfcbasevisualmanagerupdatesystemcolors"></a><a name="updatesystemcolors"></a>CMFCBaseВизуальныйМенеджер::ОбновлениеСистемныеЦвета

Призывы `OpenThemeData` к получению ручек для рисования различных элементов управления: окна, панели инструментов, кнопки и так далее.

```cpp
void UpdateSystemColors();
```

### <a name="remarks"></a>Remarks

Только для внутреннего использования.

## <a name="see-also"></a>См. также раздел

[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Классы](../../mfc/reference/mfc-classes.md)
