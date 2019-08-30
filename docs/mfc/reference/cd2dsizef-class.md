---
title: Класс CD2DSizeF
ms.date: 08/29/2019
f1_keywords:
- CD2DSizeF
- AFXRENDERTARGET/CD2DSizeF
- AFXRENDERTARGET/CD2DSizeF::CD2DSizeF
- AFXRENDERTARGET/CD2DSizeF::IsNull
helpviewer_keywords:
- CD2DSizeF [MFC], CD2DSizeF
- CD2DSizeF [MFC], IsNull
ms.assetid: f486a1e1-997d-4286-8cb9-26369dc82055
ms.openlocfilehash: df895c278003e2c71f37a00af6bf14912756701a
ms.sourcegitcommit: e10a5feea193c249ddc5a6faba48e7c6d8784e73
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/30/2019
ms.locfileid: "70177197"
---
# <a name="cd2dsizef-class"></a>Класс CD2DSizeF

Оболочка для D2D1_SIZE_F.

## <a name="syntax"></a>Синтаксис

```
class CD2DSizeF : public D2D1_SIZE_F;
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|name|Описание|
|----------|-----------------|
|[CD2DSizeF:: CD2DSizeF](#cd2dsizef)|Перегружен. Конструирует объект из `D2D1_SIZE_F`объекта. `CD2DSizeF`|

### <a name="public-methods"></a>Открытые методы

|name|Описание|
|----------|-----------------|
|[CD2DSizeF:: IsNull](#isnull)|Возвращает **логическое** значение, указывающее, содержит ли выражение допустимые данные (null).|

### <a name="public-operators"></a>Открытые операторы

|name|Описание|
|----------|-----------------|
|[CD2DSizeF:: operator Ксизе](#operator_csize)|Преобразует `CD2DSizeF` в`CSize` объект.|

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`D2D1_SIZE_F`

[CD2DSizeF](../../mfc/reference/cd2dsizef-class.md)

## <a name="requirements"></a>Требования

**Заголовок:** афксрендертаржет. h

##  <a name="cd2dsizef"></a>CD2DSizeF:: CD2DSizeF

Конструирует объект CD2DSizeF из объекта Ксизе.

```
CD2DSizeF(const CSize& size);
CD2DSizeF(const D2D1_SIZE_F& size);
CD2DSizeF(const D2D1_SIZE_F* size);

CD2DSizeF(
    FLOAT cx = 0.,
    FLOAT cy = 0.);
```

### <a name="parameters"></a>Параметры

*size*<br/>
Размер источника

*cx*<br/>
ширина источника

*CY*<br/>
высота источника

##  <a name="isnull"></a>CD2DSizeF:: IsNull

Возвращает логическое значение, указывающее, содержит ли выражение допустимые данные (null).

```
BOOL IsNull() const;
```

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если ширина и высота пусты; в противном случае — FALSE.

##  <a name="operator_csize"></a>CD2DSizeF:: operator Ксизе

Преобразует CD2DSizeF в объект Ксизе.

```
operator CSize();
```

### <a name="return-value"></a>Возвращаемое значение

Текущее значение размера D2D.

## <a name="see-also"></a>См. также

[Классы](../../mfc/reference/mfc-classes.md)
