---
title: Класс CD2DSizeU
ms.date: 08/29/2019
f1_keywords:
- CD2DSizeU
- AFXRENDERTARGET/CD2DSizeU
- AFXRENDERTARGET/CD2DSizeU::CD2DSizeU
- AFXRENDERTARGET/CD2DSizeU::IsNull
helpviewer_keywords:
- CD2DSizeU [MFC], CD2DSizeU
- CD2DSizeU [MFC], IsNull
ms.assetid: 6e679ba8-2112-43c3-8275-70b660856f02
ms.openlocfilehash: 45625331d0c1be8ca7c663d12c53516dc7bd77c7
ms.sourcegitcommit: e10a5feea193c249ddc5a6faba48e7c6d8784e73
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/30/2019
ms.locfileid: "70177184"
---
# <a name="cd2dsizeu-class"></a>Класс CD2DSizeU

Оболочка для D2D1_SIZE_U.

## <a name="syntax"></a>Синтаксис

```
class CD2DSizeU : public D2D1_SIZE_U;
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|name|Описание|
|----------|-----------------|
|[CD2DSizeU::CD2DSizeU](#cd2dsizeu)|Перегружен. Конструирует объект из `D2D1_SIZE_U`объекта. `CD2DSizeU`|

### <a name="public-methods"></a>Открытые методы

|name|Описание|
|----------|-----------------|
|[CD2DSizeU:: IsNull](#isnull)|Возвращает **логическое** значение, указывающее, содержит ли выражение допустимые данные (null).|

### <a name="public-operators"></a>Открытые операторы

|name|Описание|
|----------|-----------------|
|[CD2DSizeU:: operator Ксизе](#operator_csize)|Преобразует `CD2DSizeU` в`CSize` объект.|

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`D2D1_SIZE_U`

[CD2DSizeU](../../mfc/reference/cd2dsizeu-class.md)

## <a name="requirements"></a>Требования

**Заголовок:** афксрендертаржет. h

##  <a name="cd2dsizeu"></a>CD2DSizeU::CD2DSizeU

Конструирует объект CD2DSizeU из объекта Ксизе.

```
CD2DSizeU(const CSize& size);
CD2DSizeU(const D2D1_SIZE_U& size);
CD2DSizeU(const D2D1_SIZE_U* size);

CD2DSizeU(
    UINT32 cx = 0,
    UINT32 cy = 0);
```

### <a name="parameters"></a>Параметры

*size*<br/>
Размер источника

*cx*<br/>
ширина источника

*CY*<br/>
высота источника

##  <a name="isnull"></a>CD2DSizeU:: IsNull

Возвращает логическое значение, указывающее, содержит ли выражение допустимые данные (null).

```
BOOL IsNull() const;
```

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если ширина и высота пусты; в противном случае — FALSE.

##  <a name="operator_csize"></a>CD2DSizeU:: operator Ксизе

Преобразует CD2DSizeU в объект Ксизе.

```
operator CSize();
```

### <a name="return-value"></a>Возвращаемое значение

Текущее значение размера D2D.

## <a name="see-also"></a>См. также

[Классы](../../mfc/reference/mfc-classes.md)
