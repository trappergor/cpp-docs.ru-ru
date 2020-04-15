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
ms.openlocfilehash: be050f98855e5af794166e1f86962111a23bfa2e
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81369066"
---
# <a name="cd2dsizef-class"></a>Класс CD2DSizeF

Обертка для D2D1_SIZE_F.

## <a name="syntax"></a>Синтаксис

```
class CD2DSizeF : public D2D1_SIZE_F;
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CD2DSizeF::CD2DSizeF](#cd2dsizef)|Перегружен. Строит `CD2DSizeF` объект из `D2D1_SIZE_F` объекта.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CD2DSizeF::Isnull](#isnull)|Возвращает значение **boolean,** которое указывает, не содержит ли выражение действительных данных (NULL).|

### <a name="public-operators"></a>Открытые операторы

|Имя|Описание|
|----------|-----------------|
|[CD2DSizeF:оператор CSize](#operator_csize)|`CD2DSizeF` Преобразуется `CSize` в объект.|

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`D2D1_SIZE_F`

[CD2DSizeF](../../mfc/reference/cd2dsizef-class.md)

## <a name="requirements"></a>Требования

**Заголовок:** afxrendertarget.h

## <a name="cd2dsizefcd2dsizef"></a><a name="cd2dsizef"></a>CD2DSizeF::CD2DSizeF

Строит объект CD2DSizeF из объекта CSize.

```
CD2DSizeF(const CSize& size);
CD2DSizeF(const D2D1_SIZE_F& size);
CD2DSizeF(const D2D1_SIZE_F* size);

CD2DSizeF(
    FLOAT cx = 0.,
    FLOAT cy = 0.);
```

### <a name="parameters"></a>Параметры

*Размер*<br/>
размер источника

*Cx*<br/>
ширина источника

*Cy*<br/>
высота источника

## <a name="cd2dsizefisnull"></a><a name="isnull"></a>CD2DSizeF::Isnull

Возвращает значение Boolean, которое указывает, не содержит ли выражение действительных данных (Null).

```
BOOL IsNull() const;
```

### <a name="return-value"></a>Возвращаемое значение

ПРАВДА, если ширина и высота пусты; в противном случае FALSE.

## <a name="cd2dsizefoperator-csize"></a><a name="operator_csize"></a>CD2DSizeF:оператор CSize

Преобразует CD2DSizeF в объект CSize.

```
operator CSize();
```

### <a name="return-value"></a>Возвращаемое значение

Текущее значение размера D2D.

## <a name="see-also"></a>См. также раздел

[Классы](../../mfc/reference/mfc-classes.md)
