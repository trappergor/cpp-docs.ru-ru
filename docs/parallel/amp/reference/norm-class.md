---
title: Класс norm | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-amp
ms.topic: reference
f1_keywords:
- norm
- AMP_SHORT_VECTORS/norm
- AMP_SHORT_VECTORS/Concurrency::graphics::norm Constructor
dev_langs:
- C++
ms.assetid: 73002f3d-c25e-4119-bcd3-4c46c9b6abf1
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 362ad3a2676fa1a7c8f965a6750782617d6a3203
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46425734"
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
