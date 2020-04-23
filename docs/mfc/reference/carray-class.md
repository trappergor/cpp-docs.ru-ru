---
title: Класс CArray
ms.date: 11/04/2016
f1_keywords:
- CArray
- AFXTEMPL/CArray
- AFXTEMPL/CArray::CArray
- AFXTEMPL/CArray::Add
- AFXTEMPL/CArray::Append
- AFXTEMPL/CArray::Copy
- AFXTEMPL/CArray::ElementAt
- AFXTEMPL/CArray::FreeExtra
- AFXTEMPL/CArray::GetAt
- AFXTEMPL/CArray::GetCount
- AFXTEMPL/CArray::GetData
- AFXTEMPL/CArray::GetSize
- AFXTEMPL/CArray::GetUpperBound
- AFXTEMPL/CArray::InsertAt
- AFXTEMPL/CArray::IsEmpty
- AFXTEMPL/CArray::RemoveAll
- AFXTEMPL/CArray::RemoveAt
- AFXTEMPL/CArray::SetAt
- AFXTEMPL/CArray::SetAtGrow
- AFXTEMPL/CArray::SetSize
helpviewer_keywords:
- CArray [MFC], CArray
- CArray [MFC], Add
- CArray [MFC], Append
- CArray [MFC], Copy
- CArray [MFC], ElementAt
- CArray [MFC], FreeExtra
- CArray [MFC], GetAt
- CArray [MFC], GetCount
- CArray [MFC], GetData
- CArray [MFC], GetSize
- CArray [MFC], GetUpperBound
- CArray [MFC], InsertAt
- CArray [MFC], IsEmpty
- CArray [MFC], RemoveAll
- CArray [MFC], RemoveAt
- CArray [MFC], SetAt
- CArray [MFC], SetAtGrow
- CArray [MFC], SetSize
ms.assetid: fead8b00-4cfd-4625-ad0e-251df62ba92f
ms.openlocfilehash: 3355e72c58365e97f8f3f8ce09754285f671915a
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2020
ms.locfileid: "81753976"
---
# <a name="carray-class"></a>Класс CArray

Поддерживает массивы, которые похожи на массивы C, но могут динамически уменьшаться и расти по мере необходимости.

## <a name="syntax"></a>Синтаксис

```
template <class TYPE, class ARG_TYPE = const TYPE&>
class CArray : public CObject
```

#### <a name="parameters"></a>Параметры

*ТИП*<br/>
Параметр шаблона, который определяет тип объектов, хранящихся в массиве. *TYPE* является параметром, `CArray`который возвращается .

