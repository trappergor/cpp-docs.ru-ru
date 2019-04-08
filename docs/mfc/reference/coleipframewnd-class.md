---
title: Класс COleIPFrameWnd
ms.date: 11/04/2016
f1_keywords:
- COleIPFrameWnd
- AFXOLE/COleIPFrameWnd
- AFXOLE/COleIPFrameWnd::COleIPFrameWnd
- AFXOLE/COleIPFrameWnd::OnCreateControlBars
- AFXOLE/COleIPFrameWnd::RepositionFrame
helpviewer_keywords:
- COleIPFrameWnd [MFC], COleIPFrameWnd
- COleIPFrameWnd [MFC], OnCreateControlBars
- COleIPFrameWnd [MFC], RepositionFrame
ms.assetid: 24abb2cb-826c-4dda-a287-d8a8900a5763
ms.openlocfilehash: 34388e635ba89d732ae3993074a2c8268e2289a3
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/05/2019
ms.locfileid: "58779616"
---
# <a name="coleipframewnd-class"></a>Класс COleIPFrameWnd

Основа для окна редактирования приложения "на месте".

## <a name="syntax"></a>Синтаксис

```
class COleIPFrameWnd : public CFrameWnd
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|name|Описание|
|----------|-----------------|
|[COleIPFrameWnd::COleIPFrameWnd](#coleipframewnd)|Создает объект `COleIPFrameWnd`.|

### <a name="public-methods"></a>Открытые методы

|name|Описание|
|----------|-----------------|
|[COleIPFrameWnd::OnCreateControlBars](#oncreatecontrolbars)|Вызывается платформой при активации элемента для редактирования на месте.|
|[COleIPFrameWnd::RepositionFrame](#repositionframe)|Вызывается платформой для изменения положения окна редактирования на месте.|

## <a name="remarks"></a>Примечания

Этот класс создает и позиций контроль линии в окне документа приложения-контейнера. Он также обрабатывает уведомления, созданные встроенный [COleResizeBar](../../mfc/reference/coleresizebar-class.md) объекта при изменении размера окна редактирования на месте.

Дополнительные сведения об использовании `COleIPFrameWnd`, см. в статье [активации](../../mfc/activation-cpp.md).

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CFrameWnd](../../mfc/reference/cframewnd-class.md)

`COleIPFrameWnd`

## <a name="requirements"></a>Требования

**Заголовок:** afxole.h

##  <a name="coleipframewnd"></a>  COleIPFrameWnd::COleIPFrameWnd

Создает `COleIPFrameWnd` объекта и инициализирует его сведения о состоянии на месте, которое хранится в структуре типа oleinplaceframeinfo, КОТОРУЮ.

```
COleIPFrameWnd();
```

### <a name="remarks"></a>Примечания

Дополнительные сведения см. в разделе [oleinplaceframeinfo, КОТОРУЮ](/windows/desktop/api/oleidl/ns-oleidl-tagoifi) в пакете Windows SDK.

##  <a name="oncreatecontrolbars"></a>  COleIPFrameWnd::OnCreateControlBars

Платформа вызывает `OnCreateControlBars` функционировать, когда элемент активируется для редактирования на месте.

```
virtual BOOL OnCreateControlBars(
    CWnd* pWndFrame,
    CWnd* pWndDoc);

virtual BOOL OnCreateControlBars(
    CFrameWnd* pWndFrame,
    CFrameWnd* pWndDoc);
```

### <a name="parameters"></a>Параметры

*pWndFrame*<br/>
Указатель на фрейм окна приложения-контейнера.

*принимает pWndDoc*<br/>
Указатель на окна документа контейнера. Может иметь значение NULL, если контейнер является приложением SDI.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение в случае успешного выполнения; в противном случае — 0.

### <a name="remarks"></a>Примечания

Реализация по умолчанию не выполняет никаких действий. Переопределите эту функцию для выполнения специальной обработки при создании панелей элементов управления.

##  <a name="repositionframe"></a>  COleIPFrameWnd::RepositionFrame

Платформа вызывает `RepositionFrame` функцию-член для размещения панелей элементов управления и изменить положение окна редактирования на месте, поэтому все из них является видимым.

```
virtual void RepositionFrame(
    LPCRECT lpPosRect,
    LPCRECT lpClipRect);
```

### <a name="parameters"></a>Параметры

*lpPosRect*<br/>
Указатель на `RECT` структуры или `CRect` объект, содержащий на месте кадров координаты текущего положения окна, в пикселях, относительно клиентской области.

*lpClipRect*<br/>
Указатель на `RECT` структуры или `CRect` объект, содержащий на месте фрейма окна текущий прямоугольник отсечения координатами в пикселях, относительно клиентской области.

### <a name="remarks"></a>Примечания

Макет панели элементов управления в окне контейнера отличается от, проведенных окна фрейма, отличных от OLE. Окна фрейма, отличных от OLE вычисляет положение панелей элементов управления и другим объектам размер заданного окна фрейма, как и в вызов [CFrameWnd::RecalcLayout](../../mfc/reference/cframewnd-class.md#recalclayout). Клиентская область — останется после вычитания пространства для панелей элементов управления и других объектов. Объект `COleIPFrameWnd` окно, с другой стороны, помещает панелей инструментов в соответствии с заданной клиентской области. Другими словами `CFrameWnd::RecalcLayout` работает «извне,», в то время как `COleIPFrameWnd::RepositionFrame` работает «наизнанку.»

## <a name="see-also"></a>См. также

[Пример MFC HIERSVR](../../overview/visual-cpp-samples.md)<br/>
[Класс CFrameWnd](../../mfc/reference/cframewnd-class.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Класс CFrameWnd](../../mfc/reference/cframewnd-class.md)
