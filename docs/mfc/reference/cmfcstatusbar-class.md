---
title: Класс CMFCStatusBar | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CMFCStatusBar
- AFXSTATUSBAR/CMFCStatusBar
- AFXSTATUSBAR/CMFCStatusBar::CalcFixedLayout
- AFXSTATUSBAR/CMFCStatusBar::CommandToIndex
- AFXSTATUSBAR/CMFCStatusBar::Create
- AFXSTATUSBAR/CMFCStatusBar::CreateEx
- AFXSTATUSBAR/CMFCStatusBar::DoesAllowDynInsertBefore
- AFXSTATUSBAR/CMFCStatusBar::EnablePaneDoubleClick
- AFXSTATUSBAR/CMFCStatusBar::EnablePaneProgressBar
- AFXSTATUSBAR/CMFCStatusBar::GetCount
- AFXSTATUSBAR/CMFCStatusBar::GetDrawExtendedArea
- AFXSTATUSBAR/CMFCStatusBar::GetExtendedArea
- AFXSTATUSBAR/CMFCStatusBar::GetItemID
- AFXSTATUSBAR/CMFCStatusBar::GetItemRect
- AFXSTATUSBAR/CMFCStatusBar::GetPaneInfo
- AFXSTATUSBAR/CMFCStatusBar::GetPaneProgress
- AFXSTATUSBAR/CMFCStatusBar::GetPaneStyle
- AFXSTATUSBAR/CMFCStatusBar::GetPaneText
- AFXSTATUSBAR/CMFCStatusBar::GetPaneWidth
- AFXSTATUSBAR/CMFCStatusBar::GetTipText
- AFXSTATUSBAR/CMFCStatusBar::InvalidatePaneContent
- AFXSTATUSBAR/CMFCStatusBar::PreCreateWindow
- AFXSTATUSBAR/CMFCStatusBar::SetDrawExtendedArea
- AFXSTATUSBAR/CMFCStatusBar::SetIndicators
- AFXSTATUSBAR/CMFCStatusBar::SetPaneAnimation
- AFXSTATUSBAR/CMFCStatusBar::SetPaneBackgroundColor
- AFXSTATUSBAR/CMFCStatusBar::SetPaneIcon
- AFXSTATUSBAR/CMFCStatusBar::SetPaneInfo
- AFXSTATUSBAR/CMFCStatusBar::SetPaneProgress
- AFXSTATUSBAR/CMFCStatusBar::SetPaneStyle
- AFXSTATUSBAR/CMFCStatusBar::SetPaneText
- AFXSTATUSBAR/CMFCStatusBar::SetPaneTextColor
- AFXSTATUSBAR/CMFCStatusBar::SetPaneWidth
- AFXSTATUSBAR/CMFCStatusBar::SetTipText
- AFXSTATUSBAR/CMFCStatusBar::OnDrawPane
dev_langs:
- C++
helpviewer_keywords:
- CMFCStatusBar [MFC], CalcFixedLayout
- CMFCStatusBar [MFC], CommandToIndex
- CMFCStatusBar [MFC], Create
- CMFCStatusBar [MFC], CreateEx
- CMFCStatusBar [MFC], DoesAllowDynInsertBefore
- CMFCStatusBar [MFC], EnablePaneDoubleClick
- CMFCStatusBar [MFC], EnablePaneProgressBar
- CMFCStatusBar [MFC], GetCount
- CMFCStatusBar [MFC], GetDrawExtendedArea
- CMFCStatusBar [MFC], GetExtendedArea
- CMFCStatusBar [MFC], GetItemID
- CMFCStatusBar [MFC], GetItemRect
- CMFCStatusBar [MFC], GetPaneInfo
- CMFCStatusBar [MFC], GetPaneProgress
- CMFCStatusBar [MFC], GetPaneStyle
- CMFCStatusBar [MFC], GetPaneText
- CMFCStatusBar [MFC], GetPaneWidth
- CMFCStatusBar [MFC], GetTipText
- CMFCStatusBar [MFC], InvalidatePaneContent
- CMFCStatusBar [MFC], PreCreateWindow
- CMFCStatusBar [MFC], SetDrawExtendedArea
- CMFCStatusBar [MFC], SetIndicators
- CMFCStatusBar [MFC], SetPaneAnimation
- CMFCStatusBar [MFC], SetPaneBackgroundColor
- CMFCStatusBar [MFC], SetPaneIcon
- CMFCStatusBar [MFC], SetPaneInfo
- CMFCStatusBar [MFC], SetPaneProgress
- CMFCStatusBar [MFC], SetPaneStyle
- CMFCStatusBar [MFC], SetPaneText
- CMFCStatusBar [MFC], SetPaneTextColor
- CMFCStatusBar [MFC], SetPaneWidth
- CMFCStatusBar [MFC], SetTipText
- CMFCStatusBar [MFC], OnDrawPane
ms.assetid: f2960d1d-f4ed-41e8-bd99-0382b2f8d88e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: b3ba50c607d7522441420686340c1f1ff32a7ccc
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/25/2018
ms.locfileid: "50081554"
---
# <a name="cmfcstatusbar-class"></a>Класс CMFCStatusBar

