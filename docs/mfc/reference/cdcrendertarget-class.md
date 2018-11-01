---
title: Класс CDCRenderTarget
ms.date: 11/04/2016
f1_keywords:
- CDCRenderTarget
- AFXRENDERTARGET/CDCRenderTarget
- AFXRENDERTARGET/CDCRenderTarget::CDCRenderTarget
- AFXRENDERTARGET/CDCRenderTarget::Attach
- AFXRENDERTARGET/CDCRenderTarget::BindDC
- AFXRENDERTARGET/CDCRenderTarget::Create
- AFXRENDERTARGET/CDCRenderTarget::Detach
- AFXRENDERTARGET/CDCRenderTarget::GetDCRenderTarget
- AFXRENDERTARGET/CDCRenderTarget::m_pDCRenderTarget
helpviewer_keywords:
- CDCRenderTarget [MFC], CDCRenderTarget
- CDCRenderTarget [MFC], Attach
- CDCRenderTarget [MFC], BindDC
- CDCRenderTarget [MFC], Create
- CDCRenderTarget [MFC], Detach
- CDCRenderTarget [MFC], GetDCRenderTarget
- CDCRenderTarget [MFC], m_pDCRenderTarget
ms.assetid: aa8059c9-08e6-49e4-9b8c-00fa54077a61
ms.openlocfilehash: e172d175bba5b4c379f7cd29451d7ad4215d9c68
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50541717"
---
# <a name="cdcrendertarget-class"></a>Класс CDCRenderTarget

Оболочка для ID2D1DCRenderTarget.

## <a name="syntax"></a>Синтаксис

```
class CDCRenderTarget : public CRenderTarget;
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CDCRenderTarget::CDCRenderTarget](#cdcrendertarget)|Создает объект CDCRenderTarget.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CDCRenderTarget::Attach](#attach)|Присоединение существующих отрисовки целевой интерфейс к объекту|
|[CDCRenderTarget::BindDC](#binddc)|Связывает целевой объект отрисовки на контекст устройства, к которому она выдает команд рисования|
|[CDCRenderTarget::Create](#create)|Создает CDCRenderTarget.|
|[CDCRenderTarget::Detach](#detach)|Отсоединяет интерфейс целевой объект отрисовки из объекта|
|[CDCRenderTarget::GetDCRenderTarget](#getdcrendertarget)|Возвращает интерфейс ID2D1DCRenderTarget|

### <a name="public-operators"></a>Открытые операторы

|Имя|Описание|
|----------|-----------------|
|[CDCRenderTarget::operator ID2D1DCRenderTarget *](#operator_id2d1dcrendertarget_star)|Возвращает интерфейс ID2D1DCRenderTarget|

### <a name="protected-data-members"></a>Защищенные члены данных

|name|Описание|
|----------|-----------------|
|[CDCRenderTarget::m_pDCRenderTarget](#m_pdcrendertarget)|Указатель на объект ID2D1DCRenderTarget.|

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CRenderTarget](../../mfc/reference/crendertarget-class.md)

[CDCRenderTarget](../../mfc/reference/cdcrendertarget-class.md)

## <a name="requirements"></a>Требования

**Заголовок:** afxrendertarget.h

##  <a name="attach"></a>  CDCRenderTarget::Attach

Присоединение существующих отрисовки целевой интерфейс к объекту

```
void Attach(ID2D1DCRenderTarget* pTarget);
```

### <a name="parameters"></a>Параметры

*pTarget*<br/>
Существующий интерфейс целевой объект отрисовки. Не может иметь значение NULL

##  <a name="binddc"></a>  CDCRenderTarget::BindDC

Связывает целевой объект отрисовки на контекст устройства, к которому она выдает команд рисования

```
BOOL BindDC(
    const CDC& dc,
    const CRect& rect);
```

### <a name="parameters"></a>Параметры

*dc*<br/>
Контекст устройства, в которую целевой объект отрисовки выдает команд рисования

*Rect*<br/>
Размеры дескриптор контекста устройства (HDC), к которому привязан целевой объект отрисовки

### <a name="return-value"></a>Возвращаемое значение

Если метод завершается успешно, возвращается значение TRUE. В противном случае возвращается значение FALSE.

##  <a name="cdcrendertarget"></a>  CDCRenderTarget::CDCRenderTarget

Создает объект CDCRenderTarget.

```
CDCRenderTarget();
```

##  <a name="create"></a>  CDCRenderTarget::Create

Создает CDCRenderTarget.

```
BOOL Create(const D2D1_RENDER_TARGET_PROPERTIES& props);
```

### <a name="parameters"></a>Параметры

*PROPS*<br/>
Режим отрисовки, формат пикселей, параметры удаленного взаимодействия, сведения о DPI и минимальную поддержку DirectX, необходимые для подготовки к просмотру оборудования.

### <a name="return-value"></a>Возвращаемое значение

Если метод завершается успешно, возвращается значение TRUE. В противном случае возвращается значение FALSE.

##  <a name="detach"></a>  CDCRenderTarget::Detach

Отсоединяет интерфейс целевой объект отрисовки из объекта

```
ID2D1DCRenderTarget* Detach();
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на отсоединенной отображения интерфейса целевой объект.

##  <a name="getdcrendertarget"></a>  CDCRenderTarget::GetDCRenderTarget

Возвращает интерфейс ID2D1DCRenderTarget

```
ID2D1DCRenderTarget* GetDCRenderTarget();
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на интерфейс ID2D1DCRenderTarget или значение NULL, если объект еще не инициализирован.

##  <a name="m_pdcrendertarget"></a>  CDCRenderTarget::m_pDCRenderTarget

Указатель на объект ID2D1DCRenderTarget.

```
ID2D1DCRenderTarget* m_pDCRenderTarget;
```

##  <a name="operator_id2d1dcrendertarget_star"></a>  CDCRenderTarget::operator ID2D1DCRenderTarget *

Возвращает интерфейс ID2D1DCRenderTarget

```
operator ID2D1DCRenderTarget*();
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на интерфейс ID2D1DCRenderTarget или значение NULL, если объект еще не инициализирован.

## <a name="see-also"></a>См. также

[Классы](../../mfc/reference/mfc-classes.md)
