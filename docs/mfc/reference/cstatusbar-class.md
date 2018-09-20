---
title: Класс CStatusBar | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CStatusBar
- AFXEXT/CStatusBar
- AFXEXT/CStatusBar::CStatusBar
- AFXEXT/CStatusBar::CommandToIndex
- AFXEXT/CStatusBar::Create
- AFXEXT/CStatusBar::CreateEx
- AFXEXT/CStatusBar::DrawItem
- AFXEXT/CStatusBar::GetItemID
- AFXEXT/CStatusBar::GetItemRect
- AFXEXT/CStatusBar::GetPaneInfo
- AFXEXT/CStatusBar::GetPaneStyle
- AFXEXT/CStatusBar::GetPaneText
- AFXEXT/CStatusBar::GetStatusBarCtrl
- AFXEXT/CStatusBar::SetIndicators
- AFXEXT/CStatusBar::SetPaneInfo
- AFXEXT/CStatusBar::SetPaneStyle
- AFXEXT/CStatusBar::SetPaneText
dev_langs:
- C++
helpviewer_keywords:
- CStatusBar [MFC], CStatusBar
- CStatusBar [MFC], CommandToIndex
- CStatusBar [MFC], Create
- CStatusBar [MFC], CreateEx
- CStatusBar [MFC], DrawItem
- CStatusBar [MFC], GetItemID
- CStatusBar [MFC], GetItemRect
- CStatusBar [MFC], GetPaneInfo
- CStatusBar [MFC], GetPaneStyle
- CStatusBar [MFC], GetPaneText
- CStatusBar [MFC], GetStatusBarCtrl
- CStatusBar [MFC], SetIndicators
- CStatusBar [MFC], SetPaneInfo
- CStatusBar [MFC], SetPaneStyle
- CStatusBar [MFC], SetPaneText
ms.assetid: a3bde3db-e71c-4881-a3ca-1d5481c345ba
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 9026f7bee9d765eedc0e6a28c9d247af75db3689
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46442036"
---
# <a name="cstatusbar-class"></a>Класс CStatusBar

Панель элементов управления со строкой областей текстового вывода или "индикаторов".

## <a name="syntax"></a>Синтаксис

