---
title: Класс Крбтри
ms.date: 11/04/2016
f1_keywords:
- CRBTree
- ATLCOLL/ATL::CRBTree
- ATLCOLL/ATL::CRBTree::KINARGTYPE
- ATLCOLL/ATL::CRBTree::KOUTARGTYPE
- ATLCOLL/ATL::CRBTree::VINARGTYPE
- ATLCOLL/ATL::CRBTree::VOUTARGTYPE
- ATLCOLL/ATL::CRBTree::FindFirstKeyAfter
- ATLCOLL/ATL::CRBTree::GetAt
- ATLCOLL/ATL::CRBTree::GetCount
- ATLCOLL/ATL::CRBTree::GetHeadPosition
- ATLCOLL/ATL::CRBTree::GetKeyAt
- ATLCOLL/ATL::CRBTree::GetNext
- ATLCOLL/ATL::CRBTree::GetNextAssoc
- ATLCOLL/ATL::CRBTree::GetNextKey
- ATLCOLL/ATL::CRBTree::GetNextValue
- ATLCOLL/ATL::CRBTree::GetPrev
- ATLCOLL/ATL::CRBTree::GetTailPosition
- ATLCOLL/ATL::CRBTree::GetValueAt
- ATLCOLL/ATL::CRBTree::IsEmpty
- ATLCOLL/ATL::CRBTree::RemoveAll
- ATLCOLL/ATL::CRBTree::RemoveAt
- ATLCOLL/ATL::CRBTree::SetValueAt
helpviewer_keywords:
- CRBTree class
ms.assetid: a1b1cb63-38e4-4fc2-bb28-f774d1721760
ms.openlocfilehash: 7b8e47b5cd0ac278711947abc867956333371be3
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/25/2020
ms.locfileid: "88833495"
---
# <a name="crbtree-class"></a>Класс Крбтри

Этот класс предоставляет методы для создания и использования дерева с красным и черным цветами.

## <a name="syntax"></a>Синтаксис

```
template <typename K,
          typename V,
          class KTraits = CElementTraits<K>,
          class VTraits = CElementTraits<V>>
class CRBTree
```

#### <a name="parameters"></a>Параметры

*Занят*<br/>
Тип элемента Key.

*3,3*<br/>
Тип элемента value.

*ктраитс*<br/>
Код, используемый для копирования или перемещения элементов ключа. Дополнительные сведения см. в разделе [класс целементтраитс](../../atl/reference/celementtraits-class.md) .

*втраитс*<br/>
Код, используемый для копирования или перемещения элементов значений.

## <a name="members"></a>Элементы

### <a name="public-typedefs"></a>Общедоступные определения типов

