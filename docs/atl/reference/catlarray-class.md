---
title: Класс CAtlArray
ms.date: 11/04/2016
f1_keywords:
- CAtlArray
- ATLCOLL/ATL::CAtlArray
- ATLCOLL/ATL::Add
- ATLCOLL/ATL::Append
- ATLCOLL/ATL::AssertValid
- ATLCOLL/ATL::Copy
- ATLCOLL/ATL::FreeExtra
- ATLCOLL/ATL::GetAt
- ATLCOLL/ATL::GetCount
- ATLCOLL/ATL::GetData
- ATLCOLL/ATL::InsertArrayAt
- ATLCOLL/ATL::InsertAt
- ATLCOLL/ATL::IsEmpty
- ATLCOLL/ATL::RemoveAll
- ATLCOLL/ATL::RemoveAt
- ATLCOLL/ATL::SetAt
- ATLCOLL/ATL::SetAtGrow
- ATLCOLL/ATL::SetCount
- ATLCOLL/ATL::INARGTYPE
- ATLCOLL/ATL::OUTARGTYPE
helpviewer_keywords:
- CAtlArray class
ms.assetid: 0b503aa8-2357-40af-a326-6654bf1da098
ms.openlocfilehash: 85168af654d3d63e06559486b464938b7fd90ad3
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81321572"
---
# <a name="catlarray-class"></a>Класс CAtlArray

Этот класс реализует объект массива.

## <a name="syntax"></a>Синтаксис

```
template<typename E, class ETraits = CElementTraits<E>>
class CAtlArray
```

#### <a name="parameters"></a>Параметры

*E*<br/>
Тип данных для сохранения в массиве.

*ETraits*<br/>
Код, используемый для копирования или перемещения элементов.

## <a name="members"></a>Участники

### <a name="methods"></a>Методы