```
class CStatusBar : public CControlBar
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CStatusBar::CStatusBar](#cstatusbar)|Создает объект `CStatusBar`.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CStatusBar::CommandToIndex](#commandtoindex)|Получает индекс для идентификатора данного индикатора.|
|[CStatusBar::Create](#create)|Создает строку состояния, присоединяется к `CStatusBar` , а также задает исходную высоту шрифта и строке.|
|[CStatusBar::CreateEx](#createex)|Создает `CStatusBar` объект с дополнительные стили для встроенного `CStatusBarCtrl` объекта.|
|[CStatusBar::DrawItem](#drawitem)|Вызывается при изменении внешнего вида панели управления рисуемого владельцем состояние изменится.|
|[CStatusBar::GetItemID](#getitemid)|Получает идентификатор индикатора для указанного индекса.|
|[CStatusBar::GetItemRect](#getitemrect)|Получает отобразить прямоугольник для заданного индекса.|
|[CStatusBar::GetPaneInfo](#getpaneinfo)|Получает идентификатор индикатора, стиля и ширины для указанного индекса.|
|[CStatusBar::GetPaneStyle](#getpanestyle)|Получает стиль индикатора для указанного индекса.|
|[CStatusBar::GetPaneText](#getpanetext)|Получает текст индикатора для указанного индекса.|
|[CStatusBar::GetStatusBarCtrl](#getstatusbarctrl)|Обеспечивает прямой доступ к базовой общего элемента управления.|
|[CStatusBar::SetIndicators](#setindicators)|Задает идентификаторы индикатора.|
|[CStatusBar::SetPaneInfo](#setpaneinfo)|Задает идентификатор индикатора, стиля и ширины для указанного индекса.|
|[CStatusBar::SetPaneStyle](#setpanestyle)|Задает стиль индикатора для указанного индекса.|
|[CStatusBar::SetPaneText](#setpanetext)|Задает текст индикатора для указанного индекса.|

## <a name="remarks"></a>Примечания

Области Вывод часто используются в качестве строки сообщения и в качестве индикаторов состояния. Примеры включают справочное сообщение строки меню, которые содержит краткое описание команды меню и индикаторов, показывающих состояние SCROLL LOCK, NUM LOCK и другие ключи.

[CStatusBar::GetStatusBarCtrl](#getstatusbarctrl), функция-член новые MFC 4.0, позволяет воспользоваться преимуществами поддержки Windows распространенных элемента управления для настройки и дополнительную функциональность в строке состояния. `CStatusBar` функции-члены обеспечивают большинство функций Windows стандартных элементов управления; Тем не менее, при вызове `GetStatusBarCtrl`, можно предоставить в строках состояния даже несколько характеристик Windows 95/98 строки состояния. При вызове `GetStatusBarCtrl`, он возвращает ссылку на `CStatusBarCtrl` объекта. См. в разделе [CStatusBarCtrl](../../mfc/reference/cstatusbarctrl-class.md) Дополнительные сведения о разработке с помощью стандартных элементов управления Windows. Более общие сведения о стандартных элементах управления см. в разделе [стандартные элементы управления](/windows/desktop/Controls/common-controls-intro) в пакете Windows SDK.

Framework хранит сведения индикатора в массив, содержащий крайний левый индикатора в позиции 0. При создании строки состояния, можно использовать массив идентификаторы, которые платформа связывает с соответствующей индикаторы строки. Строковый идентификатор или индекс затем можно использовать для доступа к индикатора.

По умолчанию основного индикатора «эластичный»: занимает около длина строки состояния, не используется в других областях индикатор, таким образом, чтобы другие панели по правому краю.

Чтобы создать строку состояния, выполните следующие действия.

1. Создать `CStatusBar` объекта.

1. Вызовите [создать](#create) (или [CreateEx](#createex)) функция для создания строки состояния окна и присоединить его к `CStatusBar` объекта.

1. Вызовите [SetIndicators](#setindicators) должен быть сопоставлен строковый идентификатор каждого индикатора.

Существует три способа обновления текста в панели строки состояния:

1. Вызовите [CWnd::SetWindowText](../../mfc/reference/cwnd-class.md#setwindowtext) обновление текста в области только для 0.

1. Вызовите [CCmdUI::SetText](../../mfc/reference/ccmdui-class.md#settext) в строке состояния ON_UPDATE_COMMAND_UI обработчика.

1. Вызовите [SetPaneText](#setpanetext) обновление текста для любой панели.

Вызовите [SetPaneStyle](#setpanestyle) Обновить стиль панели строки состояния.

Дополнительные сведения об использовании `CStatusBar`, см. в статье [реализация строки состояния в MFC](../../mfc/status-bar-implementation-in-mfc.md) и [Технические примечания 31: панелей элементов управления](../../mfc/tn031-control-bars.md).

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CControlBar](../../mfc/reference/ccontrolbar-class.md)

`CStatusBar`

## <a name="requirements"></a>Требования

**Заголовок:** afxext.h

##  <a name="commandtoindex"></a>  CStatusBar::CommandToIndex

Получает индекс индикатор с заданным идентификатором.

```
int CommandToIndex(UINT nIDFind) const;
```

### <a name="parameters"></a>Параметры

*nIDFind*<br/>
Идентификатор строки индикатора —, индекс которого требуется извлечь.

### <a name="return-value"></a>Возвращаемое значение

Индекс индикатора успешного выполнения; -1, если не выполнено.

### <a name="remarks"></a>Примечания

Индекс первого индикатора равно 0.

##  <a name="create"></a>  CStatusBar::Create

Создает (дочернего окна) в строке состояния и связывает его с `CStatusBar` объекта.

```
virtual BOOL Create(
    CWnd* pParentWnd,
    DWORD dwStyle = WS_CHILD | WS_VISIBLE | CBRS_BOTTOM,
    UINT nID = AFX_IDW_STATUS_BAR);