|Имя|Описание|
|----------|-----------------|
|[Крбтри:: КИНАРГТИПЕ](#kinargtype)|Тип, используемый при передаче ключа в качестве входного аргумента.|
|[Крбтри:: КАУТАРГТИПЕ](#koutargtype)|Тип, используемый при возврате ключа в качестве выходного аргумента.|
|[Крбтри:: ВИНАРГТИПЕ](#vinargtype)|Тип, используемый при передаче значения в качестве входного аргумента.|
|[Крбтри:: ВАУТАРГТИПЕ](#voutargtype)|Тип, используемый при передаче значения в качестве выходного аргумента.|

### <a name="public-classes"></a>Открытые классы

|Имя|Описание|
|----------|-----------------|
|[Класс Крбтри:: Кпаир](#cpair_class)|Класс, содержащий элементы Key и value.|

### <a name="public-constructors"></a>Открытые конструкторы

|name|Описание|
|----------|-----------------|
|[Крбтри:: ~ Крбтри](#dtor)|Деструктор|

### <a name="public-methods"></a>Открытые методы

|name|Описание|
|----------|-----------------|
|[Крбтри:: Финдфирсткэйафтер](#findfirstkeyafter)|Вызовите этот метод, чтобы найти расположение элемента, который использует следующий доступный ключ.|
|[Крбтри:: GetAt](#getat)|Вызовите этот метод, чтобы получить элемент в заданной позиции в дереве.|
|[Крбтри:: NOCOUNT](#getcount)|Вызовите этот метод, чтобы получить количество элементов в дереве.|
|[Крбтри:: Жесеадпоситион](#getheadposition)|Вызовите этот метод, чтобы получить значение позиции для элемента в заголовке дерева.|
|[Крбтри:: Жеткэйат](#getkeyat)|Вызовите этот метод, чтобы получить ключ из заданной позицией в дереве.|
|[Крбтри:: GetNext](#getnext)|Вызовите этот метод, чтобы получить указатель на элемент, хранящийся в `CRBTree` объекте, и переместить его на следующий элемент.|
|[Крбтри:: Жетнекстассок](#getnextassoc)|Вызовите этот метод, чтобы получить ключ и значение элемента, хранящегося на карте, и переместить его на следующий элемент.|
|[Крбтри:: Жетнексткэй](#getnextkey)|Вызовите этот метод, чтобы получить ключ элемента, хранящегося в дереве, и переместить его на следующий элемент.|
|[Крбтри:: Жетнекствалуе](#getnextvalue)|Вызовите этот метод, чтобы получить значение элемента, хранящегося в дереве, и переместить его на следующий элемент.|
|[Крбтри:: prev](#getprev)|Вызовите этот метод, чтобы получить указатель на элемент, хранящийся в `CRBTree` объекте, а затем обновить расположение до предыдущего элемента.|
|[Крбтри:: Жеттаилпоситион](#gettailposition)|Вызовите этот метод, чтобы получить значение позиции для элемента в хвосте дерева.|
|[Крбтри:: Жетвалуеат](#getvalueat)|Вызовите этот метод, чтобы получить значение, хранящееся в заданной позиции в `CRBTree` объекте.|
|[Крбтри:: IsEmpty](#isempty)|Вызовите этот метод, чтобы проверить наличие пустого объекта Tree.|
|[Крбтри:: RemoveAll](#removeall)|Вызовите этот метод, чтобы удалить все элементы из `CRBTree` объекта.|
|[Крбтри:: RemoveAt](#removeat)|Вызовите этот метод, чтобы удалить элемент в заданной позиции в `CRBTree` объекте.|
|[Крбтри:: Сетвалуеат](#setvalueat)|Вызовите этот метод, чтобы изменить значение, хранящееся в заданной позиции в `CRBTree` объекте.|

## <a name="remarks"></a>Remarks

Черно-Черное дерево — это двоичное дерево поиска, которое использует дополнительные сведения для каждого узла, чтобы убедиться, что он остается сбалансированным, т. е. высота дерева не слишком велика и влияет на производительность.

Этот класс шаблона предназначен для использования в [крбмап](../../atl/reference/crbmap-class.md) и [крбмултимап](../../atl/reference/crbmultimap-class.md). Основная часть методов, составляющих эти производные классы, предоставляется `CRBTree` .

Более подробное обсуждение различных классов коллекций, их функций и характеристик производительности см. в разделе [классы коллекций ATL](../../atl/atl-collection-classes.md).

## <a name="requirements"></a>Требования

**Заголовок:** атлколл. h

## <a name="crbtreecpair-class"></a><a name="cpair_class"></a> Класс Крбтри:: Кпаир

Класс, содержащий элементы Key и value.

```
class CPair : public __POSITION
```

### <a name="remarks"></a>Remarks

Этот класс используется методами [крбтри:: GetAt](#getat), [Крбтри:: GetNext](#getnext)и [крбтри:: prev](#getprev) для доступа к элементам Key и value, хранящимся в древовидной структуре.

Ниже приведены элементы.

|Элемент данных|Описание|
|-|-|
|`m_key`|Элемент данных, в котором хранится элемент key.|
|`m_value`|Элемент данных, в котором хранится элемент value.|

## <a name="crbtreecrbtree"></a><a name="dtor"></a> Крбтри:: ~ Крбтри

Деструктор

```
~CRBTree() throw();
```

### <a name="remarks"></a>Remarks

Освобождает все выделенные ресурсы. Вызывает [крбтри:: RemoveAll](#removeall) для удаления всех элементов.

## <a name="crbtreefindfirstkeyafter"></a><a name="findfirstkeyafter"></a> Крбтри:: Финдфирсткэйафтер

Вызовите этот метод, чтобы найти расположение элемента, который использует следующий доступный ключ.

```
POSITION FindFirstKeyAfter(KINARGTYPE key) const throw();
```

### <a name="parameters"></a>Параметры

*key*<br/>
Значение ключа.

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение расположения элемента, использующего следующий доступный ключ. Если больше нет элементов, возвращается значение NULL.

### <a name="remarks"></a>Remarks

Этот метод упрощает обход дерева без необходимости заранее рассчитывать значения позиций.

## <a name="crbtreegetat"></a><a name="getat"></a> Крбтри:: GetAt

Вызовите этот метод, чтобы получить элемент в заданной позиции в дереве.

```
CPair* GetAt(POSITION pos) throw();
const CPair* GetAt(POSITION pos) const throw();
void GetAt(POSITION pos, KOUTARGTYPE key, VOUTARGTYPE value) const;
```

### <a name="parameters"></a>Параметры

*pos*<br/>
Позиция.

*key*<br/>
Переменная, которая получает ключ.

*value*<br/>
Переменная, которая получает значение.

### <a name="return-value"></a>Возвращаемое значение

Первые две формы возвращают указатель на [кпаир](#cpair_class). Третья форма получает ключ и значение для заданной должности.

### <a name="remarks"></a>Remarks

Значение расположения можно определить ранее с помощью вызова метода, например [крбтри:: жесеадпоситион](#getheadposition) или [Крбтри:: жеттаилпоситион](#gettailposition).

В отладочных сборках произойдет сбой утверждения, если *POS* равен null.

## <a name="crbtreegetcount"></a><a name="getcount"></a> Крбтри:: NOCOUNT

Вызовите этот метод, чтобы получить количество элементов в дереве.

```
size_t GetCount() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает количество элементов (каждая пара «ключ-значение» — это один элемент), хранящийся в дереве.

## <a name="crbtreegetheadposition"></a><a name="getheadposition"></a> Крбтри:: Жесеадпоситион

Вызовите этот метод, чтобы получить значение позиции для элемента в заголовке дерева.

```
POSITION GetHeadPosition() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение позиции для элемента в заголовке дерева.

### <a name="remarks"></a>Remarks

Значение, возвращаемое, `GetHeadPosition` можно использовать с такими методами, как [крбтри:: Жеткэйат](#getkeyat) или [крбтри:: GetNext](#getnext) , для прохода по дереву и получения значений.

## <a name="crbtreegetkeyat"></a><a name="getkeyat"></a> Крбтри:: Жеткэйат

Вызовите этот метод, чтобы получить ключ из заданной позицией в дереве.

```
const K& GetKeyAt(POSITION pos) const throw();
```

### <a name="parameters"></a>Параметры

*pos*<br/>
Позиция.

### <a name="return-value"></a>Возвращаемое значение

Возвращает ключ, хранящийся в позиции *POS* в дереве.

### <a name="remarks"></a>Remarks

Если *POS* не является допустимым значением координаты, результаты будут непредсказуемыми. В отладочных сборках произойдет сбой утверждения, если *POS* равен null.

## <a name="crbtreegetnext"></a><a name="getnext"></a> Крбтри:: GetNext

Вызовите этот метод, чтобы получить указатель на элемент, хранящийся в `CRBTree` объекте, и переместить его на следующий элемент.

```
const CPair* GetNext(POSITION& pos) const throw();
CPair* GetNext(POSITION& pos) throw();
```

### <a name="parameters"></a>Параметры

*pos*<br/>
Счетчик позиций, возвращенный предыдущим вызовом методов, таких как [крбтри:: жесеадпоситион](#getheadposition) или [Крбтри:: финдфирсткэйафтер](#findfirstkeyafter).

### <a name="return-value"></a>Возвращаемое значение

Возвращает указатель на следующее значение [кпаир](#cpair_class) в дереве.

### <a name="remarks"></a>Remarks

Счетчик "положение *POS* " обновляется после каждого вызова. Если извлеченный элемент является последним в дереве, *POS* имеет значение null.

## <a name="crbtreegetnextassoc"></a><a name="getnextassoc"></a> Крбтри:: Жетнекстассок

Вызовите этот метод, чтобы получить ключ и значение элемента, хранящегося на карте, и переместить его на следующий элемент.

```cpp
void GetNextAssoc(
    POSITION& pos,
    KOUTARGTYPE key,
    VOUTARGTYPE value) const;
```

### <a name="parameters"></a>Параметры

*pos*<br/>
Счетчик позиций, возвращенный предыдущим вызовом методов, таких как [крбтри:: жесеадпоситион](#getheadposition) или [Крбтри:: финдфирсткэйафтер](#findfirstkeyafter).

*key*<br/>
Параметр шаблона, указывающий тип ключа дерева.

*value*<br/>
Параметр шаблона, указывающий тип значения дерева.

### <a name="remarks"></a>Remarks

Счетчик "положение *POS* " обновляется после каждого вызова. Если извлеченный элемент является последним в дереве, *POS* имеет значение null.

## <a name="crbtreegetnextkey"></a><a name="getnextkey"></a> Крбтри:: Жетнексткэй

Вызовите этот метод, чтобы получить ключ элемента, хранящегося в дереве, и переместить его на следующий элемент.

```
const K& GetNextKey(POSITION& pos) const throw();
```

### <a name="parameters"></a>Параметры

*pos*<br/>
Счетчик позиций, возвращенный предыдущим вызовом методов, таких как [крбтри:: жесеадпоситион](#getheadposition) или [Крбтри:: финдфирсткэйафтер](#findfirstkeyafter).

### <a name="return-value"></a>Возвращаемое значение

Возвращает ссылку на следующий ключ в дереве.

### <a name="remarks"></a>Remarks

Обновляет текущий счетчик позиций, *POS*. Если в дереве больше нет записей, счетчику позиции присваивается значение NULL.

## <a name="crbtreegetnextvalue"></a><a name="getnextvalue"></a> Крбтри:: Жетнекствалуе

Вызовите этот метод, чтобы получить значение элемента, хранящегося в дереве, и переместить его на следующий элемент.

```
const V& GetNextValue(POSITION& pos) const throw();
V& GetNextValue(POSITION& pos) throw();
```

### <a name="parameters"></a>Параметры

*pos*<br/>
Счетчик позиций, возвращенный предыдущим вызовом методов, таких как [крбтри:: жесеадпоситион](#getheadposition) или [Крбтри:: финдфирсткэйафтер](#findfirstkeyafter).

### <a name="return-value"></a>Возвращаемое значение

Возвращает ссылку на следующее значение в дереве.

### <a name="remarks"></a>Remarks

Обновляет текущий счетчик позиций, *POS*. Если в дереве больше нет записей, счетчику позиции присваивается значение NULL.

## <a name="crbtreegetprev"></a><a name="getprev"></a> Крбтри:: prev

Вызовите этот метод, чтобы получить указатель на элемент, хранящийся в `CRBTree` объекте, а затем обновить расположение до предыдущего элемента.

```
const CPair* GetPrev(POSITION& pos) const throw();
CPair* GetPrev(POSITION& pos) throw();
```

### <a name="parameters"></a>Параметры

*pos*<br/>
Счетчик позиций, возвращенный предыдущим вызовом методов, таких как [крбтри:: жесеадпоситион](#getheadposition) или [Крбтри:: финдфирсткэйафтер](#findfirstkeyafter).

### <a name="return-value"></a>Возвращаемое значение

Возвращает указатель на предыдущее значение [кпаир](#cpair_class) , хранящееся в дереве.

### <a name="remarks"></a>Remarks

Обновляет текущий счетчик позиций, *POS*. Если в дереве больше нет записей, счетчику позиции присваивается значение NULL.

## <a name="crbtreegettailposition"></a><a name="gettailposition"></a> Крбтри:: Жеттаилпоситион

Вызовите этот метод, чтобы получить значение позиции для элемента в хвосте дерева.

```
POSITION GetTailPosition() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение позиции для элемента в хвосте дерева.

### <a name="remarks"></a>Remarks

Значение, возвращаемое, `GetTailPosition` можно использовать с такими методами, как [крбтри:: Жеткэйат](#getkeyat) или [крбтри:: prev](#getprev) , для прохода по дереву и извлечения значений.

## <a name="crbtreegetvalueat"></a><a name="getvalueat"></a> Крбтри:: Жетвалуеат

Вызовите этот метод, чтобы получить значение, хранящееся в заданной позиции в `CRBTree` объекте.

```
const V& GetValueAt(POSITION pos) const throw();
V& GetValueAt(POSITION pos) throw();
```

### <a name="parameters"></a>Параметры

*pos*<br/>
Счетчик позиций, возвращенный предыдущим вызовом методов, таких как [крбтри:: жесеадпоситион](#getheadposition) или [Крбтри:: финдфирсткэйафтер](#findfirstkeyafter).

### <a name="return-value"></a>Возвращаемое значение

Возвращает ссылку на значение, хранящееся в заданной позиции в `CRBTree` объекте.

## <a name="crbtreeisempty"></a><a name="isempty"></a> Крбтри:: IsEmpty

Вызовите этот метод, чтобы проверить наличие пустого объекта Tree.

```
bool IsEmpty() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение TRUE, если дерево пусто, и FALSE в противном случае.

## <a name="crbtreekinargtype"></a><a name="kinargtype"></a> Крбтри:: КИНАРГТИПЕ

Тип, используемый при передаче ключа в качестве входного аргумента.

```
typedef KTraits::INARGTYPE KINARGTYPE;
```

## <a name="crbtreekoutargtype"></a><a name="koutargtype"></a> Крбтри:: КАУТАРГТИПЕ

Тип, используемый при возврате ключа в качестве выходного аргумента.

```
typedef KTraits::OUTARGTYPE KOUTARGTYPE;
```

## <a name="crbtreeremoveall"></a><a name="removeall"></a> Крбтри:: RemoveAll

Вызовите этот метод, чтобы удалить все элементы из `CRBTree` объекта.

```cpp
void RemoveAll() throw();
```

### <a name="remarks"></a>Remarks

Очищает `CRBTree` объект, освобождая память, используемую для хранения элементов.

## <a name="crbtreeremoveat"></a><a name="removeat"></a> Крбтри:: RemoveAt

Вызовите этот метод, чтобы удалить элемент в заданной позиции в `CRBTree` объекте.

```cpp
void RemoveAt(POSITION pos) throw();
```

### <a name="parameters"></a>Параметры

*pos*<br/>
Счетчик позиций, возвращенный предыдущим вызовом методов, таких как [крбтри:: жесеадпоситион](#getheadposition) или [Крбтри:: финдфирсткэйафтер](#findfirstkeyafter).

### <a name="remarks"></a>Remarks

Удаляет пару "ключ-значение", хранящуюся в указанной позиции. Память, используемая для хранения элемента, освобождается. ПОЗИЦИЯ, на которую ссылается *POS* , становится недопустимой, а позиция любых других элементов в дереве остается допустимой, но не обязательно сохраняет одинаковый порядок.

## <a name="crbtreesetvalueat"></a><a name="setvalueat"></a> Крбтри:: Сетвалуеат

Вызовите этот метод, чтобы изменить значение, хранящееся в заданной позиции в `CRBTree` объекте.

```cpp
void SetValueAt(POSITION pos, VINARGTYPE value);
```

### <a name="parameters"></a>Параметры

*pos*<br/>
Счетчик позиций, возвращенный предыдущим вызовом методов, таких как [крбтри:: жесеадпоситион](#getheadposition) или [Крбтри:: финдфирсткэйафтер](#findfirstkeyafter).

*value*<br/>
Значение, добавляемое в `CRBTree` объект.

### <a name="remarks"></a>Remarks

Изменяет элемент value, хранящийся в заданной позиции в `CRBTree` объекте.

## <a name="crbtreevinargtype"></a><a name="vinargtype"></a> Крбтри:: ВИНАРГТИПЕ

Тип, используемый при передаче значения в качестве входного аргумента.

```
typedef VTraits::INARGTYPE VINARGTYPE;
```

## <a name="crbtreevoutargtype"></a><a name="voutargtype"></a> Крбтри:: ВАУТАРГТИПЕ

Тип, используемый при передаче значения в качестве выходного аргумента.

```
typedef VTraits::OUTARGTYPE VOUTARGTYPE;
```

## <a name="see-also"></a>См. также раздел

[Общие сведения о классах](../../atl/atl-class-overview.md)
