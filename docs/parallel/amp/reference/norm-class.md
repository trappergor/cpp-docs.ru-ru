---
title: Класс norm
ms.date: 11/04/2016
f1_keywords:
- norm
- AMP_SHORT_VECTORS/norm
- AMP_SHORT_VECTORS/Concurrency::graphics::norm Constructor
ms.assetid: 73002f3d-c25e-4119-bcd3-4c46c9b6abf1
ms.openlocfilehash: 56f879ef2fc0d3010ab4f64fedaf2570dac565d1
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62351567"
---
# <a name="norm-class"></a>Класс norm

Представляет число нормы. Каждый элемент — это число с плавающей запятой в диапазоне [-1, 0f, 1.0f].

## <a name="syntax"></a>Синтаксис

```
class norm;
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|name|Описание|
|----------|-----------------|
|[Норма конструктор](#ctor)|Перегружен. Конструктор по умолчанию. Инициализируйте 0, 0f.|

### <a name="public-operators"></a>Открытые операторы

|name|Описание|
|----------|-----------------|
|norm::operator-||
|norm::operator--||
|norm::operator число с плавающей запятой|Оператор преобразования. Преобразуйте нормы число с плавающей запятой.|
|norm::operator*=||
|norm::operator / =||
|norm::operator ++||
|norm::operator +=||
|norm::operator =||
|norm::operator-=||

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`norm`

## <a name="requirements"></a>Требования

**Заголовок:** amp_short_vectors.h

**Пространство имен:** Concurrency::Graphics

##  <a name="ctor"></a> Норма

Конструктор по умолчанию. Инициализируйте 0, 0f.

```
norm(
    void) restrict(amp,
    cpu);

explicit norm(
    float _V) restrict(amp,
    cpu);

explicit norm(
    unsigned int _V) restrict(amp,
    cpu);

explicit norm(
    int _V) restrict(amp,
    cpu);

explicit norm(
    double _V) restrict(amp,
    cpu);

norm(
    const norm& _Other) restrict(amp,
    cpu);

norm(
    const unorm& _Other) restrict(amp,
    cpu);
```

### <a name="parameters"></a>Параметры

*_V*<br/>
Значение, используемое для инициализации.

*_Другое*<br/>
Объект, используемый для инициализации.

## <a name="see-also"></a>См. также

[Пространство имен Concurrency::graphics](concurrency-graphics-namespace.md)