```

### <a name="parameters"></a>Параметры

*pParentWnd*<br/>
Указатель на [CWnd](../../mfc/reference/cwnd-class.md) объекта, окно которого Windows является родительским для объекта строки состояния.

*dwStyle*<br/>
Стиль строки состояния. Помимо стандартных Windows [стили](../../mfc/reference/styles-used-by-mfc.md#window-styles), поддерживаются следующие стили.

- Панель элементов управления CBRS_TOP — в верхней части окна области.

- Панель элементов управления CBRS_BOTTOM — в нижней части окна области.

- При изменении размера родительской панели элементов управления CBRS_NOALIGN не перемещен.

*nID*<br/>
Идентификатор элемента управления панель инструментов дочернего окна.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="remarks"></a>Примечания

Также задает начальное шрифт и устанавливает состояние высоты строки на значение по умолчанию.

##  <a name="createex"></a>  CStatusBar::CreateEx

Вызывайте эту функцию для создания (дочернего окна) в строке состояния и свяжите ее с `CStatusBar` объекта.

```
virtual BOOL CreateEx(
    CWnd* pParentWnd,
    DWORD dwCtrlStyle = 0,
    DWORD dwStyle = WS_CHILD | WS_VISIBLE | CBRS_BOTTOM,
    UINT nID = AFX_IDW_STATUS_BAR);
```

### <a name="parameters"></a>Параметры

*pParentWnd*<br/>
Указатель на [CWnd](../../mfc/reference/cwnd-class.md) объекта, окно которого Windows является родительским для объекта строки состояния.

*dwCtrlStyle*<br/>
Дополнительные стили для создания внедренных [CStatusBarCtrl](../../mfc/reference/cstatusbarctrl-class.md) объекта. Значение по умолчанию указывает строку состояния без захвата для изменения размера или подсказки поддержки. Существуют следующие стили панели состояния поддерживается:

- SBARS_SIZEGRIP управления строкой состояния включает в себя захват для изменения размера в правом конце строки состояния. Захват регулировки размера аналогичен рамкой для изменения размера; он представляет собой прямоугольную область, в который пользователь может щелкните и перетащите для изменения размеров родительского окна.

- SBT_TOOLTIPS строка состояния поддерживает подсказки.

Дополнительные сведения об этих стилей, см. в разделе [параметры для CStatusBarCtrl](../../mfc/settings-for-the-cstatusbarctrl.md).

*dwStyle*<br/>
Стиль строки состояния. Значение по умолчанию указывает, что созданы в строке состояния отображается в нижней части окна фрейма. Применить любое сочетание строки стили элемента управления, перечисленные в состояния [стили окна](../../mfc/reference/styles-used-by-mfc.md#window-styles) и [CDialogBar::Create](../../mfc/reference/cdialogbar-class.md#create). Тем не менее этот параметр должен всегда включать WS_CHILD и WS_VISIBLE стили.

*nID*<br/>
Идентификатор дочернего окна в строке состояния.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="remarks"></a>Примечания

Эта функция также задает начальное шрифт и устанавливает состояние высоты строки на значение по умолчанию.

Используйте `CreateEx`, а не [создать](#create), при определенных стилей должен указываться во время создания внедренные строки состояния. Например, задать *dwCtrlStyle* для SBT_TOOLTIPS для отображения всплывающих подсказок в объекте строки состояния.

##  <a name="cstatusbar"></a>  CStatusBar::CStatusBar

Создает `CStatusBar` , шрифт по умолчанию строки состояния при необходимости создает и задает характеристики шрифта для значения по умолчанию.

```
CStatusBar();
```

##  <a name="drawitem"></a>  CStatusBar::DrawItem

Эта функция-член вызывается платформой при изменении внешнего вида строка владельцем состояния.

```
virtual void DrawItem(LPDRAWITEMSTRUCT lpDrawItemStruct);
```

### <a name="parameters"></a>Параметры

*lpDrawItemStruct*<br/>
Указатель на [DRAWITEMSTRUCT](/windows/desktop/api/winuser/ns-winuser-tagdrawitemstruct) структуру, содержащую сведения о типе документа требуется.

### <a name="remarks"></a>Примечания

`itemAction` Членом `DRAWITEMSTRUCT` структура определяет рисования действие, которое должно быть выполнено. Переопределите эту функцию-член для реализации рисования для рисуемого владельцем `CStatusBar` объекта. Приложение следует восстановить всех графических устройств (интерфейс) выбранных объектов контекста отображения, указано в *lpDrawItemStruct* до завершения операции этой функции-члена.

##  <a name="getitemid"></a>  CStatusBar::GetItemID

Возвращает идентификатор индикатора, определяемое *nIndex*.

```
UINT GetItemID(int nIndex) const;
```

### <a name="parameters"></a>Параметры

*nIndex*<br/>
Индекс, идентификатор которого — должны быть получены индикатора.

### <a name="return-value"></a>Возвращаемое значение

Идентификатор индикатора, определяемое *nIndex*.

##  <a name="getitemrect"></a>  CStatusBar::GetItemRect

Копирует координаты индикатора, определяемое *nIndex* в структуру, на которые указывают *lpRect*.

```
void GetItemRect(
    int nIndex,
    LPRECT lpRect) const;
