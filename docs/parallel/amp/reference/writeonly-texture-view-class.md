---
title: Класс writeonly_texture_view
ms.date: 11/04/2016
f1_keywords:
- writeonly_texture_view
- AMP_GRAPHICS/writeonly_texture_view
- AMP_GRAPHICS/Concurrency::graphics::writeonly_texture_view
- AMP_GRAPHICS/Concurrency::graphics::writeonly_texture_view::set
- AMP_GRAPHICS/Concurrency::graphics::rank Constant
ms.assetid: 8d117ad3-0a1c-41ae-b29c-7c95fdd4d04d
ms.openlocfilehash: 022450469a69e9fe127f23a50b799092e7e057b4
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50524698"
---
# <a name="writeonlytextureview-class"></a>Класс writeonly_texture_view

Предоставляет доступ к текстуре.

## <a name="syntax"></a>Синтаксис

```
template <
    typename value_type,
    int _Rank
>
class writeonly_texture_view;

template <
    typename value_type,
    int _Rank
>
class writeonly_texture_view<value_type, _Rank> : public details::_Texture_base<value_type, _Rank>;
```

#### <a name="parameters"></a>Параметры

*value_type*<br/>
Тип элементов в текстуре.

*_Rank*<br/>
Ранг текстуры.

## <a name="members"></a>Участники

### <a name="public-typedefs"></a>Общедоступные определения типов

|Имя|Описание|
|----------|-----------------|
|`scalar_type`||
|`value_type`|Тип элементов в текстуре.|

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[Конструктор writeonly_texture_view](#ctor)|Инициализирует новый экземпляр класса `writeonly_texture_view`.|
|[~ writeonly_texture_view деструктор](#ctor)|Уничтожает `writeonly_texture_view` объекта.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[set](#set)|Задает значение элемента по указанному индексу.|

### <a name="public-operators"></a>Открытые операторы

|Имя|Описание|
|----------|-----------------|
|[оператор=](#operator_eq)|Копирует указанный `writeonly_texture_view` в данный объект.|

### <a name="public-constants"></a>Открытые константы

|name|Описание|
|----------|-----------------|
|[Ранг константа](#rank)|Получает ранг объекта `writeonly_texture_view` объекта.|

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`_Texture_base`

`writeonly_texture_view`

## <a name="requirements"></a>Требования

**Заголовок:** amp_graphics.h

**Пространство имен:** Concurrency::graphics

##  <a name="dtor"></a> ~ writeonly_texture_view

Уничтожает `writeonly_texture_view` объекта.

```
~writeonly_texture_view() restrict(amp,cpu);
```

##  <a name="operator_eq"></a> оператор =

Копирует указанный `writeonly_texture_view` в данный объект.

```
writeonly_texture_view<value_type, _Rank>& operator= (
    const writeonly_texture_view<value_type, _Rank>& _Other) restrict(amp,cpu);
```

### <a name="parameters"></a>Параметры

*_Другое*<br/>
`writeonly_texture_view` объект для копирования из.

### <a name="return-value"></a>Возвращаемое значение

Ссылка на этот `writeonly_texture_view` объекта.

##  <a name="rank"></a> Ранг

Получает ранг объекта `writeonly_texture_view` объекта.

```
static const int rank = _Rank;
```

##  <a name="set"></a> Набор

Задает значение элемента по указанному индексу.

```
void set(
    const index<_Rank>& _Index,
    const value_type& value) const restrict(amp);
```

### <a name="parameters"></a>Параметры

*_Index*<br/>
Индекс элемента.

*значение*<br/>
Новое значение элемента.

##  <a name="ctor"></a> writeonly_texture_view

Инициализирует новый экземпляр класса `writeonly_texture_view`.

```
writeonly_texture_view(
    texture<value_type,
    _Rank>& _Src) restrict(amp);

writeonly_texture_view(
    const writeonly_texture_view<value_type,
    _Rank>& _Src) restrict(amp,cpu);
```

### <a name="parameters"></a>Параметры

*_Rank*<br/>
Ранг текстуры.

*value_type*<br/>
Тип элементов в текстуре.

*_Src*<br/>
Текстуры, который используется для создания `writeonly_texture_view`.

## <a name="see-also"></a>См. также

[Пространство имен Concurrency::graphics](concurrency-graphics-namespace.md)