*ARG_TYPE*<br/>
Параметр шаблона, опознавательный тип аргумента, используемый для доступа к объектам, хранящимся в массиве. Часто ссылка на *TYPE*. *ARG_TYPE* является параметром, `CArray`который передается .

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CArray::CArray](#carray)|Создает пустой массив.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CArray::Добавить](#add)|Добавляет элемент в конец массива. При необходимости размер массива увеличивается.|
|[CArray::Приложение](#append)|Приложения другого массива к массиву; растет массив, если это необходимо|
|[CArray::Copy](#copy)|Копирует другой массив в этот массив. При необходимости размер массива увеличивается.|
|[CArray::ElementAt](#elementat)|Возвращает временную ссылку на указатель элемента в массиве.|
|[CArray::FreeExtra](#freeextra)|Освобождает всю неиспользуемую память сверх текущей верхней границы.|
|[CArray::GetAt](#getat)|Возвращает значение по указанному индексу.|
|[CArray::GetCount](#getcount)|Возвращает количество элементов в массиве.|
|[CArray::GetData](#getdata)|Разрешает доступ к элементам в массиве. Может иметь значение NULL.|
|[CArray::GetSize](#getsize)|Возвращает количество элементов в массиве.|
|[CArray::GetUpperBound](#getupperbound)|Возвращает самый большой допустимый индекс.|
|[CArray::InsertAt](#insertat)|Вставляет элемент (или все элементы в другом массиве) по указанному индексу.|
|[CArray::Isempty](#isempty)|Определяет, пуст массив.|
|[CArray::RemoveAll](#removeall)|Удаляет все элементы из этого массива.|
|[CArray::RemoveAt](#removeat)|Удаляет элемент по указанному индексу.|
|[CArray::SetAt](#setat)|Задает значение для указанного индекса. Размер массива не увеличивается.|
|[CArray::SetAtGrow](#setatgrow)|Задает значение для указанного индекса. При необходимости размер массива увеличивается.|
|[CArray::SetSize](#setsize)|Задает число элементов, которые будут храниться в этом массиве.|

### <a name="public-operators"></a>Открытые операторы

|Имя|Описание|
|----------|-----------------|
|[оператор&#91;&#93;](#operator_at)|Получает или задает элемент с указанным индексом.|

## <a name="remarks"></a>Remarks

Индексы массива всегда начинаются с позиции 0. Вы можете решить, следует ли исправить верхнюю границу или включить массив для расширения при добавлении элементов мимо текущей границы. Память распределяется смежно к верхней границе, даже если некоторые элементы являются недействительными.

> [!NOTE]
> Большинство методов, которые `CArray` изменяют размер объекта или добавляют элементы к нему, используют [memcpy_s](../../c-runtime-library/reference/memcpy-s-wmemcpy-s.md) для перемещения элементов. Это проблема, `memcpy_s` потому что не совместима с любыми объектами, которые требуют, чтобы конструктор был вызван. Если `CArray` элементы в них не `memcpy_s`совместимы с, `CArray` необходимо создать новый соответствующего размера. Затем необходимо использовать [CArray::Copy](#copy) и [CArray::SetAt](#setat) для заполнения нового массива, потому что эти методы используют оператора назначения вместо `memcpy_s`.

Как и в блоке C, `CArray` время доступа к индексированному элементу является постоянным и не зависит от размера массива.

> [!TIP]
> Прежде чем использовать массив, используйте [SetSize,](#setsize) чтобы установить его размер и выделить память для него. Если не использовать функцию `SetSize`, при добавлении элементов в массив он будет часто копироваться и для него снова и снова будет повторно выделяться память. Это может привести к ухудшению производительности и фрагментации памяти.

Если вам нужна свалка отдельных элементов в массиве, необходимо установить глубину объекта [CDumpContext](../../mfc/reference/cdumpcontext-class.md) на 1 или больше.

Некоторые функции членов этого класса вызывают функции глобального помощника, `CArray` которые должны быть настроены для большинства видов использования класса. Смотрите тему [Сбора Класса Помощники](../../mfc/reference/collection-class-helpers.md) в разделе MFC Макрос и Глобалс.

Производные классы массива подобны произветворению списка.

Для получения дополнительной информации о [Collections](../../mfc/collections.md)том, как использовать, `CArray`см.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

`CArray`

## <a name="requirements"></a>Требования

**Заголовок:** afxtempl.h

## <a name="carrayadd"></a><a name="add"></a>CArray::Добавить

Добавляет новый элемент в конец массива, увеличив массив на 1.

```
INT_PTR Add(ARG_TYPE newElement);
```

### <a name="parameters"></a>Параметры

*ARG_TYPE*<br/>
Параметры шаблона, определяющие тип аргументов, ссылающихся на элементы в этом массиве.

*newElement*<br/>
Элемент, который будет добавлен в этот массив.

### <a name="return-value"></a>Возвращаемое значение

Индекс добавленного элемента.

### <a name="remarks"></a>Remarks

Если [SetSize](#setsize) был использован `nGrowBy` со значением больше 1, то может быть выделена дополнительная память. Однако верхняя граница увеличится только на 1.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCCollections#22](../../mfc/codesnippet/cpp/carray-class_1.cpp)]

## <a name="carrayappend"></a><a name="append"></a>CArray::Приложение

Вызовите эту функцию участника, чтобы добавить содержимое одного массива в конец другого.

```
INT_PTR Append(const CArray& src);
```

### <a name="parameters"></a>Параметры

*src*<br/>
Источник элементов, которые будут приписаны к массиву.

### <a name="return-value"></a>Возвращаемое значение

Индекс первого придативного элемента.

### <a name="remarks"></a>Remarks

Массивы должны быть одного типа.

При необходимости `Append` можно выделить дополнительную память для размещения элементов, применяемых к массиву.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCCollections#23](../../mfc/codesnippet/cpp/carray-class_2.cpp)]

## <a name="carraycarray"></a><a name="carray"></a>CArray::CArray

Создает пустой массив.

```
CArray();
```

### <a name="remarks"></a>Remarks

Массив растет один элемент за один раз.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCCollections#24](../../mfc/codesnippet/cpp/carray-class_3.cpp)]

## <a name="carraycopy"></a><a name="copy"></a>CArray::Copy

Используйте эту функцию члена для копирования элементов одного массива в другой.

```cpp
void Copy(const CArray& src);
```

### <a name="parameters"></a>Параметры

*src*<br/>
Источник элементов, которые должны быть скопированы в массив.

### <a name="remarks"></a>Remarks

Вызов ифункции этого элемента перезаписать элементы одного массива с элементами другого массива.

`Copy`не освобождает память; однако, при `Copy` необходимости, может выделить дополнительную память для размещения элементов, скопированных на массив.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCCollections#25](../../mfc/codesnippet/cpp/carray-class_4.cpp)]

## <a name="carrayelementat"></a><a name="elementat"></a>CArray::ElementAt

Возвращает временную ссылку на указанный элемент в массиве.

```
TYPE& ElementAt(INT_PTR nIndex);
const TYPE& ElementAt(INT_PTR nIndex) const;
```

### <a name="parameters"></a>Параметры

*Nindex*<br/>
Равный индекс, который больше или равен 0 и меньше, чем или равен значению, возвращенному [GetUpperBound.](#getupperbound)

### <a name="return-value"></a>Возвращаемое значение

Ссылка на элемент массива.

### <a name="remarks"></a>Remarks

Используется для реализации оператора левого назначения для массивов.

### <a name="example"></a>Пример

  Смотрите пример [GetSize](#getsize).

## <a name="carrayfreeextra"></a><a name="freeextra"></a>CArray::FreeExtra

Освобождает любую дополнительную память, которая была выделена в то время как массив был выращен.

```cpp
void FreeExtra();
```

### <a name="remarks"></a>Remarks

Эта функция не влияет на размер или верхнюю границу массива.

### <a name="example"></a>Пример

  Смотрите пример [GetData](#getdata).

## <a name="carraygetat"></a><a name="getat"></a>CArray::GetAt

Возвращает элемент массива в указанном индексе.

```
TYPE& GetAt(INT_PTR nIndex);
const TYPE& GetAt(INT_PTR nIndex) const;
```

### <a name="parameters"></a>Параметры

*ТИП*<br/>
Параметры шаблона, определяющие тип элементов массива.

*Nindex*<br/>
Равный индекс, который больше или равен 0 и меньше, чем или равен значению, возвращенному [GetUpperBound.](#getupperbound)

### <a name="return-value"></a>Возвращаемое значение

Элемент массива в настоящее время находится в этом индексе.

### <a name="remarks"></a>Remarks

Прохождение отрицательного значения или значения, `GetUpperBound` превышающее возвращенное значение, приведет к неудавому утверждению.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCCollections#26](../../mfc/codesnippet/cpp/carray-class_5.cpp)]

## <a name="carraygetcount"></a><a name="getcount"></a>CArray::GetCount

Возвращает количество элементов массива.

```
INT_PTR GetCount() const;
```

### <a name="return-value"></a>Возвращаемое значение

Количество элементов в массиве.

### <a name="remarks"></a>Remarks

Вызовите этот метод, чтобы получить количество элементов в массиве. Поскольку индексы на нулевом уровне, размер на 1 больше, чем самый большой индекс. Вызов этого метода будет генерировать тот же результат, что и метод [CArray::GetSize.](#getsize)

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCCollections#27](../../mfc/codesnippet/cpp/carray-class_6.cpp)]

## <a name="carraygetdata"></a><a name="getdata"></a>CArray::GetData

Используйте эту функцию члена, чтобы получить прямой доступ к элементам в массиве.

```
const TYPE* GetData() const;
TYPE* GetData();
```

### <a name="parameters"></a>Параметры

*ТИП*<br/>
Параметры шаблона, определяющие тип элементов массива.

### <a name="return-value"></a>Возвращаемое значение

Указатель на элемент массива.

### <a name="remarks"></a>Remarks

Если элементы отсутствуют, `GetData` возвращаетнулнулнуло нулевую стоимость.

В то время как прямой доступ к элементам массива `GetData`может помочь вам работать быстрее, используйте осторожность при вызове; любые ошибки, которые вы делаете, непосредственно влияют на элементы вашего массива.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCCollections#28](../../mfc/codesnippet/cpp/carray-class_7.cpp)]

## <a name="carraygetsize"></a><a name="getsize"></a>CArray::GetSize

Возвращает размер массива.

```
INT_PTR GetSize() const;
```

### <a name="remarks"></a>Remarks

Поскольку индексы на нулевом уровне, размер на 1 больше, чем самый большой индекс. Вызов этого метода будет генерировать тот же результат, что и метод [CArray::GetCount.](#getcount)

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCCollections#29](../../mfc/codesnippet/cpp/carray-class_8.cpp)]

## <a name="carraygetupperbound"></a><a name="getupperbound"></a>CArray::GetUpperBound

Возвращает текущую верхнюю границу этого массива.

```
INT_PTR GetUpperBound() const;
```

### <a name="remarks"></a>Remarks

Поскольку индексы массива основаны на нулевом `GetSize`уровне, эта функция возвращает значение на 1 меньше, чем.

Условие `GetUpperBound( )` No -1 указывает на то, что массив не содержит элементов.

### <a name="example"></a>Пример

  Смотрите пример для [CArray::GetAt](#getat).

## <a name="carrayinsertat"></a><a name="insertat"></a>CArray::InsertAt

Первая версия `InsertAt` вставки одного элемента (или нескольких копий элемента) в определенном индексе в массиве.

```cpp
void InsertAt(
    INT_PTR nIndex,
    ARG_TYPE newElement,
    INT_PTR nCount = 1);

void InsertAt(
    INT_PTR nStartIndex,
    CArray* pNewArray);
```

### <a name="parameters"></a>Параметры

*Nindex*<br/>
Индекс, который может быть больше, чем `GetUpperBound`значение, возвращенное .

*ARG_TYPE*<br/>
Параметры шаблона, определяющие тип элементов в этом массиве.

*newElement*<br/>
Элемент, который будет помещен в этот массив.

*Ncount*<br/>
Количество раз, когда этот элемент должен быть вставлен (по умолчанию до 1).

*nСтарт-индекс*<br/>
Неземной индекс, который может быть больше, чем значение, возвращенное [GetUpperBound.](#getupperbound)

*pNewArray*<br/>
Другой массив, содержащий элементы, которые будут добавлены в этот массив.

### <a name="remarks"></a>Remarks

В процессе он смещает вверх (путем приращения индекса) существующий элемент в этом индексе, и он перемещает вверх все элементы над ним.

Вторая версия вставляет все `CArray` элементы из другой коллекции, начиная с позиции *nStartIndex.*

Функция, `SetAt` напротив, заменяет один указанный элемент массива и не сдвигает элементы.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCCollections#30](../../mfc/codesnippet/cpp/carray-class_9.cpp)]

## <a name="carrayisempty"></a><a name="isempty"></a>CArray::Isempty

Определяет, пуст массив.

```
BOOL IsEmpty() const;
```

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если массив не содержит элементов; в противном случае 0.

## <a name="carrayoperator-"></a><a name="operator_at"></a>CArray::оператор\[\]

Эти операторы подписных посыла являются удобной заменой функциям [SetAt](#setat) и [GetAt.](#getat)

```
TYPE& operator[](int_ptr nindex);
const TYPE& operator[](int_ptr nindex) const;
```

### <a name="parameters"></a>Параметры

*ТИП*<br/>
Параметры шаблона, определяющие тип элементов в этом массиве.

*Nindex*<br/>
Индекс элемента, к который будет доступен.

### <a name="remarks"></a>Remarks

Первый оператор, вызванный для массивов, которые не являются **конст,** может быть использован либо справа (r-value) или слева (l-значение) оператора назначения. Второй, называемый **конст массивов,** может быть использован только справа.

Версия библиотеки Debug утверждает, что подтекст (или слева, либо справа от оператора назначения) выходит за рамки.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCCollections#34](../../mfc/codesnippet/cpp/carray-class_10.cpp)]

## <a name="carrayrelocateelements"></a><a name="relocateelements"></a>CArray::ПереместитьЭлементы

Перемещает данные в новый буфер, когда массив должен расти или сокращаться.

```
template<class TYPE, class ARG_TYPE>
AFX_INLINE void CArray<TYPE, ARG_TYPE>::RelocateElements(
    TYPE* pNewData,
    const TYPE* pData,
    INT_PTR nCount);
```

### <a name="parameters"></a>Параметры

*pNewData*<br/>
Новый буфер для массива элементов.

*Pdata*<br/>
Старый массив элементов.

*Ncount*<br/>
Количество элементов в старом массиве.

### <a name="remarks"></a>Remarks

*pNewData* всегда достаточно большой, чтобы держать все элементы *pData.*

Реализация [CArray](../../mfc/reference/carray-class.md) использует этот метод для копирования старых данных в новый буфер, когда массив должен расти или сокращаться (когда [называются SetSize](#setsize) или [FreeExtra).](#freeextra) Реализация по умолчанию просто копирует данные.

Для массивов, в которых элемент содержит указатель на одного из своих членов, или другая структура содержит указатель на один из элементов массива, указатели не обновляются в простой копии. В этом случае можно исправить указатели, внедрив специализацию с соответствующими `RelocateElements` типами. Вы также несете ответственность за копирование данных.

## <a name="carrayremoveall"></a><a name="removeall"></a>CArray::RemoveAll

Удаляет все элементы из этого массива.

```cpp
void RemoveAll();
```

### <a name="remarks"></a>Remarks

Если массив уже пуст, функция по-прежнему работает.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCCollections#31](../../mfc/codesnippet/cpp/carray-class_11.cpp)]

## <a name="carrayremoveat"></a><a name="removeat"></a>CArray::RemoveAt

Удаляет один или несколько элементов, начиная с заданного индекса в массиве.

```cpp
void RemoveAt(
    INT_PTR nIndex,
    INT_PTR nCount = 1);
```

### <a name="parameters"></a>Параметры

*Nindex*<br/>
Равный индекс, который больше или равен 0 и меньше, чем или равен значению, возвращенному [GetUpperBound.](#getupperbound)

*Ncount*<br/>
Число удаляемых элементов.

### <a name="remarks"></a>Remarks

В процессе он смещает вниз все элементы выше удаленного элемента (ы). Он присваивает верхнюю границу массива, но не освобождает память.

Если вы попытаетесь удалить больше элементов, чем содержится в массиве над точкой удаления, то версия библиотеки Debug утверждает.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCCollections#32](../../mfc/codesnippet/cpp/carray-class_12.cpp)]

## <a name="carraysetat"></a><a name="setat"></a>CArray::SetAt

Устанавливает элемент массива в указанном индексе.

```cpp
void SetAt(INT_PTR nIndex, ARG_TYPE newElement);
```

### <a name="parameters"></a>Параметры

*Nindex*<br/>
Равный индекс, который больше или равен 0 и меньше, чем или равен значению, возвращенному [GetUpperBound.](#getupperbound)

*ARG_TYPE*<br/>
Параметры шаблона, определяющие тип аргументов, используемых для элементов массива ссылок.

*newElement*<br/>
Новое значение элемента, хранящееся в указанном положении.

### <a name="remarks"></a>Remarks

`SetAt`не приведет к росту массива. Используйте [SetAtGrow,](#setatgrow) если вы хотите, чтобы массив рос автоматически.

Необходимо убедиться, что значение индекса представляет собой допустимое положение в массиве. Если это выходит за рамки, то версия библиотеки Debug утверждает.

### <a name="example"></a>Пример

  Смотрите пример [GetAt](#getat).

## <a name="carraysetatgrow"></a><a name="setatgrow"></a>CArray::SetAtGrow

Устанавливает элемент массива в указанном индексе.

```cpp
void SetAtGrow(INT_PTR nIndex, ARG_TYPE newElement);
```

### <a name="parameters"></a>Параметры

*Nindex*<br/>
Равный индекс, который больше или равен 0.

*ARG_TYPE*<br/>
Параметры шаблона, определяющие тип элементов в массиве.

*newElement*<br/>
Элемент, который будет добавлен в этот массив. Допускается значение NULL.

### <a name="remarks"></a>Remarks

Массив растет автоматически, если это необходимо (т.е. верхняя граница регулируется с учетом нового элемента).

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCCollections#33](../../mfc/codesnippet/cpp/carray-class_13.cpp)]

## <a name="carraysetsize"></a><a name="setsize"></a>CArray::SetSize

Устанавливает размер пустого или существующего массива; распределяет память при необходимости.

```cpp
void SetSize(
    INT_PTR nNewSize,
    INT_PTR nGrowBy = -1);
```

### <a name="parameters"></a>Параметры

*nNewSize*<br/>
Новый размер массива (количество элементов). Должно быть больше или равно 0.

*nGrowBy*<br/>
Минимальное количество слотов элементов, чтобы выделить, если увеличение размера необходимо.

### <a name="remarks"></a>Remarks

Если новый размер меньше старого, то массив усечен и все неиспользованные памяти освобождены.

Используйте эту функцию, чтобы установить размер массива, прежде чем начать использовать массив. Если не использовать функцию `SetSize`, при добавлении элементов в массив он будет часто копироваться и для него снова и снова будет повторно выделяться память. Это может привести к ухудшению производительности и фрагментации памяти.

Параметр *nGrowBy* влияет на внутреннее распределение памяти, пока массив растет. Его использование никогда не влияет на размер массива, как сообщили [GetSize](#getsize) и [GetUpperBound](#getupperbound). При использовании значения по умолчанию MFC распределяет память таким образом, чтобы избежать фрагментации памяти и оптимизировать эффективность в большинстве случаев.

### <a name="example"></a>Пример

  Смотрите пример [GetData](#getdata).

## <a name="see-also"></a>См. также раздел

[MFC Образец COLLECT](../../overview/visual-cpp-samples.md)<br/>
[Класс CObject](../../mfc/reference/cobject-class.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Класс CObArray](../../mfc/reference/cobarray-class.md)<br/>
[Вспомогательные функции классов коллекции](../../mfc/reference/collection-class-helpers.md)