```

### <a name="parameters"></a>Параметры

*nIndex*<br/>
Индекс индикатор, должны быть получены, координаты прямоугольника.

*lpRect*<br/>
Указывает на [RECT](https://msdn.microsoft.com/library/windows/desktop/dd162897) структуры или [CRect](../../atl-mfc-shared/reference/crect-class.md) объект, принимающий координаты индикатора, определяемое *nIndex*.

### <a name="remarks"></a>Примечания

Координаты указываются в пикселях относительно верхнего левого угла строки состояния.

##  <a name="getpaneinfo"></a>  CStatusBar::GetPaneInfo

Наборы *nID*, *nStyle*, и *cxWidth* идентификатор, стиль и ширину области индикатора в расположении, заданном параметром *nIndex*.

```
void GetPaneInfo(
    int nIndex,
    UINT& nID,
    UINT& nStyle,
    int& cxWidth) const;
```

### <a name="parameters"></a>Параметры

*nIndex*<br/>
Индекс панели, сведения о которой требуется получить.

*nID*<br/>
Ссылка на целое число без знака, ей присваивается идентификатор области.

*nStyle*<br/>
Ссылка на целое число без знака, которой присваивается стиль области.

*cxWidth*<br/>
Ссылка на целое число, равное ширину области.

##  <a name="getpanestyle"></a>  CStatusBar::GetPaneStyle

Вызовите эту функцию-член для извлечения стиль панели строки состояния.

```
UINT GetPaneStyle(int nIndex) const;
```

### <a name="parameters"></a>Параметры

*nIndex*<br/>
Индекс панели, стиль которого требуется получить.

### <a name="return-value"></a>Возвращаемое значение

Стиль панели строки состояния, определяемое *nIndex*.

### <a name="remarks"></a>Примечания

Стиль области определяет, как отображается области.

Список стилей, доступных для строки состояния, см. в разделе [создать](#create).

##  <a name="getpanetext"></a>  CStatusBar::GetPaneText

Вызовите эту функцию-член для извлечения текста, который отображается в панели строки состояния.

```
CString GetPaneText(int nIndex) const;  void GetPaneText(int nIndex, CString& rString) const;
```

### <a name="parameters"></a>Параметры

*nIndex*<br/>
Индекс панели, текст которого требуется получить.

*rString*<br/>
Ссылку на [CString](../../atl-mfc-shared/reference/cstringt-class.md) объекта, содержащего текст, который требуется получить.

### <a name="return-value"></a>Возвращаемое значение

Объект `CString` объект, содержащий текст области.

### <a name="remarks"></a>Примечания

Вторая форма этого члена функции заливки `CString` с текстом строки.

##  <a name="getstatusbarctrl"></a>  CStatusBar::GetStatusBarCtrl

Эта функция-член обеспечивает прямой доступ к базовой общего элемента управления.

```
CStatusBarCtrl& GetStatusBarCtrl() const;
```

### <a name="return-value"></a>Возвращаемое значение

Содержит ссылку на [CStatusBarCtrl](../../mfc/reference/cstatusbarctrl-class.md) объекта.

### <a name="remarks"></a>Примечания

Используйте `GetStatusBarCtrl` преимуществами функциональные возможности стандартного элемента управления строки состояния Windows и пользоваться преимуществами поддержки [CStatusBarCtrl](../../mfc/reference/cstatusbarctrl-class.md) предоставляет для настройки строки состояния. Например с помощью стандартного элемента управления, можно указать стилем, включающим захват для изменения размера в строке состояния или вы можете указать стиль, чтобы в строке состояния отображается в верхней части клиентской области родительского окна.

Более общие сведения о стандартных элементах управления см. в разделе [стандартные элементы управления](/windows/desktop/Controls/common-controls-intro) в пакете Windows SDK.

##  <a name="setindicators"></a>  CStatusBar::SetIndicators

Задает идентификатор каждого индикатора к значению, заданному в соответствующий элемент массива *lpIDArray*, загружает строковый ресурс, указанная с помощью каждого идентификатора и задает текст для индикатора в строку.

```
BOOL SetIndicators(
    const UINT* lpIDArray,
    int nIDCount);
