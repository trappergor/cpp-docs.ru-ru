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
ms.openlocfilehash: a5b87fe2ddd8fb32ddbbb2884c630952afdb079c
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81359292"
---
# <a name="cd2dsizeu-class"></a>Класс CD2DSizeU

Обертка для D2D1_SIZE_U.

## <a name="syntax"></a>Синтаксис

```
class CD2DSizeU : public D2D1_SIZE_U;
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CD2DSizeU:CD2DSizeU](#cd2dsizeu)|Перегружен. Строит `CD2DSizeU` объект из `D2D1_SIZE_U` объекта.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CD2DSizeU::Isnull](#isnull)|Возвращает значение **boolean,** которое указывает, не содержит ли выражение действительных данных (NULL).|

### <a name="public-operators"></a>Открытые операторы

|Имя|Описание|
|----------|-----------------|
|[CD2DSizeU:оператор CSize](#operator_csize)|`CD2DSizeU` Преобразуется `CSize` в объект.|

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`D2D1_SIZE_U`

[CD2DSizeU](../../mfc/reference/cd2dsizeu-class.md)

## <a name="requirements"></a>Требования

**Заголовок:** afxrendertarget.h

## <a name="cd2dsizeucd2dsizeu"></a><a name="cd2dsizeu"></a>CD2DSizeU:CD2DSizeU

Строит объект CD2DSizeU из объекта CSize.

```
CD2DSizeU(const CSize& size);
CD2DSizeU(const D2D1_SIZE_U& size);
CD2DSizeU(const D2D1_SIZE_U* size);

CD2DSizeU(
    UINT32 cx = 0,
    UINT32 cy = 0);
```

### <a name="parameters"></a>Параметры

*Размер*<br/>
размер источника

*Cx*<br/>
ширина источника

*Cy*<br/>
высота источника

## <a name="cd2dsizeuisnull"></a><a name="isnull"></a>CD2DSizeU::Isnull

Возвращает значение Boolean, которое указывает, не содержит ли выражение действительных данных (Null).

```
BOOL IsNull() const;
```

### <a name="return-value"></a>Возвращаемое значение

ПРАВДА, если ширина и высота пусты; в противном случае FALSE.

## <a name="cd2dsizeuoperator-csize"></a><a name="operator_csize"></a>CD2DSizeU:оператор CSize

Преобразует CD2DSizeU в объект CSize.

```
operator CSize();
```

### <a name="return-value"></a>Возвращаемое значение

Текущее значение размера D2D.

## <a name="see-also"></a>См. также раздел

[Классы](../../mfc/reference/mfc-classes.md)
