---
title: Класс norm
ms.date: 11/04/2016
f1_keywords:
- norm
- AMP_SHORT_VECTORS/norm
- AMP_SHORT_VECTORS/Concurrency::graphics::norm Constructor
ms.assetid: 73002f3d-c25e-4119-bcd3-4c46c9b6abf1
ms.openlocfilehash: 2d37dcb430be9941444a90ac0a4ba34f3ee30515
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50630767"
---
# <a name="norm-class"></a>Класс norm

Представляет число нормы. Каждый элемент — это число с плавающей запятой в диапазоне [-1, 0f, 1.0f].

## <a name="syntax"></a>Синтаксис

```
class norm;
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[Норма конструктор](#ctor)|Перегружен. Конструктор по умолчанию. Инициализируйте 0, 0f.|

### <a name="public-operators"></a>Открытые операторы

|Имя|Описание|
|----------|-----------------|
|norm::operator-||
|norm::operator--||
|norm::operator число с плавающей запятой|Оператор преобразования. Преобразуйте нормы число с плавающей запятой.|
|norm::operator * =||
|norm::operator / =||
|norm::operator ++||
|norm::operator +=||
|norm::operator =||
|norm::operator-=||

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`norm`

## <a name="requirements"></a>Требования

**Заголовок:** amp_short_vectors.h

**Пространство имен:** Concurrency::graphics

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
