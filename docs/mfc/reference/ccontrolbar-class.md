---
title: CControlBar Class
ms.date: 11/04/2016
f1_keywords:
- CControlBar
- AFXEXT/CControlBar
- AFXEXT/CControlBar::CControlBar
- AFXEXT/CControlBar::CalcDynamicLayout
- AFXEXT/CControlBar::CalcFixedLayout
- AFXEXT/CControlBar::CalcInsideRect
- AFXEXT/CControlBar::DoPaint
- AFXEXT/CControlBar::DrawBorders
- AFXEXT/CControlBar::DrawGripper
- AFXEXT/CControlBar::EnableDocking
- AFXEXT/CControlBar::GetBarStyle
- AFXEXT/CControlBar::GetBorders
- AFXEXT/CControlBar::GetCount
- AFXEXT/CControlBar::GetDockingFrame
- AFXEXT/CControlBar::IsFloating
- AFXEXT/CControlBar::OnUpdateCmdUI
- AFXEXT/CControlBar::SetBarStyle
- AFXEXT/CControlBar::SetBorders
- AFXEXT/CControlBar::SetInPlaceOwner
- AFXEXT/CControlBar::m_bAutoDelete
- AFXEXT/CControlBar::m_pInPlaceOwner
helpviewer_keywords:
- CControlBar [MFC], CControlBar
- CControlBar [MFC], CalcDynamicLayout
- CControlBar [MFC], CalcFixedLayout
- CControlBar [MFC], CalcInsideRect
- CControlBar [MFC], DoPaint
- CControlBar [MFC], DrawBorders
- CControlBar [MFC], DrawGripper
- CControlBar [MFC], EnableDocking
- CControlBar [MFC], GetBarStyle
- CControlBar [MFC], GetBorders
- CControlBar [MFC], GetCount
- CControlBar [MFC], GetDockingFrame
- CControlBar [MFC], IsFloating
- CControlBar [MFC], OnUpdateCmdUI
- CControlBar [MFC], SetBarStyle
- CControlBar [MFC], SetBorders
- CControlBar [MFC], SetInPlaceOwner
- CControlBar [MFC], m_bAutoDelete
- CControlBar [MFC], m_pInPlaceOwner
ms.assetid: 4d668c55-9b42-4838-97ac-cf2b3000b82c
ms.openlocfilehash: c2f8ea48bf9a1f015928650085b07198b152771a
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2020
ms.locfileid: "81754797"
---
# <a name="ccontrolbar-class"></a>CControlBar Class

Базовый класс для класса контроль-бара [CStatusBar](../../mfc/reference/cstatusbar-class.md), [CToolBar](../../mfc/reference/ctoolbar-class.md), [CDialogBar](../../mfc/reference/cdialogbar-class.md), [CReBar](../../mfc/reference/crebar-class.md)и [COleResizeBar](../../mfc/reference/coleresizebar-class.md).

## <a name="syntax"></a>Синтаксис

```
class CControlBar : public CWnd
```

## <a name="members"></a>Участники

### <a name="protected-constructors"></a>Защищенные конструкторы

