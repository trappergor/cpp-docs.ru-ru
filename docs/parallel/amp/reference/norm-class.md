---
title: Класс norm
ms.date: 11/04/2016
f1_keywords:
- norm
- AMP_SHORT_VECTORS/norm
- AMP_SHORT_VECTORS/Concurrency::graphics::norm Constructor
ms.assetid: 73002f3d-c25e-4119-bcd3-4c46c9b6abf1
ms.openlocfilehash: 272ac3685539eb03f773c8bc60d5938ed6c53876
ms.sourcegitcommit: a8ef52ff4a4944a1a257bdaba1a3331607fb8d0f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/11/2020
ms.locfileid: "77126517"
---
# <a name="norm-class"></a>Класс norm

Представляет значение нормы. Каждый элемент является числом с плавающей запятой в диапазоне [-1.0 f, 1.0 f].

## <a name="syntax"></a>Синтаксис

```cpp
class norm;
```

## <a name="members"></a>Члены

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Description|
|----------|-----------------|
|[норма, конструктор](#ctor)|Перегружен. Конструктор по умолчанию. Инициализируйте до 0,0 f.|

### <a name="public-operators"></a>Открытые операторы

|Имя|Description|
|----------|-----------------|
|норма:: operator-||
|норма:: operator--||
|норма:: оператор float|Оператор преобразования. Преобразуйте нормативное число в значение с плавающей запятой.|
|норма:: operator * =||
|норма:: оператор/=||
|норма:: operator + +||
|норма:: operator + =||
|норма:: оператор =||
|норма:: operator-=||

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`norm`

## <a name="requirements"></a>Требования

**Заголовок:** amp_short_vectors. h

**Пространство имен:** Concurrency:: Graphics

## <a name="ctor"></a>норма

Конструктор по умолчанию. Инициализируйте до 0,0 f.

```cpp
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

*_Other*<br/>
Объект, используемый для инициализации.

## <a name="see-also"></a>См. также раздел

[Пространство имен Concurrency::graphics](concurrency-graphics-namespace.md)
