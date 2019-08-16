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
ms.openlocfilehash: 483998529b83d9b28c6ab1b219c4f5288dbd8ec7
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/15/2019
ms.locfileid: "69503834"
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
|[COleIPFrameWnd:: COleIPFrameWnd](#coleipframewnd)|Создает объект `COleIPFrameWnd`.|

### <a name="public-methods"></a>Открытые методы

|name|Описание|
|----------|-----------------|
|[COleIPFrameWnd:: OnCreateControlBars](#oncreatecontrolbars)|Вызывается структурой при активации элемента для редактирования на месте.|
|[COleIPFrameWnd:: Репоситионфраме](#repositionframe)|Вызвано структурой для изменения расположения окна редактирования на месте.|

## <a name="remarks"></a>Примечания

Этот класс создает и позиционирует панели элементов управления в окне документа приложения контейнера. Он также обрабатывает уведомления, созданные внедренным объектом [колересизебар](../../mfc/reference/coleresizebar-class.md) , когда пользователь изменяет размер окна редактирования на месте.

Дополнительные сведения об использовании `COleIPFrameWnd`см. в статье [Активация](../../mfc/activation-cpp.md).

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CFrameWnd](../../mfc/reference/cframewnd-class.md)

`COleIPFrameWnd`

## <a name="requirements"></a>Требования

**Заголовок:** афксоле. h

##  <a name="coleipframewnd"></a>COleIPFrameWnd:: COleIPFrameWnd

`COleIPFrameWnd` Создает объект и инициализирует его сведения о состоянии на месте, которые хранятся в структуре типа олеинплацефрамеинфо.

```
COleIPFrameWnd();
```

### <a name="remarks"></a>Примечания

Дополнительные сведения см. в разделе [олеинплацефрамеинфо](/windows/win32/api/oleidl/ns-oleidl-oifi) в Windows SDK.

##  <a name="oncreatecontrolbars"></a>COleIPFrameWnd:: OnCreateControlBars

Платформа вызывает функцию, `OnCreateControlBars` когда элемент активируется для редактирования на месте.

```
virtual BOOL OnCreateControlBars(
    CWnd* pWndFrame,
    CWnd* pWndDoc);

virtual BOOL OnCreateControlBars(
    CFrameWnd* pWndFrame,
    CFrameWnd* pWndDoc);
```

### <a name="parameters"></a>Параметры

*пвндфраме*<br/>
Указатель на окно фрейма приложения контейнера.

*pWndDoc*<br/>
Указатель на окно уровня документа контейнера. Может иметь значение NULL, если контейнер является приложением SDI.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение при успешном выполнении; в противном случае — значение 0.

### <a name="remarks"></a>Примечания

Реализация по умолчанию не выполняет никаких действий. Переопределите эту функцию для выполнения специальной обработки, необходимой при создании панелей элементов управления.

##  <a name="repositionframe"></a>COleIPFrameWnd:: Репоситионфраме

Платформа вызывает `RepositionFrame` функцию-член для размещения панелей управления и перемещения окна редактирования на месте, чтобы все это было видимым.

```
virtual void RepositionFrame(
    LPCRECT lpPosRect,
    LPCRECT lpClipRect);
```

### <a name="parameters"></a>Параметры

*лппосрект*<br/>
Указатель на `RECT` структуру `CRect` или объект, содержащий координаты текущей позиции окна фрейма в пикселях относительно клиентской области.

*лпклипрект*<br/>
Указатель на `RECT` структуру `CRect` или объект, содержащий координаты текущего прямоугольника в окне фрейма в пикселях относительно клиентской области.

### <a name="remarks"></a>Примечания

Макет панелей элементов управления в окне контейнера отличается от структуры, выполняемой окном фрейма, не относящегося к OLE. Окно фрейма, не являющегося рамкой OLE, вычисляет положение панелей элементов управления и других объектов от определенного размера окна фрейма, как при вызове метода [CFrameWnd:: RecalcLayout](../../mfc/reference/cframewnd-class.md#recalclayout). Клиентская область остается после вычитания пространства для панелей элементов управления и других объектов. `COleIPFrameWnd` Окно, с другой стороны, позиционирует панели инструментов в соответствии с заданной клиентской областью. Иными словами, `CFrameWnd::RecalcLayout` Works «работает» из внешней среды, « `COleIPFrameWnd::RepositionFrame` а работает» из «внутренней».

## <a name="see-also"></a>См. также

[Пример MFC для примера HIERSVR](../../overview/visual-cpp-samples.md)<br/>
[Класс CFrameWnd](../../mfc/reference/cframewnd-class.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Класс CFrameWnd](../../mfc/reference/cframewnd-class.md)
