---
title: Класс CD2DSizeF
ms.date: 11/04/2016
f1_keywords:
- CD2DSizeF
- AFXRENDERTARGET/CD2DSizeF
- AFXRENDERTARGET/CD2DSizeF::CD2DSizeF
- AFXRENDERTARGET/CD2DSizeF::IsNull
helpviewer_keywords:
- CD2DSizeF [MFC], CD2DSizeF
- CD2DSizeF [MFC], IsNull
ms.assetid: f486a1e1-997d-4286-8cb9-26369dc82055
ms.openlocfilehash: 09ccd8c4ba6bb0c345adb32bcf22686c485d1184
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/04/2019
ms.locfileid: "57296596"
---
# <a name="cd2dsizef-class"></a>Класс CD2DSizeF

Оболочка для D2D1_SIZE_F.

## <a name="syntax"></a>Синтаксис

```
class CD2DSizeF : public D2D1_SIZE_F;
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание:|
|----------|-----------------|
|[CD2DSizeF::CD2DSizeF](#cd2dsizef)|Перегружен. Создает `CD2DSizeF` объекта из `D2D1_SIZE_F` объекта.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание:|
|----------|-----------------|
|[CD2DSizeF::IsNull](#isnull)|Возвращает **логическое** значение, указывающее, является ли выражение содержит недопустимые данные (NULL).|

### <a name="public-operators"></a>Открытые операторы

|Имя|Описание|
|----------|-----------------|
|[CD2DSizeF::operator CSize](#operator_csize)|Преобразует `CD2DSizeF` для `CSize` объекта.|

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`D2D1_SIZE_F`

[CD2DSizeF](../../mfc/reference/cd2dsizef-class.md)

## <a name="requirements"></a>Требования

**Заголовок:** afxrendertarget.h

##  <a name="cd2dsizef"></a>  CD2DSizeF::CD2DSizeF

Создает объект CD2DSizeF из CSize объекта.

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
исходная ширина

*CY*<br/>
Исходная высота

##  <a name="isnull"></a>  CD2DSizeF::IsNull

Возвращает логическое значение, указывающее, является ли выражение содержит недопустимые данные (Null).

```
BOOL IsNull() const;
```

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если ширина и высота являются пустыми; в противном случае — значение FALSE.

##  <a name="operator_csize"></a>  CD2DSizeF::operator CSize

Преобразует CD2DSizeF CSize.

```
operator CSize();
```

### <a name="return-value"></a>Возвращаемое значение

Текущее значение размера D2D.

## <a name="see-also"></a>См. также

[Классы](../../mfc/reference/mfc-classes.md)
