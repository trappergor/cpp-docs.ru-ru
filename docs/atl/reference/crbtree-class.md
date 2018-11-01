---
title: Класс CRBTree
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
ms.openlocfilehash: a0f66e888220fbc5a4a484ddd37a3f28dff66065
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50583278"
---
# <a name="crbtree-class"></a>Класс CRBTree

Этот класс предоставляет методы для создания и использования красно-черного дерева.

## <a name="syntax"></a>Синтаксис

```
template <typename K,
          typename V,
          class KTraits = CElementTraits<K>,
          class VTraits = CElementTraits<V>>
class CRBTree
```

#### <a name="parameters"></a>Параметры

*K*<br/>
Тип ключа элемента.

*V*<br/>
Тип значения элемента.

*KTraits*<br/>
Код, используемый для копирования или перемещения ключевые элементы. См. в разделе [класс CElementTraits](../../atl/reference/celementtraits-class.md) для получения дополнительных сведений.

*VTraits*<br/>
Код, используемый для копирования или перемещения элементов value.

## <a name="members"></a>Участники

### <a name="public-typedefs"></a>Общедоступные определения типов

|Имя|Описание|
|----------|-----------------|
|[CRBTree::KINARGTYPE](#kinargtype)|Тип, используемый при передаче ключа в качестве входного аргумента.|
|[CRBTree::KOUTARGTYPE](#koutargtype)|Тип, используемый при возврате ключа в виде выходного аргумента.|
|[CRBTree::VINARGTYPE](#vinargtype)|Тип, используемый, когда значение передается в качестве входного аргумента.|
|[CRBTree::VOUTARGTYPE](#voutargtype)|Тип, используемый, когда значение передается в качестве выходного аргумента.|

### <a name="public-classes"></a>Открытые классы

|Имя|Описание|
|----------|-----------------|
|[Класс CRBTree::CPair](#cpair_class)|Класс, содержащий элементы ключ и значение.|

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CRBTree:: ~ CRBTree](#dtor)|Деструктор|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CRBTree::FindFirstKeyAfter](#findfirstkeyafter)|Вызовите этот метод, чтобы определить позицию элемента, который использует следующего доступного ключа.|
|[CRBTree::GetAt](#getat)|Вызовите этот метод для возвращения элемента в заданной позиции в дереве.|
|[CRBTree::GetCount](#getcount)|Вызовите этот метод, чтобы получить число элементов в дереве.|
|[CRBTree::GetHeadPosition](#getheadposition)|Вызовите этот метод, чтобы получить значение позиции для элемент в голове дерева.|
|[CRBTree::GetKeyAt](#getkeyat)|Вызовите этот метод, чтобы получить ключ в заданной позиции в дереве.|
|[CRBTree::GetNext](#getnext)|Вызовите этот метод, чтобы получить указатель на элемент, хранящийся в `CRBTree` объекта и переместить позицию к следующему элементу.|
|[CRBTree::GetNextAssoc](#getnextassoc)|Вызовите этот метод, чтобы получить ключ и значение элемент, хранящийся в сопоставлении и переместить позицию к следующему элементу.|
|[CRBTree::GetNextKey](#getnextkey)|Вызовите этот метод, чтобы получить ключ элемент, хранящийся в дереве и переместить позицию к следующему элементу.|
|[CRBTree::GetNextValue](#getnextvalue)|Вызовите этот метод для получения значения элемент, хранящийся в дереве и переместить позицию к следующему элементу.|
|[CRBTree::GetPrev](#getprev)|Вызовите этот метод, чтобы получить указатель на элемент, хранящийся в `CRBTree` объекта, а затем обновите положение до предыдущего элемента.|
|[CRBTree::GetTailPosition](#gettailposition)|Этот метод используется для получения значения позиции для элемента по заключительного фрагмента дерева.|
|[CRBTree::GetValueAt](#getvalueat)|Вызовите этот метод, чтобы извлечь значение, сохраненное в заданном положении в `CRBTree` объекта.|
|[CRBTree::IsEmpty](#isempty)|Этот метод используется для проверки дерева пустой объект.|
|[CRBTree::RemoveAll](#removeall)|Вызовите этот метод для удаления всех элементов из `CRBTree` объекта.|
|[CRBTree::RemoveAt](#removeat)|Вызовите этот метод для удаления элемента в заданной позиции в `CRBTree` объекта.|
|[CRBTree::SetValueAt](#setvalueat)|Вызовите этот метод, чтобы изменить значение, хранящееся в заданном положении в `CRBTree` объекта.|

## <a name="remarks"></a>Примечания

Красно-черного дерева представляет собой дерево двоичного поиска, который использует дополнительный бита информации на узел, чтобы убедиться, что он остается «сбалансированный», высота дерева не увеличиваться непропорционально большого и повлиять на производительность.

Этот класс-шаблон предназначен для использования [CRBMap](../../atl/reference/crbmap-class.md) и [CRBMultiMap](../../atl/reference/crbmultimap-class.md). Основная часть методы, составляющие эти производные классы, предоставляемые `CRBTree`.

Более полное описание различных классов коллекций и функций и характеристики производительности, см. в разделе [классы коллекций ATL](../../atl/atl-collection-classes.md).

## <a name="requirements"></a>Требования

**Заголовок:** atlcoll.h

##  <a name="cpair_class"></a>  Класс CRBTree::CPair

Класс, содержащий элементы ключ и значение.

```
class CPair : public __POSITION
```

### <a name="remarks"></a>Примечания

Этот класс используется методами [CRBTree::GetAt](#getat), [CRBTree::GetNext](#getnext), и [CRBTree::GetPrev](#getprev) для доступа к элементам ключа и значения, хранящиеся в структуре дерева.

Далее приведены элементы.

|||
|-|-|
|`m_key`|Элемент данных, хранения ключа элемента.|
|`m_value`|Элемент данных, хранения значение элемента.|

##  <a name="dtor"></a>  CRBTree:: ~ CRBTree

Деструктор

```
~CRBTree() throw();
```

### <a name="remarks"></a>Примечания

Освобождает все выделенные ресурсы. Вызовы [CRBTree::RemoveAll](#removeall) для удаления всех элементов.

##  <a name="findfirstkeyafter"></a>  CRBTree::FindFirstKeyAfter

Вызовите этот метод, чтобы определить позицию элемента, который использует следующего доступного ключа.

```
POSITION FindFirstKeyAfter(KINARGTYPE key) const throw();
```

### <a name="parameters"></a>Параметры

*key*<br/>
Значение ключа.

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение позиции элемента, который использует следующего доступного ключа. Если никакие элементы, возвращается значение NULL.

### <a name="remarks"></a>Примечания

Этот метод позволяет проходить по дереву без необходимости заранее вычислить значения позиции.

##  <a name="getat"></a>  CRBTree::GetAt

Вызовите этот метод для возвращения элемента в заданной позиции в дереве.

```
CPair* GetAt(POSITION pos) throw();
const CPair* GetAt(POSITION pos) const throw();
void GetAt(POSITION pos, KOUTARGTYPE key, VOUTARGTYPE value) const;
```

### <a name="parameters"></a>Параметры

*торговых терминалов*<br/>
Значение позиции.

*key*<br/>
Переменная, которая получает ключ.

*значение*<br/>
Переменная, которая получает значение.

### <a name="return-value"></a>Возвращаемое значение

Первые две формы возвращают указатель на [CPair](#cpair_class). Третья форма получает ключ и значение для заданной позиции.

### <a name="remarks"></a>Примечания

Позиция значение может быть ранее определено с помощью вызова метода например [CRBTree::GetHeadPosition](#getheadposition) или [CRBTree::GetTailPosition](#gettailposition).

В отладочных сборках, произойдет сбой утверждения, если *pos* равен NULL.

##  <a name="getcount"></a>  CRBTree::GetCount

Вызовите этот метод, чтобы получить число элементов в дереве.

```
size_t GetCount() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает количество элементов (один элемент — каждая пара ключ значение), хранящиеся в дереве.

##  <a name="getheadposition"></a>  CRBTree::GetHeadPosition

Вызовите этот метод, чтобы получить значение позиции для элемент в голове дерева.

```
POSITION GetHeadPosition() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение позиции для элемента в голове дерева.

### <a name="remarks"></a>Примечания

Значение, возвращенное `GetHeadPosition` можно использовать с методами например [CRBTree::GetKeyAt](#getkeyat) или [CRBTree::GetNext](#getnext) для прохода по дереву и извлечения значений.

##  <a name="getkeyat"></a>  CRBTree::GetKeyAt

Вызовите этот метод, чтобы получить ключ в заданной позиции в дереве.

```
const K& GetKeyAt(POSITION pos) const throw();
```

### <a name="parameters"></a>Параметры

*торговых терминалов*<br/>
Значение позиции.

### <a name="return-value"></a>Возвращаемое значение

Возвращает ключ, хранящийся в позиции *pos* в дереве.

### <a name="remarks"></a>Примечания

Если *pos* значение не является допустимой, результаты будут непредсказуемыми. В отладочных сборках, произойдет сбой утверждения, если *pos* равен NULL.

##  <a name="getnext"></a>  CRBTree::GetNext

Вызовите этот метод, чтобы получить указатель на элемент, хранящийся в `CRBTree` объекта и переместить позицию к следующему элементу.

```
const CPair* GetNext(POSITION& pos) const throw();
CPair* GetNext(POSITION& pos) throw();
```

### <a name="parameters"></a>Параметры

*торговых терминалов*<br/>
Счетчик позиции, возвращается предыдущим вызовом методов, таких как [CRBTree::GetHeadPosition](#getheadposition) или [CRBTree::FindFirstKeyAfter](#findfirstkeyafter).

### <a name="return-value"></a>Возвращаемое значение

Возвращает указатель на следующий [CPair](#cpair_class) значение в дереве.

### <a name="remarks"></a>Примечания

*Pos* позиции счетчик обновляется после каждого вызова. Если полученный элемент является последним в дереве *pos* имеет значение NULL.

##  <a name="getnextassoc"></a>  CRBTree::GetNextAssoc

Вызовите этот метод, чтобы получить ключ и значение элемент, хранящийся в сопоставлении и переместить позицию к следующему элементу.

```
void GetNextAssoc(
    POSITION& pos,
    KOUTARGTYPE key,
    VOUTARGTYPE value) const;
```

### <a name="parameters"></a>Параметры

*торговых терминалов*<br/>
Счетчик позиции, возвращается предыдущим вызовом методов, таких как [CRBTree::GetHeadPosition](#getheadposition) или [CRBTree::FindFirstKeyAfter](#findfirstkeyafter).

*key*<br/>
Параметр шаблона, указывающий тип ключа, как дерево.

*значение*<br/>
Параметр шаблона, указывающий тип значения, как дерево.

### <a name="remarks"></a>Примечания

*Pos* позиции счетчик обновляется после каждого вызова. Если полученный элемент является последним в дереве *pos* имеет значение NULL.

##  <a name="getnextkey"></a>  CRBTree::GetNextKey

Вызовите этот метод, чтобы получить ключ элемент, хранящийся в дереве и переместить позицию к следующему элементу.

```
const K& GetNextKey(POSITION& pos) const throw();
```

### <a name="parameters"></a>Параметры

*торговых терминалов*<br/>
Счетчик позиции, возвращается предыдущим вызовом методов, таких как [CRBTree::GetHeadPosition](#getheadposition) или [CRBTree::FindFirstKeyAfter](#findfirstkeyafter).

### <a name="return-value"></a>Возвращаемое значение

Возвращает ссылку на следующий ключ в дереве.

### <a name="remarks"></a>Примечания

Обновляет текущий счетчик позиции, *pos*. Если больше нет элементов в дереве, положение счетчика будет присвоено значение NULL.

##  <a name="getnextvalue"></a>  CRBTree::GetNextValue

Вызовите этот метод для получения значения элемент, хранящийся в дереве и переместить позицию к следующему элементу.

```
const V& GetNextValue(POSITION& pos) const throw();
V& GetNextValue(POSITION& pos) throw();
```

### <a name="parameters"></a>Параметры

*торговых терминалов*<br/>
Счетчик позиции, возвращается предыдущим вызовом методов, таких как [CRBTree::GetHeadPosition](#getheadposition) или [CRBTree::FindFirstKeyAfter](#findfirstkeyafter).

### <a name="return-value"></a>Возвращаемое значение

Возвращает ссылку на следующее значение в дереве.

### <a name="remarks"></a>Примечания

Обновляет текущий счетчик позиции, *pos*. Если больше нет элементов в дереве, положение счетчика будет присвоено значение NULL.

##  <a name="getprev"></a>  CRBTree::GetPrev

Вызовите этот метод, чтобы получить указатель на элемент, хранящийся в `CRBTree` объекта, а затем обновите положение до предыдущего элемента.

```
const CPair* GetPrev(POSITION& pos) const throw();
CPair* GetPrev(POSITION& pos) throw();
```

### <a name="parameters"></a>Параметры

*торговых терминалов*<br/>
Счетчик позиции, возвращается предыдущим вызовом методов, таких как [CRBTree::GetHeadPosition](#getheadposition) или [CRBTree::FindFirstKeyAfter](#findfirstkeyafter).

### <a name="return-value"></a>Возвращаемое значение

Возвращает указатель на предыдущую [CPair](#cpair_class) значение, хранящееся в дереве.

### <a name="remarks"></a>Примечания

Обновляет текущий счетчик позиции, *pos*. Если больше нет элементов в дереве, положение счетчика будет присвоено значение NULL.

##  <a name="gettailposition"></a>  CRBTree::GetTailPosition

Этот метод используется для получения значения позиции для элемента по заключительного фрагмента дерева.

```
POSITION GetTailPosition() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение позиции для элемента по заключительного фрагмента дерева.

### <a name="remarks"></a>Примечания

Значение, возвращенное `GetTailPosition` можно использовать с методами например [CRBTree::GetKeyAt](#getkeyat) или [CRBTree::GetPrev](#getprev) для прохода по дереву и извлечения значений.

##  <a name="getvalueat"></a>  CRBTree::GetValueAt

Вызовите этот метод, чтобы извлечь значение, сохраненное в заданном положении в `CRBTree` объекта.

```
const V& GetValueAt(POSITION pos) const throw();
V& GetValueAt(POSITION pos) throw();
```

### <a name="parameters"></a>Параметры

*торговых терминалов*<br/>
Счетчик позиции, возвращается предыдущим вызовом методов, таких как [CRBTree::GetHeadPosition](#getheadposition) или [CRBTree::FindFirstKeyAfter](#findfirstkeyafter).

### <a name="return-value"></a>Возвращаемое значение

Возвращает ссылку на значение, хранящееся в заданном положении в `CRBTree` объекта.

##  <a name="isempty"></a>  CRBTree::IsEmpty

Этот метод используется для проверки дерева пустой объект.

```
bool IsEmpty() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение TRUE, если дерево пуст, значение FALSE в противном случае.

##  <a name="kinargtype"></a>  CRBTree::KINARGTYPE

Тип, используемый при передаче ключа в качестве входного аргумента.

```
typedef KTraits::INARGTYPE KINARGTYPE;
```

##  <a name="koutargtype"></a>  CRBTree::KOUTARGTYPE

Тип, используемый при возврате ключа в виде выходного аргумента.

```
typedef KTraits::OUTARGTYPE KOUTARGTYPE;
```

##  <a name="removeall"></a>  CRBTree::RemoveAll

Вызовите этот метод для удаления всех элементов из `CRBTree` объекта.

```
void RemoveAll() throw();
```

### <a name="remarks"></a>Примечания

Очищает `CRBTree` объект, память, используемую для хранения элементов.

##  <a name="removeat"></a>  CRBTree::RemoveAt

Вызовите этот метод для удаления элемента в заданной позиции в `CRBTree` объекта.

```
void RemoveAt(POSITION pos) throw();
```

### <a name="parameters"></a>Параметры

*торговых терминалов*<br/>
Счетчик позиции, возвращается предыдущим вызовом методов, таких как [CRBTree::GetHeadPosition](#getheadposition) или [CRBTree::FindFirstKeyAfter](#findfirstkeyafter).

### <a name="remarks"></a>Примечания

Удаляет пару ключ значение, хранящееся в указанной позиции. Освобождается память, используемая для сохранения элемента. ПОЗИЦИЯ ссылается *pos* становится недействительным, а в то время как положение любых других элементов в дереве остается допустимым, это не обязательно хранить в том же порядке.

##  <a name="setvalueat"></a>  CRBTree::SetValueAt

Вызовите этот метод, чтобы изменить значение, хранящееся в заданном положении в `CRBTree` объекта.

```
void SetValueAt(POSITION pos, VINARGTYPE value);
```

### <a name="parameters"></a>Параметры

*торговых терминалов*<br/>
Счетчик позиции, возвращается предыдущим вызовом методов, таких как [CRBTree::GetHeadPosition](#getheadposition) или [CRBTree::FindFirstKeyAfter](#findfirstkeyafter).

*значение*<br/>
Значение, которое нужно добавить `CRBTree` объекта.

### <a name="remarks"></a>Примечания

Изменяет значение элемента, хранящихся в заданной позиции в `CRBTree` объекта.

##  <a name="vinargtype"></a>  CRBTree::VINARGTYPE

Тип, используемый, когда значение передается в качестве входного аргумента.

```
typedef VTraits::INARGTYPE VINARGTYPE;
```

##  <a name="voutargtype"></a>  CRBTree::VOUTARGTYPE

Тип, используемый, когда значение передается в качестве выходного аргумента.

```
typedef VTraits::OUTARGTYPE VOUTARGTYPE;
```

## <a name="see-also"></a>См. также

[Общие сведения о классе](../../atl/atl-class-overview.md)