```

### <a name="parameters"></a>Параметры

*lpIDArray*<br/>
Указатель на массив идентификаторов.

*nIDCount*<br/>
Число элементов в массиве, на которые указывают *lpIDArray*.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

##  <a name="setpaneinfo"></a>  CStatusBar::SetPaneInfo

Задает области указанного индикатор новый идентификатор, стиля и ширины.

```
void SetPaneInfo(
    int nIndex,
    UINT nID,
    UINT nStyle,
    int cxWidth);
```

### <a name="parameters"></a>Параметры

*nIndex*<br/>
Индекс панели индикаторов, стиль которого является устанавливаемое значение.

*nID*<br/>
Новый идентификатор для панели индикаторов.

*nStyle*<br/>
Создание стиля для панели индикаторов.

*cxWidth*<br/>
Новое значение ширины панели индикаторов.

### <a name="remarks"></a>Примечания

Поддерживаются следующие стили индикатора:

- Нет SBPS_NOBORDERS трехмерной границы вокруг области.

- Обратный SBPS_POPOUT границы, чтобы текст «раскрывается.»

- Не делать SBPS_DISABLED рисовать текст.

- Область SBPS_STRETCH Stretch для заполнения неиспользуемое пространство. Только одна область, в строке состояния может иметь этот стиль.

- Нет SBPS_NORMAL stretch, границы и выступающего.

##  <a name="setpanestyle"></a>  CStatusBar::SetPaneStyle

Вызывайте эту функцию члена, если требуется задать стиль панели строки состояния.

```
void SetPaneStyle(
    int nIndex,
    UINT nStyle);
```

### <a name="parameters"></a>Параметры

*nIndex*<br/>
Индекс, стиль которого является задаваемый области.

*nStyle*<br/>
Стиль области, стиль которого расположена устанавливаемое значение.

### <a name="remarks"></a>Примечания

Стиль области определяет, как отображается области.

Список стилей, доступных для строки состояния, см. в разделе [SetPaneInfo](#setpaneinfo).

##  <a name="setpanetext"></a>  CStatusBar::SetPaneText

Вызовите для задания области текста в строку, на которые указывает эта функция-член *lpszNewText*.

```
BOOL SetPaneText(
    int nIndex,
    LPCTSTR lpszNewText,
    BOOL bUpdate = TRUE);
```

### <a name="parameters"></a>Параметры

*nIndex*<br/>
Индекс области, в которых указано устанавливаемое значение.

*lpszNewText*<br/>
Указатель на новый текст панели.

*bСтратегии обновлениями*<br/>
Значение TRUE, если область становится недействительным после изменения текста.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="remarks"></a>Примечания

После вызова метода `SetPaneText`, необходимо добавить обработчик обновления пользовательского интерфейса для отображения нового текста в строке состояния.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCDocView#176](../../mfc/codesnippet/cpp/cstatusbar-class_1.cpp)]

[!code-cpp[NVC_MFCDocView#177](../../mfc/codesnippet/cpp/cstatusbar-class_2.cpp)]

[!code-cpp[NVC_MFCDocView#178](../../mfc/codesnippet/cpp/cstatusbar-class_3.cpp)]

## <a name="see-also"></a>См. также

[Пример MFC CTRLBARS](../../visual-cpp-samples.md)<br/>
[Образец DLGCBR32 MFC](../../visual-cpp-samples.md)<br/>
[Класс CControlBar](../../mfc/reference/ccontrolbar-class.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Класс CStatusBarCtrl](../../mfc/reference/cstatusbarctrl-class.md)<br/>
[Класс CControlBar](../../mfc/reference/ccontrolbar-class.md)