`CMFCStatusBar` Класс реализует строку состояния, аналогичную `CStatusBar` класса. Однако класс `CMFCStatusBar` не содержит функции, предоставляемые классом `CStatusBar` , такие как возможность отображать изображения, анимации и индикаторы выполнения, а также возможность реагировать на двойные нажатия мыши.

Для получения дополнительных сведений см. в разделе исходном коде, расположенном в **VC\\atlmfc\\src\\mfc** папке установки Visual Studio.

## <a name="syntax"></a>Синтаксис

```
class CMFCStatusBar : public CPane
```

## <a name="members"></a>Участники

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CMFCStatusBar::CalcFixedLayout](#calcfixedlayout)|(Переопределяет [CBasePane::CalcFixedLayout](../../mfc/reference/cbasepane-class.md#calcfixedlayout).)|
|[CMFCStatusBar::CommandToIndex](#commandtoindex)||
|[CMFCStatusBar::Create](#create)|Создает панель элементов управления и прикрепляет его к [CPane](../../mfc/reference/cpane-class.md) объекта. (Переопределяет [CPane::Create](../../mfc/reference/cpane-class.md#create).)|
|[CMFCStatusBar::CreateEx](#createex)|Создает панель элементов управления и прикрепляет его к [CPane](../../mfc/reference/cpane-class.md) объекта. (Переопределяет [CPane::CreateEx](../../mfc/reference/cpane-class.md#createex).)|
|[CMFCStatusBar::DoesAllowDynInsertBefore](#doesallowdyninsertbefore)|Определяет, могут ли другой области динамически вставлены между этой областью и родительского фрейма. (Переопределяет [CBasePane::DoesAllowDynInsertBefore](../../mfc/reference/cbasepane-class.md#doesallowdyninsertbefore).)|
|[CMFCStatusBar::EnablePaneDoubleClick](#enablepanedoubleclick)|Включает или отключает обработку мыши производит двойной щелчок на строке состояния.|
|[CMFCStatusBar::EnablePaneProgressBar](#enablepaneprogressbar)|Отображает индикатор выполнения в указанной области.|
|[CMFCStatusBar::GetCount](#getcount)|Возвращает число панелей строки состояния.|
|[CMFCStatusBar::GetDrawExtendedArea](#getdrawextendedarea)||
|[CMFCStatusBar::GetExtendedArea](#getextendedarea)||
|[CMFCStatusBar::GetItemID](#getitemid)||
|[CMFCStatusBar::GetItemRect](#getitemrect)||
|[CMFCStatusBar::GetPaneInfo](#getpaneinfo)||
|[CMFCStatusBar::GetPaneProgress](#getpaneprogress)||
|[CMFCStatusBar::GetPaneStyle](#getpanestyle)|Возвращает стиль панели. (Переопределяет [CBasePane::GetPaneStyle](../../mfc/reference/cbasepane-class.md#getpanestyle).)|
|[CMFCStatusBar::GetPaneText](#getpanetext)||
|[CMFCStatusBar::GetPaneWidth](#getpanewidth)|Возвращает ширину в пикселях области, указанной в строке состояния.|
|[CMFCStatusBar::GetTipText](#gettiptext)|Возвращает текст подсказки для области, указанной в строке состояния.|
|[CMFCStatusBar::InvalidatePaneContent](#invalidatepanecontent)|Делает недействительной указанную область и перерисовывает его содержимого.|
|[CMFCStatusBar::PreCreateWindow](#precreatewindow)|Вызвано структурой перед созданием окна Windows, прикрепленный к этому `CWnd` объекта. (Переопределяет [CWnd::PreCreateWindow](../../mfc/reference/cwnd-class.md#precreatewindow).)|
|[CMFCStatusBar::SetDrawExtendedArea](#setdrawextendedarea)||
|[CMFCStatusBar::SetIndicators](#setindicators)||
|[CMFCStatusBar::SetPaneAnimation](#setpaneanimation)|Присваивает указанную область анимации.|
|[CMFCStatusBar::SetPaneBackgroundColor](#setpanebackgroundcolor)|Задает цвет фона для области, указанной в строке состояния.|
|[CMFCStatusBar::SetPaneIcon](#setpaneicon)|Задает значок для области, указанной в строке состояния.|
|[CMFCStatusBar::SetPaneInfo](#setpaneinfo)||
|[CMFCStatusBar::SetPaneProgress](#setpaneprogress)|Задает текущее положение индикатора хода выполнения для области, указанной в строке состояния.|
|[CMFCStatusBar::SetPaneStyle](#setpanestyle)|Задает стиль области. (Переопределяет [CBasePane::SetPaneStyle](../../mfc/reference/cbasepane-class.md#setpanestyle).)|
|[CMFCStatusBar::SetPaneText](#setpanetext)||
|[CMFCStatusBar::SetPaneTextColor](#setpanetextcolor)|Задает цвет текста для области, указанной в строке состояния.|
|[CMFCStatusBar::SetPaneWidth](#setpanewidth)|Задает ширину в пикселях области, указанной в строке состояния.|
|[CMFCStatusBar::SetTipText](#settiptext)|Задает текст подсказки для области, указанной в строке состояния.|

### <a name="protected-methods"></a>Защищенные методы

|Имя|Описание|
|----------|-----------------|
|[CMFCStatusBar::OnDrawPane](#ondrawpane)|Вызывается платформой, когда он перерисовывает панели строки состояния.|

## <a name="remarks"></a>Примечания

На следующей схеме показаны рис строки состояния из [состояние панели демонстрационного](../../visual-cpp-samples.md) приложения.

![Пример cmfcstatusbar](../../mfc/reference/media/cmfcstatusbar.png "cmfcstatusbar")

## <a name="example"></a>Пример

В следующем примере демонстрируется локальные переменные, которые приложение использует для вызова методов в `CMFCStatusBar` класса. Эти переменные объявляются в StatusBarDemoView.h. Главного фрейма объявляется в MainFrm.h документа объявляется в StatusBarDemoDoc.h и представление объявляется в StatusBarDemoView.h. Этот фрагмент кода является частью [состояние панели демонстрационного](../../visual-cpp-samples.md).

[!code-cpp[NVC_MFC_StatusBarDemo#9](../../mfc/reference/codesnippet/cpp/cmfcstatusbar-class_1.h)]

## <a name="example"></a>Пример

В следующем примере показано, как получить ссылку на `CMFCStatusBar` объекта путем введения `GetStatusBar` метод в MainFrm.h и последующего вызова данного метода из `GetStatusBar` метод в StatusBarDemoView.h. Этот фрагмент кода является частью [состояние панели демонстрационного](../../visual-cpp-samples.md).

[!code-cpp[NVC_MFC_StatusBarDemo#7](../../mfc/reference/codesnippet/cpp/cmfcstatusbar-class_2.h)]
[!code-cpp[NVC_MFC_StatusBarDemo#8](../../mfc/reference/codesnippet/cpp/cmfcstatusbar-class_3.h)]

## <a name="example"></a>Пример

Следующий пример демонстрирует вызов методов `CMFCStatusBar` класс в StatusBarDemoView.cpp. Константы, объявляются в MainFrm.h. Пример показано, как задать значок, текст подсказки для панели строки состояния, отображать индикатор хода выполнения в указанной области, назначить анимации в указанную область, задать текст и ширину панели строки состояния и текущий индикатор хода выполнения из progr полоса ESS для панели строки состояния. Этот фрагмент кода является частью [состояние панели демонстрационного](../../visual-cpp-samples.md).

[!code-cpp[NVC_MFC_StatusBarDemo#6](../../mfc/reference/codesnippet/cpp/cmfcstatusbar-class_4.h)]
[!code-cpp[NVC_MFC_StatusBarDemo#1](../../mfc/reference/codesnippet/cpp/cmfcstatusbar-class_5.cpp)]
[!code-cpp[NVC_MFC_StatusBarDemo#2](../../mfc/reference/codesnippet/cpp/cmfcstatusbar-class_6.cpp)]
[!code-cpp[NVC_MFC_StatusBarDemo#3](../../mfc/reference/codesnippet/cpp/cmfcstatusbar-class_7.cpp)]
[!code-cpp[NVC_MFC_StatusBarDemo#4](../../mfc/reference/codesnippet/cpp/cmfcstatusbar-class_8.cpp)]
[!code-cpp[NVC_MFC_StatusBarDemo#5](../../mfc/reference/codesnippet/cpp/cmfcstatusbar-class_9.cpp)]

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CBasePane](../../mfc/reference/cbasepane-class.md)

[CPane](../../mfc/reference/cpane-class.md)

[CMFCStatusBar](../../mfc/reference/cmfcstatusbar-class.md)

## <a name="requirements"></a>Требования

**Заголовок:** afxstatusbar.h

##  <a name="calcfixedlayout"></a>  CMFCStatusBar::CalcFixedLayout

```
virtual CSize CalcFixedLayout(
    BOOL bStretch,
    BOOL bHorz);
```

### <a name="parameters"></a>Параметры

[in] *bStretch*<br/>
[in] *bHorz*<br/>

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Примечания

##  <a name="commandtoindex"></a>  CMFCStatusBar::CommandToIndex

```
int CommandToIndex(UINT nIDFind) const;
```

### <a name="parameters"></a>Параметры

[in] *nIDFind*<br/>

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Примечания

##  <a name="create"></a>  CMFCStatusBar::Create

```
BOOL Create(
    CWnd* pParentWnd,
    DWORD dwStyle = WS_CHILD | WS_VISIBLE | CBRS_BOTTOM,
    UINT nID = AFX_IDW_STATUS_BAR);
```

### <a name="parameters"></a>Параметры

[in] *pParentWnd*<br/>
[in] *dwStyle*<br/>
[in] *nID*<br/>

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Примечания

##  <a name="createex"></a>  CMFCStatusBar::CreateEx

```
BOOL CreateEx(
    CWnd* pParentWnd,
    DWORD dwCtrlStyle = 0,
    DWORD dwStyle = WS_CHILD | WS_VISIBLE | CBRS_BOTTOM,
    UINT nID = AFX_IDW_STATUS_BAR);
```

### <a name="parameters"></a>Параметры

[in] *pParentWnd*<br/>
[in] *dwCtrlStyle*<br/>
[in] *dwStyle*<br/>
[in] *nID*<br/>

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Примечания

##  <a name="doesallowdyninsertbefore"></a>  CMFCStatusBar::DoesAllowDynInsertBefore

```
virtual BOOL DoesAllowDynInsertBefore() const;
```

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Примечания

##  <a name="enablepanedoubleclick"></a>  CMFCStatusBar::EnablePaneDoubleClick

Включает или отключает обработку мыши производит двойной щелчок на строке состояния.

```
void EnablePaneDoubleClick(BOOL bEnable=TRUE);
```

### <a name="parameters"></a>Параметры

*bEnable*<br/>
[in] Значение TRUE, если включите обработку двойной щелчок мышью. В противном случае отключите обработку двойной щелчок мышью.

### <a name="remarks"></a>Примечания

Если в строке состояния включена для обработки двойных щелчков, Windows отправляет уведомление WM_COMMAND вместе с Идентификатором ресурса владельцу строки каждый раз, что пользователь дважды щелкает панель строки состояния состояния.

##  <a name="enablepaneprogressbar"></a>  CMFCStatusBar::EnablePaneProgressBar

Отображать индикатор хода выполнения в указанной области.

```
void EnablePaneProgressBar(
    int nIndex,
    long nTotal=100,
    BOOL bDisplayText=FALSE,
    COLORREF clrBar=-1,
    COLORREF clrBarDest=-1,
    COLORREF clrProgressText=-1);
```

### <a name="parameters"></a>Параметры

*nIndex*<br/>
[in] Указывает, индикатор хода выполнения, чтобы включить индекс области.

*nTotal*<br/>
[in] Указывает максимальное значение для индикатора выполнения.

*bDisplayText*<br/>
[in] Отображение индикатора текущего значения хода выполнения.

*clrBar*<br/>
[in] Задает цвет фона индикатора хода выполнения.

*clrBarDest*<br/>
[in] Задает вторичный цвет фона панели хода выполнения. Использовать другое значение, чем *clrBar* для заливки цветом смешением в градиенте.

*clrProgressText*<br/>
[in] Задает цвет текста индикатора хода выполнения.

### <a name="remarks"></a>Примечания

Если вы хотите отключить вызов панель хода выполнения `EnablePaneProgressBar` с *nTotal* задано значение -1. По умолчанию *nTotal* становится равным 100. Таким образом вы не обязательно любые дополнительные вычисления для отображения хода выполнения в процентах.

Следует передавать разные значения *clrBar* и *clrBarDest* таким образом, чтобы цвет фона индикатора хода выполнения отображает цвет в градиенте смешением. .

Чтобы задать текущее положение, вызовите [CMFCStatusBar::SetPaneProgress](#setpaneprogress) метод.

##  <a name="getcount"></a>  CMFCStatusBar::GetCount

Извлекает число панелей в строке состояния.

```
int GetCount() const;
```

### <a name="return-value"></a>Возвращаемое значение

Число панелей в строке состояния.

##  <a name="getdrawextendedarea"></a>  CMFCStatusBar::GetDrawExtendedArea

```
BOOL GetDrawExtendedArea() const;
```

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Примечания

##  <a name="getextendedarea"></a>  CMFCStatusBar::GetExtendedArea

```
virtual BOOL GetExtendedArea(CRect& rect) const;
```

### <a name="parameters"></a>Параметры

[in] *rect*<br/>

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Примечания

##  <a name="getitemid"></a>  CMFCStatusBar::GetItemID

```
UINT GetItemID(int nIndex) const;
```

### <a name="parameters"></a>Параметры

[in] *nIndex*<br/>

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Примечания

##  <a name="getitemrect"></a>  CMFCStatusBar::GetItemRect

```
void GetItemRect(
    int nIndex,
    LPRECT lpRect) const;
```

### <a name="parameters"></a>Параметры

[in] *nIndex*<br/>
[in] *lpRect*<br/>

### <a name="remarks"></a>Примечания

##  <a name="getpaneinfo"></a>  CMFCStatusBar::GetPaneInfo

```
void GetPaneInfo(
    int nIndex,
    UINT& nID,
    UINT& nStyle,
    int& cxWidth) const;
```

### <a name="parameters"></a>Параметры

[in] *nIndex*<br/>
[in] *nID*<br/>
[in] *nStyle*<br/>
[in] *cxWidth*<br/>

### <a name="remarks"></a>Примечания

##  <a name="getpaneprogress"></a>  CMFCStatusBar::GetPaneProgress

```
long GetPaneProgress(int nIndex) const;
```

### <a name="parameters"></a>Параметры

[in] *nIndex*<br/>

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Примечания

##  <a name="getpanestyle"></a>  CMFCStatusBar::GetPaneStyle

```
UINT GetPaneStyle(int nIndex) const;
```

### <a name="parameters"></a>Параметры

[in] *nIndex*<br/>

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Примечания

##  <a name="getpanetext"></a>  CMFCStatusBar::GetPaneText

```
void GetPaneText(
    int nIndex,
    CString& s) const;

CString GetPaneText(int nIndex) const;
```

### <a name="parameters"></a>Параметры

[in] *nIndex*<br/>
[in] *s*<br/>

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Примечания

##  <a name="getpanewidth"></a>  CMFCStatusBar::GetPaneWidth

Получает ширину панели строки состояния.

```
int GetPaneWidth(int nIndex) const;
```

### <a name="parameters"></a>Параметры

*nIndex*<br/>
[in] Указывает индекс панели строки состояния.

### <a name="return-value"></a>Возвращаемое значение

Ширина панели строки состояния, *nIndex* указывает; в противном случае — нуль, если панели строки состояния не существует.

##  <a name="gettiptext"></a>  CMFCStatusBar::GetTipText

Получить текст подсказки для панели строки состояния.

```
CString GetTipText(int nIndex) const;
```

### <a name="parameters"></a>Параметры

*nIndex*<br/>
[in] Указывает индекс области, для которого необходимо получить текст подсказки.

### <a name="return-value"></a>Возвращаемое значение

Текст подсказки для панели строки состояния, *nIndex* указывает. В противном случае — пустая строка, если панель строки состояния не существует для указанного *nIndex* или если его текст подсказки является пустым.

##  <a name="invalidatepanecontent"></a>  CMFCStatusBar::InvalidatePaneContent

Сделать недействительным панель строки состояния и перерисовывает его содержимого.

```
void InvalidatePaneContent(int nIndex);
```

### <a name="parameters"></a>Параметры

*nIndex*<br/>
[in] Указывает индекс области, содержимое которого является недействительным и перерисовать.

### <a name="remarks"></a>Примечания

Когда строка состояния становится недействительным, оно отмечено для перерисовки. Windows перерисовывает его при `UpdateWindow` метод отправляет сообщение WM_PAINT `OnPaint` метод.

##  <a name="ondrawpane"></a>  CMFCStatusBar::OnDrawPane

Преобразование панели строки состояния.

```
virtual void OnDrawPane(
    CDC* pDC,
    CMFCStatusBarPaneInfo* pPane);
```

### <a name="parameters"></a>Параметры

*pDC*<br/>
[in] Указатель на контекст устройства для рисования.

*pPane*<br/>
[in] Указатель на `CMFCStatusBarPaneInfo` структуру, содержащую сведения об области перерисовку.

### <a name="remarks"></a>Примечания

По умолчанию `OnDrawPane` перерисовывает области, используя контекст устройства *pDC* в соответствии с стиля и содержимого панели.

Переопределите этот метод в `CMFCStatusBar`-производного класса, чтобы настроить внешний вид области.

##  <a name="precreatewindow"></a>  CMFCStatusBar::PreCreateWindow

```
virtual BOOL PreCreateWindow(CREATESTRUCT& cs);
```

### <a name="parameters"></a>Параметры

[in] *cs*<br/>

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Примечания

##  <a name="setdrawextendedarea"></a>  CMFCStatusBar::SetDrawExtendedArea

```
void SetDrawExtendedArea(BOOL bSet = TRUE);
```

### <a name="parameters"></a>Параметры

[in] *bSet*<br/>

### <a name="remarks"></a>Примечания

##  <a name="setindicators"></a>  CMFCStatusBar::SetIndicators

```
BOOL SetIndicators(
    const UINT* lpIDArray,
    int nIDCount);
```

### <a name="parameters"></a>Параметры

[in] *lpIDArray*<br/>
[in] *nIDCount*<br/>

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Примечания

##  <a name="setpaneanimation"></a>  CMFCStatusBar::SetPaneAnimation

Присваивает указанную область анимации.

```
void SetPaneAnimation(
    int nIndex,
    HIMAGELIST hImageList,
    UINT nFrameRate=500,
    BOOL bUpdate=TRUE);
```

### <a name="parameters"></a>Параметры

*nIndex*<br/>
[in] Указывает индекс панели, к которому вы хотите назначить для него анимации.

*hImageList*<br/>
[in] Указывает дескриптор для списка изображений, содержащий кадров анимации.

*nFrameRate*<br/>
[in] Указывает частоту кадров, в миллисекундах, для анимации.

*bСтратегии обновлениями*<br/>
[in] Если значение равно TRUE, немедленно обновите содержимое области. В противном случае содержимое панели обновляется при он станет недействительным.

### <a name="remarks"></a>Примечания

Если вы хотите отключить текущей анимации, вызвать `SetPaneAnimation` с `hImageList` присваивается значение NULL.

##  <a name="setpanebackgroundcolor"></a>  CMFCStatusBar::SetPaneBackgroundColor

Задает цвет фона панели строки состояния.

```
void SetPaneBackgroundColor(
    int nIndex,
    COLORREF clrBackground=(COLORREF)-1,
    BOOL bUpdate=TRUE);
```

### <a name="parameters"></a>Параметры

*nIndex*<br/>
[in] Указывает индекс области, для которого требуется задать новый цвет фона.

*clrBackground*<br/>
[in] Указывает новый цвет фона.

*bСтратегии обновлениями*<br/>
[in] Если значение равно TRUE, немедленно обновите содержимое области. В противном случае не обновить содержимое области, пока не становится недействительным области с помощью другого метода.

##  <a name="setpaneicon"></a>  CMFCStatusBar::SetPaneIcon

Задайте значок панели строки состояния.

```
void SetPaneIcon(
    int nIndex,
    HICON hIcon,
    BOOL bUpdate=TRUE);

void SetPaneIcon(
    int nIndex,
    HBITMAP hBmp,
    COLORREF clrTransparent=RGB(255, 0, 255),
    BOOL bUpdate=TRUE);
```

### <a name="parameters"></a>Параметры

*nIndex*<br/>
[in] Указывает индекс области, для которого требуется задать изображение.

*hIcon*<br/>
[in] Указывает дескриптор для значка должен быть установлен как изображение панели.

*bСтратегии обновлениями*<br/>
[in] Указывает, следует ли обновить содержимое области немедленно.

*hBmp*<br/>
[in] Указывает дескриптор к растровому изображению в качестве области изображения.

*clrTransparent*<br/>
[in] Указывает прозрачный цвет точечного рисунка, *hBmp* указывает.

### <a name="remarks"></a>Примечания

Вы можете передать HICON или HBITMAP вместе с прозрачный цвет для задания области изображения. Если вы не хотите отображать изображение более, передайте значение NULL в качестве маркера изображения.

При возникновении любой запущенная анимация, [CMFCStatusBar::SetPaneAnimation](#setpaneanimation) имеет значение, анимация останавливается.

##  <a name="setpaneinfo"></a>  CMFCStatusBar::SetPaneInfo

```
void SetPaneInfo(
    int nIndex,
    UINT nID,
    UINT nStyle,
    int cxWidth);
```

### <a name="parameters"></a>Параметры

[in] *nIndex*<br/>
[in] *nID*<br/>
[in] *nStyle*<br/>
[in] *cxWidth*<br/>

### <a name="remarks"></a>Примечания

##  <a name="setpaneprogress"></a>  CMFCStatusBar::SetPaneProgress

Задайте текущий индикатор хода выполнения индикатора хода выполнения для указанной области.

```
void SetPaneProgress(
    int nIndex,
    long nCurr,
    BOOL bUpdate=TRUE);
```

### <a name="parameters"></a>Параметры

*nIndex*<br/>
[in] Указывает индекс области, для которого требуется обновить индикатор хода выполнения.

*nCurr*<br/>
[in] Указывает текущее значение индикатора хода выполнения.

*bСтратегии обновлениями*<br/>
[in] Указывает, следует ли немедленно обновлять области.

### <a name="remarks"></a>Примечания

Этот метод вызывается в том случае, если вы хотите обновить индикатор выполнения для индикатора в указанной области.

Чтобы использовать эту функцию для данной области, необходимо вызвать [CMFCStatusBar::EnablePaneProgressBar](#enablepaneprogressbar) первого.

##  <a name="setpanestyle"></a>  CMFCStatusBar::SetPaneStyle

```
void SetPaneStyle(
    int nIndex,
    UINT nStyle);
```

### <a name="parameters"></a>Параметры

[in] *nIndex*<br/>
[in] *nStyle*<br/>

### <a name="remarks"></a>Примечания

##  <a name="setpanetext"></a>  CMFCStatusBar::SetPaneText

```
virtual BOOL SetPaneText(
    int nIndex,
    LPCTSTR lpszNewText,
    BOOL bUpdate = TRUE);
```

### <a name="parameters"></a>Параметры

[in] *nIndex*<br/>
[in] *lpszNewText*<br/>
[in] *bСтратегии обновлениями*<br/>

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Примечания

##  <a name="setpanetextcolor"></a>  CMFCStatusBar::SetPaneTextColor

Задает цвет текста указанной области.

```
void SetPaneTextColor(
    int nIndex,
    COLORREF clrText=(COLORREF)-1,
    BOOL bUpdate=TRUE);
```

### <a name="parameters"></a>Параметры

*nIndex*<br/>
[in] Указывает индекс панели, к которому вы хотите назначить новый цвет текста.

*clrText*<br/>
[in] Задает цвет текста.

*bСтратегии обновлениями*<br/>
[in] Если значение равно TRUE, немедленно обновите содержимое области. В противном случае не обновить содержимое области, пока не становится недействительным области с помощью другого метода.

##  <a name="setpanewidth"></a>  CMFCStatusBar::SetPaneWidth

Задайте ширину панели строки состояния.

```
void SetPaneWidth(
    int nIndex,
    int cx);
```

### <a name="parameters"></a>Параметры

*nIndex*<br/>
[in] Индекс панели строки состояния, для которого требуется задать новую ширину.

*CX*<br/>
[in] Новая ширина панели строки состояния, в пикселях.

##  <a name="settiptext"></a>  CMFCStatusBar::SetTipText

Задает текст всплывающей подсказки в панель строки состояния.

```
void SetTipText(
    int nIndex,
    LPCTSTR pszTipText);
```

### <a name="parameters"></a>Параметры

*nIndex*<br/>
[in] Индекс панели, к которому вы хотите назначить текст всплывающей подсказки.

*pszTipText*<br/>
[in] Новый текст всплывающей подсказки.

## <a name="see-also"></a>См. также

[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Классы](../../mfc/reference/mfc-classes.md)<br/>
[Класс CPane](../../mfc/reference/cpane-class.md)<br/>
[Класс CStatusBar](../../mfc/reference/cstatusbar-class.md)
