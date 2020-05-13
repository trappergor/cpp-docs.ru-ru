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
ms.openlocfilehash: 58c001ccef35d4265ef5b7fe200654781f130872
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2020
ms.locfileid: "81746576"
---
# <a name="crbtree-class"></a>Класс CRBTree

Этот класс предоставляет методы создания и использования красно-черного дерева.

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
Тип ключевого элемента.

*V*<br/>
Тип элемента значения.

*KTraits*<br/>
Код, используемый для копирования или перемещения ключевых элементов. Более подробную информацию можно узнать в [классе CElementTraits.](../../atl/reference/celementtraits-class.md)

*VTraits*<br/>
Код, используемый для копирования или перемещения элементов значения.

## <a name="members"></a>Участники

### <a name="public-typedefs"></a>Общедоступные определения типов

|Имя|Описание|
|----------|-----------------|
|[CRBTree::КИНАРГТИП](#kinargtype)|Тип используется при передаваемом ключе в качестве входиного аргумента.|
|[CRBTree::KOUTARGTYPE](#koutargtype)|Введите используется при возврате ключа в качестве аргумента вывода.|
|[CRBTree::VINARGTYPE](#vinargtype)|Тип используется при перевалке значения в качестве аргумента ввода.|
|[CRBTree::VOUTARGTYPE](#voutargtype)|Тип используется при перевалке значения в качестве аргумента вывода.|

### <a name="public-classes"></a>Открытые классы

|Имя|Описание|
|----------|-----------------|
|[CRBTree::CPair Class](#cpair_class)|Класс, содержащий ключевые элементы и элементы значения.|

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CRBTree:::CRBTree](#dtor)|Деструктор|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CRBTree::FindFirstKeyAfter](#findfirstkeyafter)|Вызовите этот метод, чтобы найти положение элемента, использующую следующий доступный ключ.|
|[CRBTree:GetAt](#getat)|Вызовите этот метод, чтобы получить элемент в заданном положении в дереве.|
|[CRBTree::GetCount](#getcount)|Вызовите этот метод, чтобы получить количество элементов в дереве.|
|[CRBTree::GetHeadPosition](#getheadposition)|Вызовите этот метод, чтобы получить значение позиции элемента во главе дерева.|
|[CRBTree::GetKeyat](#getkeyat)|Вызовите этот метод, чтобы получить ключ из заданной позиции на дереве.|
|[CRBTree::GetNext](#getnext)|Вызовите этот метод, чтобы получить указатель на элемент, хранящийся в объекте, `CRBTree` и перепровить положение к следующему элементу.|
|[CRBTree::GetNextAssoc](#getnextassoc)|Вызовите этот метод, чтобы получить ключ и значение элемента, хранящегося на карте, и переключите положение на следующий элемент.|
|[CRBTree::GetNextKey](#getnextkey)|Вызовите этот метод, чтобы получить ключ элемента, хранящегося в дереве, и переключите положение на следующий элемент.|
|[CRBTree::GetNextValue](#getnextvalue)|Вызовите этот метод, чтобы получить значение элемента, хранящегося в дереве, и перейти к позиции следующему элементу.|
|[CRBTree::GetPrev](#getprev)|Вызов исправьте этот метод, чтобы `CRBTree` получить указатель на элемент, хранящийся в объекте, а затем обновите положение до предыдущего элемента.|
|[CRBTree::GetTailPosition](#gettailposition)|Вызовите этот метод, чтобы получить значение положения элемента в хвосте дерева.|
|[CRBTree::GetValueat](#getvalueat)|Вызовите этот метод для получения значения, `CRBTree` хранящегося в заданном положении объекта.|
|[CRBTree::Isempty](#isempty)|Вызовите этот метод для проверки пустого объекта дерева.|
|[CRBTree::RemoveAll](#removeall)|Вызовите этот метод, `CRBTree` чтобы удалить все элементы из объекта.|
|[CRBTree::RemoveAt](#removeat)|Вызовите этот метод, чтобы удалить `CRBTree` элемент в заданном положении объекта.|
|[CRBTree::SetValueAt](#setvalueat)|Вызовите этот метод, чтобы изменить значение, хранящееся в заданном положении `CRBTree` объекта.|

## <a name="remarks"></a>Remarks

Красно-черное дерево является бинарным деревом поиска, которое использует дополнительный бит информации на узде, чтобы гарантировать, что он остается "сбалансированным", то есть высота дерева не растет непропорционально большой и влияет на производительность.

Этот класс шаблонов предназначен для использования [CRBMap](../../atl/reference/crbmap-class.md) и [CRBMultiMap.](../../atl/reference/crbmultimap-class.md) Основная часть методов, которые составляют эти производные классы предоставляются `CRBTree`.

Для более полного обсуждения различных классов коллекции и их особенностей и характеристик производительности, [см.](../../atl/atl-collection-classes.md)

## <a name="requirements"></a>Требования

**Заголовок:** atlcoll.h

## <a name="crbtreecpair-class"></a><a name="cpair_class"></a>CRBTree::CPair Class

Класс, содержащий ключевые элементы и элементы значения.

```
class CPair : public __POSITION
```

### <a name="remarks"></a>Remarks

Этот класс используется методами [CRBTree::GetAt,](#getat) [CRBTree::GetNext](#getnext)и [CRBTree::GetPrev](#getprev) для доступа к элементам ключа и ценности, хранящимся в структуре дерева.

Члены являются следующими:

|||
|-|-|
|`m_key`|Элемент данных, храпромевающих ключевой элемент.|
|`m_value`|Элемент данных, храпромевающих элемент значения.|

## <a name="crbtreecrbtree"></a><a name="dtor"></a>CRBTree:::CRBTree

Деструктор

```
~CRBTree() throw();
```

### <a name="remarks"></a>Remarks

Освобождает все выделенные ресурсы. Вызовы [CRBTree::RemoveAll,](#removeall) чтобы удалить все элементы.

## <a name="crbtreefindfirstkeyafter"></a><a name="findfirstkeyafter"></a>CRBTree::FindFirstKeyAfter

Вызовите этот метод, чтобы найти положение элемента, использующую следующий доступный ключ.

```
POSITION FindFirstKeyAfter(KINARGTYPE key) const throw();
```

### <a name="parameters"></a>Параметры

*key*<br/>
Значение ключа.

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение позиции элемента, использующую следующий доступный ключ. Если элементов больше нет, NULL возвращается.

### <a name="remarks"></a>Remarks

Этот метод позволяет легко пройти дерево без необходимости вычислять значения положения заранее.

## <a name="crbtreegetat"></a><a name="getat"></a>CRBTree:GetAt

Вызовите этот метод, чтобы получить элемент в заданном положении в дереве.

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

Первые две формы возвращают указатель [cPair.](#cpair_class) Третья форма получает ключ и значение для данной позиции.

### <a name="remarks"></a>Remarks

Значение позиции может быть предварительно определено с помощью вызова к такому методу, как [CRBTree::GetHeadPosition](#getheadposition) или [CRBTree::GetTailPosition](#gettailposition).

В отладке сборки произойдет сбой утверждения, если *pos* равен NULL.

## <a name="crbtreegetcount"></a><a name="getcount"></a>CRBTree::GetCount

Вызовите этот метод, чтобы получить количество элементов в дереве.

```
size_t GetCount() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает количество элементов (каждый ключ/пара значения является одним элементом), хранящимся в дереве.

## <a name="crbtreegetheadposition"></a><a name="getheadposition"></a>CRBTree::GetHeadPosition

Вызовите этот метод, чтобы получить значение позиции элемента во главе дерева.

```
POSITION GetHeadPosition() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение позиции для элемента во главе дерева.

### <a name="remarks"></a>Remarks

Возвращается значение `GetHeadPosition` может быть использовано с помощью таких методов, как [CRBTree::GetKeyAt](#getkeyat) или [CRBTree::GetNext,](#getnext) чтобы пройти дерево и получить значения.

## <a name="crbtreegetkeyat"></a><a name="getkeyat"></a>CRBTree::GetKeyat

Вызовите этот метод, чтобы получить ключ из заданной позиции на дереве.

```
const K& GetKeyAt(POSITION pos) const throw();
```

### <a name="parameters"></a>Параметры

*pos*<br/>
Позиция.

### <a name="return-value"></a>Возвращаемое значение

Возвращает ключ, хранящийся в *позиции, поза* в дереве.

### <a name="remarks"></a>Remarks

Если *pos* не является допустимым значением позиции, результаты непредсказуемы. В отладке сборки произойдет сбой утверждения, если *pos* равен NULL.

## <a name="crbtreegetnext"></a><a name="getnext"></a>CRBTree::GetNext

Вызовите этот метод, чтобы получить указатель на элемент, хранящийся в объекте, `CRBTree` и перепровить положение к следующему элементу.

```
const CPair* GetNext(POSITION& pos) const throw();
CPair* GetNext(POSITION& pos) throw();
```

### <a name="parameters"></a>Параметры

*pos*<br/>
Счетчик позиции, возвращенный предыдущим вызовом таким методам, как [CRBTree::GetHeadPosition](#getheadposition) или [CRBTree::FindFirstKeyAfter](#findfirstkeyafter).

### <a name="return-value"></a>Возвращаемое значение

Возвращает указатель на следующее значение [CPair](#cpair_class) на дереве.

### <a name="remarks"></a>Remarks

Счетчик позиции *pos* обновляется после каждого вызова. Если извлеченный элемент является последним в дереве, *pos* установлен на NULL.

## <a name="crbtreegetnextassoc"></a><a name="getnextassoc"></a>CRBTree::GetNextAssoc

Вызовите этот метод, чтобы получить ключ и значение элемента, хранящегося на карте, и переключите положение на следующий элемент.

```cpp
void GetNextAssoc(
    POSITION& pos,
    KOUTARGTYPE key,
    VOUTARGTYPE value) const;
```

### <a name="parameters"></a>Параметры

*pos*<br/>
Счетчик позиции, возвращенный предыдущим вызовом таким методам, как [CRBTree::GetHeadPosition](#getheadposition) или [CRBTree::FindFirstKeyAfter](#findfirstkeyafter).

*key*<br/>
Параметры шаблона, определяющие тип ключа дерева.

*value*<br/>
Параметры шаблона, определяющие тип значения дерева.

### <a name="remarks"></a>Remarks

Счетчик позиции *pos* обновляется после каждого вызова. Если извлеченный элемент является последним в дереве, *pos* установлен на NULL.

## <a name="crbtreegetnextkey"></a><a name="getnextkey"></a>CRBTree::GetNextKey

Вызовите этот метод, чтобы получить ключ элемента, хранящегося в дереве, и переключите положение на следующий элемент.

```
const K& GetNextKey(POSITION& pos) const throw();
```

### <a name="parameters"></a>Параметры

*pos*<br/>
Счетчик позиции, возвращенный предыдущим вызовом таким методам, как [CRBTree::GetHeadPosition](#getheadposition) или [CRBTree::FindFirstKeyAfter](#findfirstkeyafter).

### <a name="return-value"></a>Возвращаемое значение

Возвращает ссылку на следующий ключ в дереве.

### <a name="remarks"></a>Remarks

Обновляет текущую позицию счетчик, *pos*. Если на дереве больше нет записей, счетчик положения установлен на NULL.

## <a name="crbtreegetnextvalue"></a><a name="getnextvalue"></a>CRBTree::GetNextValue

Вызовите этот метод, чтобы получить значение элемента, хранящегося в дереве, и перейти к позиции следующему элементу.

```
const V& GetNextValue(POSITION& pos) const throw();
V& GetNextValue(POSITION& pos) throw();
```

### <a name="parameters"></a>Параметры

*pos*<br/>
Счетчик позиции, возвращенный предыдущим вызовом таким методам, как [CRBTree::GetHeadPosition](#getheadposition) или [CRBTree::FindFirstKeyAfter](#findfirstkeyafter).

### <a name="return-value"></a>Возвращаемое значение

Возвращает ссылку на следующее значение в дереве.

### <a name="remarks"></a>Remarks

Обновляет текущую позицию счетчик, *pos*. Если на дереве больше нет записей, счетчик положения установлен на NULL.

## <a name="crbtreegetprev"></a><a name="getprev"></a>CRBTree::GetPrev

Вызов исправьте этот метод, чтобы `CRBTree` получить указатель на элемент, хранящийся в объекте, а затем обновите положение до предыдущего элемента.

```
const CPair* GetPrev(POSITION& pos) const throw();
CPair* GetPrev(POSITION& pos) throw();
```

### <a name="parameters"></a>Параметры

*pos*<br/>
Счетчик позиции, возвращенный предыдущим вызовом таким методам, как [CRBTree::GetHeadPosition](#getheadposition) или [CRBTree::FindFirstKeyAfter](#findfirstkeyafter).

### <a name="return-value"></a>Возвращаемое значение

Возвращает указатель на предыдущее значение [CPair,](#cpair_class) хранящееся в дереве.

### <a name="remarks"></a>Remarks

Обновляет текущую позицию счетчик, *pos*. Если на дереве больше нет записей, счетчик положения установлен на NULL.

## <a name="crbtreegettailposition"></a><a name="gettailposition"></a>CRBTree::GetTailPosition

Вызовите этот метод, чтобы получить значение положения элемента в хвосте дерева.

```
POSITION GetTailPosition() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение положения элемента в хвосте дерева.

### <a name="remarks"></a>Remarks

Возвращается значение `GetTailPosition` может быть использовано с помощью таких методов, как [CRBTree::GetKeyAt](#getkeyat) или [CRBTree::GetPrev](#getprev) для обхода дерева и получения значений.

## <a name="crbtreegetvalueat"></a><a name="getvalueat"></a>CRBTree::GetValueat

Вызовите этот метод для получения значения, `CRBTree` хранящегося в заданном положении объекта.

```
const V& GetValueAt(POSITION pos) const throw();
V& GetValueAt(POSITION pos) throw();
```

### <a name="parameters"></a>Параметры

*pos*<br/>
Счетчик позиции, возвращенный предыдущим вызовом таким методам, как [CRBTree::GetHeadPosition](#getheadposition) или [CRBTree::FindFirstKeyAfter](#findfirstkeyafter).

### <a name="return-value"></a>Возвращаемое значение

Возвращает ссылку на значение, хранящееся в данном положении `CRBTree` объекта.

## <a name="crbtreeisempty"></a><a name="isempty"></a>CRBTree::Isempty

Вызовите этот метод для проверки пустого объекта дерева.

```
bool IsEmpty() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает TRUE, если дерево пусто, FALSE в противном случае.

## <a name="crbtreekinargtype"></a><a name="kinargtype"></a>CRBTree::КИНАРГТИП

Тип используется при передаваемом ключе в качестве входиного аргумента.

```
typedef KTraits::INARGTYPE KINARGTYPE;
```

## <a name="crbtreekoutargtype"></a><a name="koutargtype"></a>CRBTree::KOUTARGTYPE

Введите используется при возврате ключа в качестве аргумента вывода.

```
typedef KTraits::OUTARGTYPE KOUTARGTYPE;
```

## <a name="crbtreeremoveall"></a><a name="removeall"></a>CRBTree::RemoveAll

Вызовите этот метод, `CRBTree` чтобы удалить все элементы из объекта.

```cpp
void RemoveAll() throw();
```

### <a name="remarks"></a>Remarks

Очищает `CRBTree` объект, освобождая память, используемую для хранения элементов.

## <a name="crbtreeremoveat"></a><a name="removeat"></a>CRBTree::RemoveAt

Вызовите этот метод, чтобы удалить `CRBTree` элемент в заданном положении объекта.

```cpp
void RemoveAt(POSITION pos) throw();
```

### <a name="parameters"></a>Параметры

*pos*<br/>
Счетчик позиции, возвращенный предыдущим вызовом таким методам, как [CRBTree::GetHeadPosition](#getheadposition) или [CRBTree::FindFirstKeyAfter](#findfirstkeyafter).

### <a name="remarks"></a>Remarks

Удаляет пару ключей/значений, хранящуюся в указанном положении. Память, используемая для хранения элемента, освобождается. POSITION, на который ссылается *pos,* становится недействительным, и хотя POSITION любых других элементов в дереве остается действительным, они не обязательно сохраняют тот же порядок.

## <a name="crbtreesetvalueat"></a><a name="setvalueat"></a>CRBTree::SetValueAt

Вызовите этот метод, чтобы изменить значение, хранящееся в заданном положении `CRBTree` объекта.

```cpp
void SetValueAt(POSITION pos, VINARGTYPE value);
```

### <a name="parameters"></a>Параметры

*pos*<br/>
Счетчик позиции, возвращенный предыдущим вызовом таким методам, как [CRBTree::GetHeadPosition](#getheadposition) или [CRBTree::FindFirstKeyAfter](#findfirstkeyafter).

*value*<br/>
Значение для добавления к объекту. `CRBTree`

### <a name="remarks"></a>Remarks

Изменяет элемент значения, хранящийся в заданном положении `CRBTree` объекта.

## <a name="crbtreevinargtype"></a><a name="vinargtype"></a>CRBTree::VINARGTYPE

Тип используется при перевалке значения в качестве аргумента ввода.

```
typedef VTraits::INARGTYPE VINARGTYPE;
```

## <a name="crbtreevoutargtype"></a><a name="voutargtype"></a>CRBTree::VOUTARGTYPE

Тип используется при перевалке значения в качестве аргумента вывода.

```
typedef VTraits::OUTARGTYPE VOUTARGTYPE;
```

## <a name="see-also"></a>См. также раздел

[Общие сведения о классах](../../atl/atl-class-overview.md)
