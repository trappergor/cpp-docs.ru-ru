---
title: Класс unorm
ms.date: 11/04/2016
f1_keywords:
- unorm
- AMP_SHORT_VECTORS/unorm
- AMP_SHORT_VECTORS/Concurrency::graphics::unorm Constructor
ms.assetid: bc30bd20-6452-4d5f-9158-3b11c4c16ed2
ms.openlocfilehash: 059cd3a388d67e540a91146f2a287c375fb02bd1
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/04/2019
ms.locfileid: "57300808"
---
# <a name="unorm-class"></a>Класс unorm

Представляет число unorm. Каждый элемент — это число с плавающей запятой в диапазоне [0, 0f, 1.0f].

## <a name="syntax"></a>Синтаксис

```
class unorm;
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[Конструктор unorm](#ctor)|Перегружен. Конструктор по умолчанию. Инициализируйте 0, 0f.|

### <a name="public-operators"></a>Открытые операторы

|Имя|Описание|
|----------|-----------------|
|unorm::operator--||
|unorm::operator число с плавающей запятой|Оператор преобразования. Преобразуйте unorm число с плавающей запятой.|
|unorm::operator*=||
|unorm::operator/=||
|unorm::operator ++||
|unorm::operator +=||
|unorm::operator =||
|unorm::operator-=||

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`unorm`

## <a name="requirements"></a>Требования

**Заголовок:** amp_short_vectors.h

**Пространство имен:** Concurrency::Graphics

##  <a name="ctor"></a> unorm

Конструктор по умолчанию. Инициализируйте 0, 0f.

```
unorm(
    void) restrict(amp,
    cpu);

explicit unorm(
    float _V) restrict(amp,
    cpu);

explicit unorm(
    unsigned int _V) restrict(amp,
    cpu);

explicit unorm(
    int _V) restrict(amp,
    cpu);

explicit unorm(
    double _V) restrict(amp,
    cpu);

unorm(
    const unorm& _Other) restrict(amp,
    cpu);

inline explicit unorm(
    const norm& _Other) restrict(amp,
    cpu);
```

### <a name="parameters"></a>Параметры

*_V*<br/>
Значение, используемое для инициализации.

*_Другое*<br/>
Норма объект, используемый для инициализации.

## <a name="see-also"></a>См. также

[Пространство имен Concurrency::graphics](concurrency-graphics-namespace.md)