|Имя|Описание|
|----------|-----------------|
|[CControlBar::CControlBar](#ccontrolbar)|Формирует объект `CControlBar`.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CControlBar::CalcDynamicLayout](#calcdynamiclayout)|Возвращает размер динамической панели управления в качестве объекта [CSize.](../../atl-mfc-shared/reference/csize-class.md)|
|[CControlBar::CalcFixedLayout](#calcfixedlayout)|Возвращает размер панели управления в качестве объекта [CSize.](../../atl-mfc-shared/reference/csize-class.md)|
|[CControlBar::CalcInsideRect](#calcinsiderect)|Возвращает текущие размеры области панели управления; включая границы.|
|[CControlBar::DoPaint](#dopaint)|Рендерс границ и захват контрольной панели.|
|[CControlBar::DrawBorders](#drawborders)|Рендерс границы панели управления.|
|[CControlBar::DrawGripper](#drawgripper)|Рендерс захват контрольной панели.|
|[CControlBar::EnableDocking](#enabledocking)|Позволяет пристыковаться к панели управления или плавать.|
|[CControlBar::GetBarStyle](#getbarstyle)|Извлекает настройки стиля панели управления.|
|[CControlBar::GetBorders](#getborders)|Извлекает значения границы панели управления.|
|[CControlBar::GetCount](#getcount)|Возвращает количество элементов, не входящих в HWND, в панели управления.|
|[CControlBar::GetDockingFrame](#getdockingframe)|Возвращает указатель в рамку, к которой пристыкована панель управления.|
|[CControlBar::IsFloating](#isfloating)|Возвращает ненулевое значение, если панель управления, о котором идет речь, является плавающей панелью управления.|
|[CControlBar::OnUpdateCmdUI](#onupdatecmdui)|Вызывает обработчиков управления.|
|[CControlBar::SetBarStyle](#setbarstyle)|Изменяет настройки стиля панели управления.|
|[CControlBar::SetBorders](#setborders)|Устанавливает значения границы панели управления.|
|[CControlbar::SetinPlaceOwner](#setinplaceowner)|Изменяет владельца панели управления.|

### <a name="public-data-members"></a>Открытые члены данных

|Имя|Описание|
|----------|-----------------|
|[CControlBar::m_bAutoDelete](#m_bautodelete)|Если ненулевой `CControlBar` объект удаляется при уничтожении панели управления Windows.|
|[CControlBar::m_pInPlaceOwner](#m_pinplaceowner)|Владелец диспетчерской панели.|

## <a name="remarks"></a>Remarks

Панель управления — это окно, обычно выровненое влево или вправо от окна рамы. Он может содержать элементы, основанные на HWND, которые являются окнами, которые генерируют и отвечают на сообщения Windows, или не-HWND-элементы, которые не являются окнами и управляются кодом приложения или кодом фрейма. Лист коробки и элементы управления для действенной дочки являются примерами элементов управления на основе HWND; стекол статус-бар и кнопки bitmap являются примерами элементов управления на основе HWND.

Окна панели управления обычно являются окнами ребенка родительского окна кадра и, как правило, являются братьями и сестрами для просмотра клиента или mDI клиента окна кадра. Объект `CControlBar` использует информацию о прямоугольнике клиента родительского окна, чтобы позиционировать себя. Затем он информирует родительское окно о том, сколько места остается нераспределенным в клиентской области родительского окна.

Для получения `CControlBar`дополнительной информации о , см.:

- [Панели элементов управления](../../mfc/control-bars.md)

- [Техническое примечание 31: Бары управления](../../mfc/tn031-control-bars.md).

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

`CControlBar`

## <a name="requirements"></a>Требования

**Заголовок:** afxext.h

## <a name="ccontrolbarcalcdynamiclayout"></a><a name="calcdynamiclayout"></a>CControlBar::CalcDynamicLayout

Платформа вызывает эту функцию члена для расчета размеров динамической панели инструментов.

```
virtual CSize CalcDynamicLayout(
    int nLength,
    DWORD nMode);
```

### <a name="parameters"></a>Параметры

*nДлина*<br/>
Запрашиваемый размер панели управления, горизонтальный или вертикальный, в зависимости от *dwMode.*

*nMode*<br/>
Для определения высоты и ширины динамической панели управления используются следующие предопределенные флаги. Используйте оператора bitwise-OR (&#124;) для объединения флагов.

|Флаги режима рабы низа|Значение|
|-----------------------|-------------------|
|LM_STRETCH|Указывает, следует ли растягивать панель управления до размера кадра. Установите, если бар не является стыковки бар (не доступен для стыковки). Не устанавливается, когда бар пристыкован или плавает (доступен для стыковки). Если установлен, LM_STRETCH игнорирует *nLength* и возвращает размеры в зависимости от состояния LM_HORZ. LM_STRETCH работает аналогично параметру *bStretch,* используемому в [CalcFixedLayout;](#calcfixedlayout) увидеть, что член функции для получения дополнительной информации о взаимосвязи между растяжением и ориентации.|
|LM_HORZ|Означает, что бар горизонтально или вертикально ориентирован. Установите, если бар горизонтально ориентирован, и если она вертикально ориентирована, она не установлена. LM_HORZ работает аналогично параметру *bHorz,* используемому в [CalcFixedLayout;](#calcfixedlayout) увидеть, что член функции для получения дополнительной информации о взаимосвязи между растяжением и ориентации.|
|LM_MRUWIDTH|В последнее время используется динамическая ширина. Игнорирует параметр *nLength* и использует запоминаемую совсем недавно использованную ширину.|
|LM_HORZDOCK|Горизонтальные стыковочные размеры. Игнорирует параметр *nLength* и возвращает динамический размер с самой большой шириной.|
|LM_VERTDOCK|Вертикальные пристыкованные размеры. Игнорирует параметр *nLength* и возвращает динамический размер с самой большой высотой.|
|LM_LENGTHY|Установите, если *nLength* указывает высоту (Y-направление) вместо ширины.|
|LM_COMMIT|Сбросы LM_MRUWIDTH к текущей ширине плавающей панели управления.|

### <a name="return-value"></a>Возвращаемое значение

Размер панели управления в пикселях объекта [CSize.](../../atl-mfc-shared/reference/csize-class.md)

### <a name="remarks"></a>Remarks

Переизобить эту функцию участника, чтобы обеспечить свой собственный динамический макет в классах, которые вы получаете из. `CControlBar` Классы MFC, `CControlBar`полученные из таких, как [CToolbar,](../../mfc/reference/ctoolbar-class.md)переопределяют эту функцию участника и обеспечивают их собственную реализацию.

## <a name="ccontrolbarcalcfixedlayout"></a><a name="calcfixedlayout"></a>CControlBar::CalcFixedLayout

Вызов исчисляйте эту функцию участника для расчета горизонтального размера панели управления.

```
virtual CSize CalcFixedLayout(
    BOOL bStretch,
    BOOL bHorz);
```

### <a name="parameters"></a>Параметры

*bStretch*<br/>
Указывает, следует ли растягивать планку до размера кадра. Параметр *bStretch* является незеролевым, когда бар не является стыковочным баром (не доступен для стыковки) и 0, когда он стыковывается или плавает (доступен для стыковки).

*bHorz*<br/>
Означает, что бар горизонтально или вертикально ориентирован. Параметр *bHorz* незерн, если бар горизонтально ориентирован и 0, если он вертикально ориентирован.

### <a name="return-value"></a>Возвращаемое значение

Размер панели управления в пикселях `CSize` объекта.

### <a name="remarks"></a>Remarks

Панели управления, такие как панели инструментов, могут растягиваться горизонтально или вертикально для размещения кнопок, содержащихся в панели управления.

Если *bStretch* является правдой, растянуть размер вдоль ориентации, предоставляемой *bHorz*. Другими словами, если *bHorz* является FALSE, панель управления растягивается вертикально. Если *bStretch* является FALSE, никакого растяжения не происходит. В следующей таблице показаны возможные перестановки, и в результате стилей управления бар, *bStretch* и *bHorz*.

|bStretch|bHorz|Растяжения|Ориентация|Стыковка/не стыковка|
|--------------|-----------|----------------|-----------------|--------------------------|
|TRUE|TRUE|Горизонтальное растяжение|Горизонтально ориентированный|Не стыковка|
|TRUE|FALSE|Вертикальное растяжение|Вертикально ориентированные|Не стыковка|
|FALSE|TRUE|Нет растяжения доступны|Горизонтально ориентированный|Закрепление|
|FALSE|FALSE|Нет растяжения доступны|Вертикально ориентированные|Закрепление|

## <a name="ccontrolbarcalcinsiderect"></a><a name="calcinsiderect"></a>CControlBar::CalcInsideRect

Рамочная система вызывает эту функцию для расчета клиентской области панели управления.

```
virtual void CalcInsideRect(
    CRect& rect,
    BOOL bHorz) const;
```

### <a name="parameters"></a>Параметры

*rect*<br/>
Содержит текущие размеры панели управления; включая границы.

*bHorz*<br/>
Означает, что бар горизонтально или вертикально ориентирован. Параметр *bHorz* незерн, если бар горизонтально ориентирован и 0, если он вертикально ориентирован.

### <a name="remarks"></a>Remarks

Эта функция вызывается до того, как будет окрашена панель управления.

Переопределить эту функцию, чтобы настроить визуализацию границ и сцепление бар панели управления.

## <a name="ccontrolbarccontrolbar"></a><a name="ccontrolbar"></a>CControlBar::CControlBar

Формирует объект `CControlBar`.

```
CControlBar();
```

## <a name="ccontrolbardopaint"></a><a name="dopaint"></a>CControlBar::DoPaint

Вызывается рамкой, чтобы сделать границы и сцепление бар панели управления.

```
virtual void DoPaint(CDC* pDC);
```

### <a name="parameters"></a>Параметры

*pDC*<br/>
Указывает на контекст устройства, который будет использоваться для визуализации границ и захвата панели управления.

### <a name="remarks"></a>Remarks

Переопределить эту функцию, чтобы настроить поведение чертежа панели управления.

Другой метод настройки заключается `DrawBorders` `DrawGripper` в том, чтобы переопределить и функции и добавить пользовательский код рисования для границ и захвата. Поскольку эти методы называются методом по умолчанию, `DoPaint` переопределение не `DoPaint` требуется.

## <a name="ccontrolbardrawborders"></a><a name="drawborders"></a>CControlBar::DrawBorders

Вызывается рамками для визуализации границ панели управления.

```
virtual void DrawBorders(
    CDC* pDC,
    CRect& rect);
```

### <a name="parameters"></a>Параметры

*pDC*<br/>
Указывает на контекст устройства, который будет использоваться для визуализации границ панели управления.

*rect*<br/>
Объект, `CRect` содержащий размеры панели управления.

### <a name="remarks"></a>Remarks

Переопределить эту функцию, чтобы настроить внешний вид границ панели управления.

## <a name="ccontrolbardrawgripper"></a><a name="drawgripper"></a>CControlBar::DrawGripper

Вызывается рамкой, чтобы сделать захват панели управления.

```
virtual void DrawGripper(
    CDC* pDC,
    const CRect& rect);
```

### <a name="parameters"></a>Параметры

*pDC*<br/>
Указывает на контекст устройства, который будет использоваться для визуализации захвата панели управления.

*rect*<br/>
Объект, `CRect` содержащий размеры захвата панели управления.

### <a name="remarks"></a>Remarks

Переопределить эту функцию, чтобы настроить внешний вид захвата панели управления.

## <a name="ccontrolbarenabledocking"></a><a name="enabledocking"></a>CControlBar::EnableDocking

Вызовите эту функцию, чтобы включить панель управления в стыковку.

```cpp
void EnableDocking(DWORD dwDockStyle);
```

### <a name="parameters"></a>Параметры

*dwDockStyle*<br/>
Определяет, поддерживает ли панель управления стыковку и стороны родительского окна, к которым может быть пристыкована панель управления, при поддержке. Может быть один или несколько из следующих:

- CBRS_ALIGN_TOP позволяет стыковки в верхней части клиентской области.

- CBRS_ALIGN_BOTTOM позволяет стыковки в нижней части клиентской области.

- CBRS_ALIGN_LEFT позволяет стыковки на левой стороне клиентской области.

- CBRS_ALIGN_RIGHT Позволяет стыковки на правой стороне клиентской области.

- CBRS_ALIGN_ANY позволяет стыковки с любой стороны клиентской области.

- CBRS_FLOAT_MULTI позволяет плавать в одном окне мини-рамки.

Если 0 (т.е. нет флагов), панель управления не будет пристыковаться.

### <a name="remarks"></a>Remarks

Указанные стороны должны соответствовать одной из сторон, включенных для стыковки в окне кадра назначения, или панель управления не может быть пристыкована к этому окну рамы.

## <a name="ccontrolbargetbarstyle"></a><a name="getbarstyle"></a>CControlBar::GetBarStyle

Вызов эту функцию, чтобы определить, какие **CBRS_** (стили панели управления) в настоящее время настроены для панели управления.

```
DWORD GetBarStyle();
```

### <a name="return-value"></a>Возвращаемое значение

Текущие **CBRS_** (стили панели управления) для панели управления. Смотрите [CControlBar::SetBarStyle](#setbarstyle) для полного списка доступных стилей.

### <a name="remarks"></a>Remarks

Не обрабатывает **WS_** (стиль окна) стилей.

## <a name="ccontrolbargetborders"></a><a name="getborders"></a>CControlBar::GetBorders

Возвращает текущие значения границы для панели управления.

```
CRect GetBorders() const;
```

### <a name="return-value"></a>Возвращаемое значение

Объект, `CRect` содержащий текущую ширину (в пикселях) каждой стороны объекта панели управления. Например, значение *левого* члена объекта [CRect](../../atl-mfc-shared/reference/crect-class.md) — это ширина границы левой руки.

## <a name="ccontrolbargetcount"></a><a name="getcount"></a>CControlBar::GetCount

Возвращает количество элементов, не входящих `CControlBar` в HWND, на объекте.

```
int GetCount() const;
```

### <a name="return-value"></a>Возвращаемое значение

Количество элементов, не входящих `CControlBar` в HWND, на объекте. Эта функция возвращает 0 для объекта [CDialogBar.](../../mfc/reference/cdialogbar-class.md)

### <a name="remarks"></a>Remarks

Тип элемента зависит от производного объекта: стекол для объектов [CStatusBar,](../../mfc/reference/cstatusbar-class.md) а также кнопок и сепараторов для объектов [CToolBar.](../../mfc/reference/ctoolbar-class.md)

## <a name="ccontrolbargetdockingframe"></a><a name="getdockingframe"></a>CControlBar::GetDockingFrame

Вызовите эту функцию участника, чтобы получить указатель на текущее окно кадра, к которому пристыкована панель управления.

```
CFrameWnd* GetDockingFrame() const;
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на окно рамы в случае успеха; в противном случае NULL.

Если панель управления не пристыкована к окну кадра (т.е. если панель управления плавает), эта функция вернет указатель своему родительскому [CMiniFrameWnd.](../../mfc/reference/cminiframewnd-class.md)

### <a name="remarks"></a>Remarks

Для получения дополнительной информации о доковых баров управления, [см. CControlBar::EnableDocking](#enabledocking) и [CFrameWnd: :DockControlBar](../../mfc/reference/cframewnd-class.md#dockcontrolbar).

## <a name="ccontrolbarisfloating"></a><a name="isfloating"></a>CControlBar::IsFloating

Вызовите эту функцию участника, чтобы определить, плавает ли панель управления или пристыкована.

```
BOOL IsFloating() const;
```

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если панель управления плавает; в противном случае 0.

### <a name="remarks"></a>Remarks

Чтобы изменить состояние панели управления от пристыкованного к плавающему, позвоните [cFrameWnd::FloatControlBar](../../mfc/reference/cframewnd-class.md#floatcontrolbar).

## <a name="ccontrolbarm_bautodelete"></a><a name="m_bautodelete"></a>CControlBar::m_bAutoDelete

Если ненулевой `CControlBar` объект удаляется при уничтожении панели управления Windows.

```
BOOL m_bAutoDelete;
```

### <a name="remarks"></a>Remarks

*m_bAutoDelete* является общедоступной переменной типа BOOL.

Объект панели управления обычно встраивается в объект окна кадра. В этом случае *m_bAutoDelete* 0, поскольку встроенный объект панели управления разрушается при уничтожении окна рамы.

Установите эту переменную на ненулевое значение, если вы выделяете `CControlBar` объект на куче и не планируете вызывать **удаление.**

## <a name="ccontrolbarm_pinplaceowner"></a><a name="m_pinplaceowner"></a>CControlBar::m_pInPlaceOwner

Владелец диспетчерской панели.

```
CWnd* m_pInPlaceOwner;
```

## <a name="ccontrolbaronupdatecmdui"></a><a name="onupdatecmdui"></a>CControlBar::OnUpdateCmdUI

Эта функция члена вызывается инфраструктурой для обновления состояния панели инструментов или панели статуса.

```
virtual void OnUpdateCmdUI(
    CFrameWnd* pTarget,
    BOOL bDisableIfNoHndler) = 0;
```

### <a name="parameters"></a>Параметры

*pTarget*<br/>
Указывает на основное окно кадра приложения. Этот указатель используется для реуктора обновления сообщений.

*bDisableIfNoHndler*<br/>
Пометить, следует ли автоматически отображать элемент управления, не обличенного обработчиком обновлений, как отключенный.

### <a name="remarks"></a>Remarks

Чтобы обновить индивидуальную кнопку или панель, используйте ON_UPDATE_COMMAND_UI макрос на карте сообщений, чтобы настроить обработчик обновления соответствующим образом. Более подробную информацию об использовании этого макроса можно просмотреть [ON_UPDATE_COMMAND_UI.](message-map-macros-mfc.md#on_update_command_ui)

`OnUpdateCmdUI`называется фреймворком, когда приложение простаивает. Обновленное окно кадра должно быть окном ребенка, по крайней мере косвенно, видимого окна рамы. `OnUpdateCmdUI`является передовой переизбытки.

## <a name="ccontrolbarsetbarstyle"></a><a name="setbarstyle"></a>CControlBar::SetBarStyle

Вызовите эту функцию, чтобы установить желаемые **стили CBRS_** для панели управления.

```cpp
void SetBarStyle(DWORD dwStyle);
```

### <a name="parameters"></a>Параметры

*dwStyle*<br/>
Нужные стили для панели управления. Может быть один или несколько из следующих:

- CBRS_ALIGN_TOP позволяет пристыковаться к верхней части клиентской области окна рамы.

- CBRS_ALIGN_BOTTOM позволяет пристыковаться к нижней части клиентской области окна рамы.

- CBRS_ALIGN_LEFT позволяет пристыковаться к левой стороне клиентской области окна рамы.

- CBRS_ALIGN_RIGHT позволяет пристыковаться к правой стороне клиентской области окна рамы.

- CBRS_ALIGN_ANY позволяет пристыковаться к любой стороне клиентской области окна рамы.

- CBRS_BORDER_TOP вызывает нарисование границы на верхнем краю панели управления, когда она будет видна.

- CBRS_BORDER_BOTTOM вызывает нарисование границы на нижнем краю панели управления, когда она будет видна.

- CBRS_BORDER_LEFT вызывает нарисование границы на левом краю панели управления, когда она будет видна.

- CBRS_BORDER_RIGHT вызывает нарисование границы на правом краю панели управления, когда она будет видна.

- CBRS_FLOAT_MULTI позволяет плавать в одном окне мини-рамки.

- CBRS_TOOLTIPS Причины инструмент советы, которые будут отображаться для панели управления.

- CBRS_FLYBY вызывает обновление текста сообщения одновременно с советами по инструменту.

- CBRS_GRIPPER вызывает захват, похожий на тот, `CReBar` который используется на `CControlBar`полосах в объекте, который будет нарисован для любого -производного класса.

### <a name="remarks"></a>Remarks

Не влияет на настройки **WS_** (стиль окна).

## <a name="ccontrolbarsetborders"></a><a name="setborders"></a>CControlBar::SetBorders

Вызовите эту функцию, чтобы установить размер границ панели управления.

```cpp
void SetBorders(
    int cxLeft = 0,
    int cyTop = 0,
    int cxRight = 0,
    int cyBottom = 0);

void SetBorders(LPCRECT lpRect);
```

### <a name="parameters"></a>Параметры

*cxLeft*<br/>
Ширина (в пикселях) левой границы панели управления.

*cyTop*<br/>
Высота (в пикселях) верхней границы панели управления.

*cxRight*<br/>
Ширина (в пикселях) правой границы панели управления.

*cyBottom*<br/>
Высота (в пикселях) нижней границы панели управления.

*lpRect*<br/>
Указатель на объект [CRect,](../../atl-mfc-shared/reference/crect-class.md) содержащий текущую ширину (в пикселях) каждой границы объекта панели управления.

### <a name="example"></a>Пример

Следующий пример кода устанавливает верхнюю и нижнюю границы панели управления до 5 пикселей, а левую и правую границы до 2 пикселей:

[!code-cpp[NVC_MFCControlLadenDialog#61](../../mfc/codesnippet/cpp/ccontrolbar-class_1.cpp)]

## <a name="ccontrolbarsetinplaceowner"></a><a name="setinplaceowner"></a>CControlbar::SetinPlaceOwner

Изменяет владельца панели управления.

```cpp
void SetInPlaceOwner(CWnd* pWnd);
```

### <a name="parameters"></a>Параметры

*pWnd*<br/>
Указатель на объект `CWnd`.

### <a name="remarks"></a>Remarks

## <a name="see-also"></a>См. также раздел

[MFC Образец CTRLBARS](../../overview/visual-cpp-samples.md)<br/>
[Класс CWnd](../../mfc/reference/cwnd-class.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Класс CToolBar](../../mfc/reference/ctoolbar-class.md)<br/>
[Класс CDialogBar](../../mfc/reference/cdialogbar-class.md)<br/>
[Класс CStatusBar](../../mfc/reference/cstatusbar-class.md)<br/>
[Класс CReBar](../../mfc/reference/crebar-class.md)