|||
|-|-|
|[Добавить](#add)|Вызовите этот метод, чтобы добавить элемент в объект массива.|
|[Добавить](#append)|Вызовите этот метод, чтобы добавить содержимое одного массива в конец другого.|
|[Assertvalid](#assertvalid)|Вызовите этот метод, чтобы подтвердить, что объект массива действителен.|
|[Catlarray](#catlarray)|Конструктор.|
|[(CAtlArray)](#dtor)|Деструктор|
|[Копирование](#copy)|Вызовите этот метод, чтобы скопировать элементы одного массива в другой.|
|[FreeExtra](#freeextra)|Вызовите этот метод, чтобы удалить любые пустые элементы из массива.|
|[Getat](#getat)|Вызовите этот метод, чтобы извлечь один элемент из объекта массива.|
|[GetCount](#getcount)|Вызовите этот метод, чтобы вернуть количество элементов, хранящихся в массиве.|
|[GetData](#getdata)|Вызовите этот метод, чтобы вернуть указатель к первому элементу массива.|
|[ВставитьАрхайт](#insertarrayat)|Вызовите этот метод, чтобы вставить один массив в другой.|
|[Вставка](#insertat)|Вызовите этот метод, чтобы вставить новый элемент (или несколько копий элемента) в объект массива.|
|[IsEmpty](#isempty)|Вызовите этот метод, чтобы проверить, пустен ли массив.|
|[Removeall](#removeall)|Вызов иметод, чтобы удалить все элементы из объекта массива.|
|[RemoveAt](#removeat)|Вызовите этот метод, чтобы удалить один или несколько элементов из массива.|
|[Setat](#setat)|Вызовите этот метод, чтобы установить значение элемента в объекте массива.|
|[SetAtGrow](#setatgrow)|Вызовите этот метод, чтобы установить значение элемента в объекте массива, расширяя массив по мере необходимости.|
|[SetCount](#setcount)|Вызовите этот метод, чтобы установить размер объекта массива.|

### <a name="operators"></a>Операторы

|||
|-|-|
|[оператор &#91;&#93;](#operator_at)|Позвоните оператору, чтобы вернуть ссылку на элемент в массиве.|

### <a name="typedefs"></a>Определения типов

|||
|-|-|
|[ИНАРГТИП](#inargtype)|Тип данных для добавления элементов в массив.|
|[АУТАРГТИП](#outargtype)|Тип данных для извлечения элементов из массива.|

## <a name="remarks"></a>Remarks

`CAtlArray`предоставляет методы создания и управления массивом элементов пользовательского типа. Хотя `CAtlArray` объект похож на стандартные массивы C, объект может динамически сокращаться и расти по мере необходимости. Индекс массива всегда начинается с позиции 0, а верхняя граница может быть исправлена или разрешена к расширению по мере добавления новых элементов.

Для массивов с небольшим количеством элементов можно использовать класс ATL [CSimpleArray.](../../atl/reference/csimplearray-class.md)

`CAtlArray`тесно связан с классом `CArray` МФЦ и будет работать в проекте МФЦ, хотя и без поддержки сериализации.

Для получения дополнительной информации, [см.](../../atl/atl-collection-classes.md)

## <a name="requirements"></a>Требования

**Заголовок:** atlcoll.h

## <a name="catlarrayadd"></a><a name="add"></a>CAtlArray::Добавить

Вызовите этот метод, чтобы добавить элемент в объект массива.

```
size_t Add(INARGTYPE element);
size_t Add();
```

### <a name="parameters"></a>Параметры

*Элемент*<br/>
Элемент, который будет добавлен в массив.

### <a name="return-value"></a>Возвращаемое значение

Возвращает индекс добавленного элемента.

### <a name="remarks"></a>Remarks

Новый элемент добавляется к концу массива. Если элемент не предоставляется, добавляется пустой элемент; то есть, массив увеличивается в размерах, как будто был добавлен реальный элемент. Если операция не удается, [AtlThrow](debugging-and-error-reporting-global-functions.md#atlthrow) вызывается с аргументом E_OUTOFMEMORY.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_Utilities#1](../../atl/codesnippet/cpp/catlarray-class_1.cpp)]

## <a name="catlarrayappend"></a><a name="append"></a>CAtlArray::Приложение

Вызовите этот метод, чтобы добавить содержимое одного массива в конец другого.

```
size_t Append(const CAtlArray<E, ETraits>& aSrc);
```

### <a name="parameters"></a>Параметры

*aSrc*<br/>
Массив для приложения.

### <a name="return-value"></a>Возвращаемое значение

Возвращает индекс первого придативного элемента.

### <a name="remarks"></a>Remarks

Элементы в поставляемом массиве добавляются к концу существующего массива. При необходимости память будет выделена для размещения новых элементов.

Массивы должны быть одного типа, и невозможно прибовать массив к себе.

В отладке сборки, ATLASSERT `CAtlArray` будет поднят, если аргумент не является действительным массивом или если *aSrc* относится к тому же объекту. При сборке релизов недействительные аргументы могут привести к непредсказуемому поведению.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_Utilities#2](../../atl/codesnippet/cpp/catlarray-class_2.cpp)]

## <a name="catlarrayassertvalid"></a><a name="assertvalid"></a>CAtlArray:AssertValid

Вызовите этот метод, чтобы подтвердить, что объект массива действителен.

```
void AssertValid() const;
```

### <a name="remarks"></a>Remarks

Если объект массива недействителен, ATLASSERT бросит утверждение. Этот метод доступен только в том случае, если _DEBUG определен.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_Utilities#3](../../atl/codesnippet/cpp/catlarray-class_3.cpp)]

## <a name="catlarraycatlarray"></a><a name="catlarray"></a>CAtlArray::CAtlArray

Конструктор.

```
CAtlArray() throw();
```

### <a name="remarks"></a>Remarks

Инициализирует объект массива.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_Utilities#4](../../atl/codesnippet/cpp/catlarray-class_4.cpp)]

## <a name="catlarraycatlarray"></a><a name="dtor"></a>CAtlArray:::CAtlArray

Деструктор

```
~CAtlArray() throw();
```

### <a name="remarks"></a>Remarks

Освобождает все ресурсы, используемые объектом массива.

## <a name="catlarraycopy"></a><a name="copy"></a>CAtlArray::Copy

Вызовите этот метод, чтобы скопировать элементы одного массива в другой.

```
void Copy(const CAtlArray<E, ETraits>& aSrc);
```

### <a name="parameters"></a>Параметры

*aSrc*<br/>
Источник элементов для копирования в массив.

### <a name="remarks"></a>Remarks

Вызовите этот метод, чтобы перезаписать элементы одного массива с элементами другого массива. При необходимости память будет выделена для размещения новых элементов. Невозможно скопировать элементы массива для себя.

Если существующее содержимое массива необходимо сохранить, используйте [CAtlArray::Append](#append) вместо этого.

В отладке сборки atLASSERT будет `CAtlArray` поднят, если существующий объект недействителен, или если *aSrc* относится к тому же объекту. При сборке релизов недействительные аргументы могут привести к непредсказуемому поведению.

> [!NOTE]
> `CAtlArray::Copy`не поддерживает массивы, состоящие из элементов, созданных с классом [CAutoPtr.](../../atl/reference/cautoptr-class.md)

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_Utilities#5](../../atl/codesnippet/cpp/catlarray-class_5.cpp)]

## <a name="catlarrayfreeextra"></a><a name="freeextra"></a>CAtlArray::FreeExtra

Вызовите этот метод, чтобы удалить любые пустые элементы из массива.

```
void FreeExtra() throw();
```

### <a name="remarks"></a>Remarks

Любые пустые элементы удаляются, но размер и верхняя граница массива остаются неизменными.

В отладке сборки объект ATLASSERT будет поднят, если объект CAtlArray недействителен или если массив превысит его максимальный размер.

## <a name="catlarraygetat"></a><a name="getat"></a>CAtlArray::GetAt

Вызов иметод, чтобы извлечь один элемент из объекта массива.

```
const E& GetAt(size_t iElement) const throw();
E& GetAt(size_t iElement) throw();
```

### <a name="parameters"></a>Параметры

*iElement*<br/>
Значение индекса элемента массива для возврата.

### <a name="return-value"></a>Возвращаемое значение

Возвращает ссылку на необходимый элемент массива.

### <a name="remarks"></a>Remarks

В отладке сборки ATLASSERT будет поднят, если *iElement* превышает количество элементов в массиве. При сборке релизов недействительный аргумент может привести к непредсказуемому поведению.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_Utilities#6](../../atl/codesnippet/cpp/catlarray-class_6.cpp)]

## <a name="catlarraygetcount"></a><a name="getcount"></a>CAtlArray::GetCount

Вызовите этот метод, чтобы вернуть количество элементов, хранящихся в массиве.

```
size_t GetCount() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает количество элементов, хранящихся в массиве.

### <a name="remarks"></a>Remarks

Поскольку первый элемент в массиве находится на `GetCount` позиции 0, возвращаемые значения всегда на 1 больше, чем самый большой индекс.

### <a name="example"></a>Пример

Смотрите пример [для CAtlArray::GetAt](#getat).

## <a name="catlarraygetdata"></a><a name="getdata"></a>CAtlArray::GetData

Вызовите этот метод, чтобы вернуть указатель к первому элементу массива.

```
E* GetData() throw();
const E* GetData() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает указатель в месторасположение памяти, хратомяв первый элемент массива. Если элементы отсутствуют, NULL возвращается.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_Utilities#7](../../atl/codesnippet/cpp/catlarray-class_7.cpp)]

## <a name="catlarrayinargtype"></a><a name="inargtype"></a>CAtlArray::INARGTYPE

Тип данных для добавления элементов в массив.

```
typedef ETraits::INARGTYPE INARGTYPE;
```

## <a name="catlarrayinsertarrayat"></a><a name="insertarrayat"></a>CAtlArray::InsertArrayAt

Вызовите этот метод, чтобы вставить один массив в другой.

```
void InsertArrayAt(size_t iStart, const CAtlArray<E, ETraits>* paNew);
```

### <a name="parameters"></a>Параметры

*iStart*<br/>
Индекс, по которому должен быть вставлен массив.

*paNew*<br/>
Массив, который будет вставлен.

### <a name="remarks"></a>Remarks

Элементы из массива *paNew* копируются в объект массива, начиная с элемента *iStart.* Существующие элементы массива перемещаются, чтобы избежать перезаписаний.

В отладке сборки, ATLASSERT `CAtlArray` будет поднят, если объект недействителен, или если *указатель paNew* является null или недействительным.

> [!NOTE]
> `CAtlArray::InsertArrayAt`не поддерживает массивы, состоящие из элементов, созданных с классом [CAutoPtr.](../../atl/reference/cautoptr-class.md)

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_Utilities#8](../../atl/codesnippet/cpp/catlarray-class_8.cpp)]

## <a name="catlarrayinsertat"></a><a name="insertat"></a>CAtlArray::InsertAt

Вызовите этот метод, чтобы вставить новый элемент (или несколько копий элемента) в объект массива.

```
void InsertAt(size_t iElement, INARGTYPE element, size_t nCount = 1);
```

### <a name="parameters"></a>Параметры

*iElement*<br/>
Индекс, в котором должен быть вставлен элемент или элемент.

*Элемент*<br/>
Значение элемента или элементов, которые будут вставлены.

*Ncount*<br/>
Количество элементов для добавления.

### <a name="remarks"></a>Remarks

Вставляет один или несколько элементов в массив, начиная с индекса *iElement.* Существующие элементы перемещаются, чтобы избежать перезаписаний.

В отладке сборки, ATLASSERT `CAtlArray` будет поднят, если объект недействителен, количество элементов, которые будут добавлены, равна нулю, или совокупное количество элементов слишком велико для массива, чтобы содержать. В розничных сборках прохождение недействительных параметров может привести к непредсказуемым результатам.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_Utilities#9](../../atl/codesnippet/cpp/catlarray-class_9.cpp)]

## <a name="catlarrayisempty"></a><a name="isempty"></a>CAtlArray::IsEmpty

Вызовите этот метод, чтобы проверить, пустен ли массив.

```
bool IsEmpty() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает верно, если массив пуст, ложно в противном случае.

### <a name="remarks"></a>Remarks

Массив считается пустым, если он не содержит элементов. Поэтому, даже если массив содержит пустые элементы, он не пуст.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_Utilities#10](../../atl/codesnippet/cpp/catlarray-class_10.cpp)]

## <a name="catlarrayoperator-"></a><a name="operator_at"></a>CAtlArray::оператор

Позвоните оператору, чтобы вернуть ссылку на элемент в массиве.

```
E& operator[](size_t ielement) throw();
const E& operator[](size_t ielement) const throw();
```

### <a name="parameters"></a>Параметры

*iElement*<br/>
Значение индекса элемента массива для возврата.

### <a name="return-value"></a>Возвращаемое значение

Возвращает ссылку на необходимый элемент массива.

### <a name="remarks"></a>Remarks

Выполняет аналогичную функцию [CAtlArray::GetAt](#getat). В отличие от класса MFC [CArray,](../../mfc/reference/carray-class.md)этот оператор не может быть использован в качестве замены [CAtlArray::SetAt](#setat).

В отладке сборки ATLASSERT будет поднят, если *iElement* превысит общее количество элементов в массиве. В розничных сборках недействительный параметр может привести к непредсказуемым результатам.

## <a name="catlarrayoutargtype"></a><a name="outargtype"></a>CAtlArray::OUTARGTYPE

Тип данных для извлечения элементов из массива.

```
typedef ETraits::OUTARGTYPE OUTARGTYPE;
```

## <a name="catlarrayremoveall"></a><a name="removeall"></a>CAtlArray::RemoveAll

Вызов иметод, чтобы удалить все элементы из объекта массива.

```
void RemoveAll() throw();
```

### <a name="remarks"></a>Remarks

Удаляет все элементы из объекта массива.

Этот метод вызывает [CAtlArray::SetCount](#setcount) для того чтобы изменить размер массива и затем освободить любое выделенное памяти.

### <a name="example"></a>Пример

Смотрите пример [для CAtlArray::IsEmpty](#isempty).

## <a name="catlarrayremoveat"></a><a name="removeat"></a>CAtlArray::RemoveAt

Вызовите этот метод, чтобы удалить один или несколько элементов из массива.

```
void RemoveAt(size_t iElement, size_t nCount = 1);
```

### <a name="parameters"></a>Параметры

*iElement*<br/>
Индекс первого элемента для удаления.

*Ncount*<br/>
Число удаляемых элементов.

### <a name="remarks"></a>Remarks

Удаляет один или несколько элементов из массива. Все оставшиеся элементы смещаются вниз. Верхняя граница разрушена, но память не освобождается до вызова [CAtlArray::FreeExtra](#freeextra) не будет выполнена.

В отладке сборки atLASSERT будет `CAtlArray` поднят, если объект недействителен, или если общая сумма *iElement* и *nCount* превышает общее количество элементов в массиве. В розничных сборках недействительные параметры могут привести к непредсказуемым результатам.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_Utilities#11](../../atl/codesnippet/cpp/catlarray-class_11.cpp)]

## <a name="catlarraysetat"></a><a name="setat"></a>CAtlArray::SetAt

Вызовите этот метод, чтобы установить значение элемента в объекте массива.

```
void SetAt(size_t iElement, INARGTYPE element);
```

### <a name="parameters"></a>Параметры

*iElement*<br/>
Индекс, указывающий на элемент массива для установки.

*Элемент*<br/>
Новое значение указанного элемента.

### <a name="remarks"></a>Remarks

В отладке сборки ATLASSERT будет поднят, если *iElement* превышает количество элементов в массиве. В розничных сборках недействительный параметр может привести к непредсказуемым результатам.

### <a name="example"></a>Пример

Смотрите пример [для CAtlArray::GetAt](#getat).

## <a name="catlarraysetcount"></a><a name="setcount"></a>CAtlArray::SetCount

Вызовите этот метод, чтобы установить размер объекта массива.

```
bool SetCount(size_t nNewSize, int nGrowBy = - 1);
```

### <a name="parameters"></a>Параметры

*nNewSize*<br/>
Необходимый размер массива.

*nGrowBy*<br/>
Значение, используемое для определения размера буфера. Значение -1 приводит к использованию внутренне рассчитанного значения.

### <a name="return-value"></a>Возвращаемое значение

Возвращает верно, если массив успешно переформулирован, ложно в противном случае.

### <a name="remarks"></a>Remarks

Массив может быть увеличен или уменьшен в размерах. При увеличении в массив добавляются дополнительные пустые элементы. При уменьшении элементы с самыми большими индексами будут удалены, а память освобождена.

Используйте этот метод, чтобы установить размер массива перед его использованием. Если `SetCount` он не используется, процесс добавления элементов - и последующее распределение памяти выполняется - уменьшит производительность и фрагмент памяти.

### <a name="example"></a>Пример

Смотрите пример [для CAtlArray::GetData](#getdata).

## <a name="catlarraysetatgrow"></a><a name="setatgrow"></a>CAtlArray::SetAtGrow

Вызовите этот метод, чтобы установить значение элемента в объекте массива, расширяя массив по мере необходимости.

```
void SetAtGrow(size_t iElement, INARGTYPE element);
```

### <a name="parameters"></a>Параметры

*iElement*<br/>
Индекс, указывающий на элемент массива для установки.

*Элемент*<br/>
Новое значение указанного элемента.

### <a name="remarks"></a>Remarks

Заменяет значение элемента, на который указывает индекс. Если *iElement* больше текущего размера массива, массив автоматически увеличивается с помощью вызова [cAtlArray::SetCount](#setcount). В отладке сборки, ATLASSERT `CAtlArray` будет поднят, если объект не действителен. В розничных сборках недействительные параметры могут привести к непредсказуемым результатам.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_Utilities#12](../../atl/codesnippet/cpp/catlarray-class_12.cpp)]

## <a name="see-also"></a>См. также раздел

[Образец MMXSwarm](../../overview/visual-cpp-samples.md)<br/>
[ДинамическийПотребительский образец](../../overview/visual-cpp-samples.md)<br/>
[Образец UpdatePV](../../overview/visual-cpp-samples.md)<br/>
[Маркес](../../overview/visual-cpp-samples.md)<br/>
[Класс CArray](../../mfc/reference/carray-class.md)<br/>
[Общие сведения о классах](../../atl/atl-class-overview.md)
