---
title: CArray-класс
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
ms.openlocfilehash: f82dbf7dce2e14bf760bb76d23d23f667797ee0f
ms.sourcegitcommit: 5cecccba0a96c1b4ccea1f7a1cfd91f259cc5bde
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/01/2019
ms.locfileid: "58779850"
---
# <a name="carray-class"></a>CArray-класс

Поддерживает массивы, которые похожи на массивы C, но может динамически увеличиваться и при необходимости.

## <a name="syntax"></a>Синтаксис

```
template <class TYPE, class ARG_TYPE = const TYPE&>
class CArray : public CObject
```

#### <a name="parameters"></a>Параметры

*ТИП*<br/>
Параметр шаблона, определяющий тип объектов, хранящихся в массиве. *Тип* — это параметр, возвращаемый `CArray`.

*ARG_TYPE*<br/>
Параметр шаблона, определяющий тип аргумента, который используется для доступа к объектам, которые хранятся в массиве. Часто ссылку *тип*. *ARG_TYPE* — это параметр, передаваемый `CArray`.

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|name|Описание|
|----------|-----------------|
|[CArray::CArray](#carray)|Создает пустой массив.|

### <a name="public-methods"></a>Открытые методы

|name|Описание|
|----------|-----------------|
|[CArray::Add](#add)|Добавляет элемент в конец массива. При необходимости размер массива увеличивается.|
|[CArray::Append](#append)|Добавляет другой массив к массиву; растет массива, при необходимости|
|[CArray::Copy](#copy)|Копирует другой массив в этот массив. При необходимости размер массива увеличивается.|
|[CArray::ElementAt](#elementat)|Возвращает временную ссылку на указатель элемента в массиве.|
|[CArray::FreeExtra](#freeextra)|Освобождает всю неиспользуемую память сверх текущей верхней границы.|
|[CArray::GetAt](#getat)|Возвращает значение по указанному индексу.|
|[CArray::GetCount](#getcount)|Возвращает количество элементов в массиве.|
|[CArray::GetData](#getdata)|Разрешает доступ к элементам в массиве. Может иметь значение NULL.|
|[CArray::GetSize](#getsize)|Возвращает количество элементов в массиве.|
|[CArray::GetUpperBound](#getupperbound)|Возвращает самый большой допустимый индекс.|
|[CArray::InsertAt](#insertat)|Вставляет элемент (или все элементы в другом массиве) по указанному индексу.|
|[CArray::IsEmpty](#isempty)|Определяет, является ли пустой массив.|
|[CArray::RemoveAll](#removeall)|Удаляет все элементы из этого массива.|
|[CArray::RemoveAt](#removeat)|Удаляет элемент по указанному индексу.|
|[CArray::SetAt](#setat)|Задает значение для указанного индекса. Размер массива не увеличивается.|
|[CArray::SetAtGrow](#setatgrow)|Задает значение для указанного индекса. При необходимости размер массива увеличивается.|
|[CArray::SetSize](#setsize)|Задает число элементов, которые будут храниться в этом массиве.|

### <a name="public-operators"></a>Открытые операторы

|name|Описание|
|----------|-----------------|
|[operator&#91;&#93;](#operator_at)|Получает или задает элемент с указанным индексом.|

## <a name="remarks"></a>Примечания

Индексы массива всегда начинаются с позиции 0. Можно ли исправить верхнюю границу или включить массив, в который разверните при добавлении элементов за пределами текущего привязан. Память выделяется непрерывно верхней границей, даже если некоторые элементы имеют значение null.

> [!NOTE]
>  Большинство методов, которые изменяют размер `CArray` объекта или добавить элементы к нему используют [memcpy_s](../../c-runtime-library/reference/memcpy-s-wmemcpy-s.md) должны перемещаться элементы. Это проблема, так как `memcpy_s` не совместим с любые объекты, требующие к вызову конструктора. Если элементы в `CArray` не совместимы с `memcpy_s`, необходимо создать новый `CArray` соответствующего размера. Затем необходимо использовать [CArray::Copy](#copy) и [CArray::SetAt](#setat) необходимо заполнить новый массив, так как эти методы используют оператор присваивания, а не `memcpy_s`.

Как и в массиве C время обращения к `CArray` индексированный элемент является константой и не зависит от размера массива.

> [!TIP]
>  Прежде чем использовать массив, используйте [SetSize](#setsize) определить его размер и выделить память для него. Если не использовать функцию `SetSize`, при добавлении элементов в массив он будет часто копироваться и для него снова и снова будет повторно выделяться память. Это может привести к ухудшению производительности и фрагментации памяти.

Если вам требуется дамп отдельных элементов в массиве, необходимо задать глубину [CDumpContext](../../mfc/reference/cdumpcontext-class.md) 1 или большего размера объекта.

Некоторые функции-члены этого класса вызова глобального вспомогательные функции, необходимо настроить для большинства вариантов использования `CArray` класса. См. в разделе [вспомогательные функции классов коллекции](../../mfc/reference/collection-class-helpers.md) в разделе макросы и Globals MFC.

Для создания производного класса массива похоже на списке наследования.

Дополнительные сведения об использовании `CArray`, см. в статье [коллекций](../../mfc/collections.md).

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

`CArray`

## <a name="requirements"></a>Требования

**Заголовок:** afxtempl.h

##  <a name="add"></a>  CArray::Add

Добавляет новый элемент в конец массива, увеличение массива на 1.

```
INT_PTR Add(ARG_TYPE newElement);
```

### <a name="parameters"></a>Параметры

*ARG_TYPE*<br/>
Параметр шаблона, указывающий тип аргументов, ссылок на элементы в этом массиве.

*newElement*<br/>
Элемент, добавляемый в этот массив.

### <a name="return-value"></a>Возвращаемое значение

Индекс добавленного элемента.

### <a name="remarks"></a>Примечания

Если [SetSize](#setsize) оно использовалось с `nGrowBy` значение больше 1, то дополнительная память может выделяться. Тем не менее верхнюю границу, будут увеличены только 1.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCCollections#22](../../mfc/codesnippet/cpp/carray-class_1.cpp)]

##  <a name="append"></a>  CArray::Append

Вызывайте эту функцию члена, чтобы добавить содержимое одного массива в другой конец.

```
INT_PTR Append(const CArray& src);
```

### <a name="parameters"></a>Параметры

*src*<br/>
Источник элементов для добавления в массив.

### <a name="return-value"></a>Возвращаемое значение

Индекс первый добавленный элемент.

### <a name="remarks"></a>Примечания

Массивы должны иметь тот же тип.

При необходимости `Append` может выделить дополнительный объем памяти для размещения элементов, добавляемый в конец массива.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCCollections#23](../../mfc/codesnippet/cpp/carray-class_2.cpp)]

##  <a name="carray"></a>  CArray::CArray

Создает пустой массив.

```
CArray();
```

### <a name="remarks"></a>Примечания

Массив растет одного элемента за раз.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCCollections#24](../../mfc/codesnippet/cpp/carray-class_3.cpp)]

##  <a name="copy"></a>  CArray::Copy

Используйте эту функцию-член для копирования элементов одного массива в другой.

```
void Copy(const CArray& src);
```

### <a name="parameters"></a>Параметры

*src*<br/>
Источник элементов, копируемых в массив.

### <a name="remarks"></a>Примечания

Вызовите эту функцию-член для перезаписи элементы одного массива с элементами другого массива.

`Copy` не освобождает память; Тем не менее, при необходимости `Copy` может выделить дополнительный объем памяти для размещения элементов, копируемых в массив.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCCollections#25](../../mfc/codesnippet/cpp/carray-class_4.cpp)]

##  <a name="elementat"></a>  CArray::ElementAt

Возвращает временную ссылку на указанный элемент в массиве.

```
TYPE& ElementAt(INT_PTR nIndex);
const TYPE& ElementAt(INT_PTR nIndex) const;
```

### <a name="parameters"></a>Параметры

*nIndex*<br/>
Целочисленный индекс, который больше или равно 0 и меньше или равно значение, возвращенное [GetUpperBound](#getupperbound).

### <a name="return-value"></a>Возвращаемое значение

Ссылка на элемент массива.

### <a name="remarks"></a>Примечания

Он используется для реализации оператор слева от оператора присваивания для массивов.

### <a name="example"></a>Пример

  См. в примере [GetSize](#getsize).

##  <a name="freeextra"></a>  CArray::FreeExtra

Освобождает любой дополнительной памяти, который был выделен хотя при явном массива.

```
void FreeExtra();
```

### <a name="remarks"></a>Примечания

Эта функция не влияет на размер или верхней границы массива.

### <a name="example"></a>Пример

  См. в примере [GetData](#getdata).

##  <a name="getat"></a>  CArray::GetAt

Возвращает элемент массива по указанному индексу.

```
TYPE& GetAt(INT_PTR nIndex);
const TYPE& GetAt(INT_PTR nIndex) const;
```

### <a name="parameters"></a>Параметры

*ТИП*<br/>
Параметр шаблона, указывающий тип элементов массива.

*nIndex*<br/>
Целочисленный индекс, который больше или равно 0 и меньше или равно значение, возвращенное [GetUpperBound](#getupperbound).

### <a name="return-value"></a>Возвращаемое значение

Элемент массива в настоящее время на этот индекс.

### <a name="remarks"></a>Примечания

Передача отрицательное значение или значение больше, чем значение, возвращенное `GetUpperBound` приведет к утверждение, вызвавшее сбой.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCCollections#26](../../mfc/codesnippet/cpp/carray-class_5.cpp)]

##  <a name="getcount"></a>  CArray::GetCount

Возвращает количество элементов массива.

```
INT_PTR GetCount() const;
```

### <a name="return-value"></a>Возвращаемое значение

Количество элементов в массиве.

### <a name="remarks"></a>Примечания

Вызовите этот метод для получения числа элементов в массиве. Так как индексы отсчитываются от нуля, размер равен 1, больше, чем наибольший индекс. Вызов этого метода создает тот же результат, как [CArray::GetSize](#getsize) метод.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCCollections#27](../../mfc/codesnippet/cpp/carray-class_6.cpp)]

##  <a name="getdata"></a>  CArray::GetData

Используйте эту функцию-член для прямого доступа к элементам массива.

```
const TYPE* GetData() const;
TYPE* GetData();
```

### <a name="parameters"></a>Параметры

*ТИП*<br/>
Параметр шаблона, указывающий тип элементов массива.

### <a name="return-value"></a>Возвращаемое значение

Указатель на элемент массива.

### <a name="remarks"></a>Примечания

Если нет элементов, `GetData` возвращает значение null.

Хотя прямой доступ к элементам массива может помочь вам работать быстрее, будьте осторожны при вызове `GetData`; все ошибки, вносимые непосредственно влияют на элементы массива.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCCollections#28](../../mfc/codesnippet/cpp/carray-class_7.cpp)]

##  <a name="getsize"></a>  CArray::GetSize

Возвращает размер массива.

```
INT_PTR GetSize() const;
```

### <a name="remarks"></a>Примечания

Так как индексы отсчитываются от нуля, размер равен 1, больше, чем наибольший индекс. Вызов этого метода создает тот же результат, как [CArray::GetCount](#getcount) метод.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCCollections#29](../../mfc/codesnippet/cpp/carray-class_8.cpp)]

##  <a name="getupperbound"></a>  CArray::GetUpperBound

Возвращает текущий верхнюю границу массива.

```
INT_PTR GetUpperBound() const;
```

### <a name="remarks"></a>Примечания

Так как массив индексы отсчитываются от нуля, эта функция возвращает значение 1 меньше, чем `GetSize`.

Условие `GetUpperBound( )` = -1 показывает, что массив не содержит элементов.

### <a name="example"></a>Пример

  См. в примере [CArray::GetAt](#getat).

##  <a name="insertat"></a>  CArray::InsertAt

Первая версия `InsertAt` вставляет один элемент (или несколько копий элемента) с указанным индексом в массиве.

```
void InsertAt(
    INT_PTR nIndex,
    ARG_TYPE newElement,
    INT_PTR nCount = 1);

void InsertAt(
    INT_PTR nStartIndex,
    CArray* pNewArray);
```

### <a name="parameters"></a>Параметры

*nIndex*<br/>
Целочисленный индекс, который может быть больше, чем значение, возвращенное `GetUpperBound`.

*ARG_TYPE*<br/>
Параметр шаблона, указывающий тип элементов в этом массиве.

*newElement*<br/>
Элемент следует поместить в этот массив.

*nCount*<br/>
Количество раз, когда этот элемент должен быть вставлен (по умолчанию — 1).

*nStartIndex*<br/>
Целочисленный индекс, который может быть больше, чем значение, возвращенное [GetUpperBound](#getupperbound).

*pNewArray*<br/>
Другой массив, содержащий элементы для добавления в этот массив.

### <a name="remarks"></a>Примечания

В процессе, он передвигается (путем увеличения индекс) существующий элемент в этот индекс и его смещает все элементы над ним.

Вторая версия вставляет все элементы из другого `CArray` коллекции, начиная с *nStartIndex* позиции.

`SetAt` Функции, напротив, заменяет один указанный элемент массива и не переместится какие-либо элементы.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCCollections#30](../../mfc/codesnippet/cpp/carray-class_9.cpp)]

##  <a name="isempty"></a>  CArray::IsEmpty

Определяет, является ли пустой массив.

```
BOOL IsEmpty() const;
```

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если массив не содержит элементов; в противном случае 0.

##  <a name="operator_at"></a>  CArray::operator \[\]

Эти подстрочного оператора являются удобным заменой [SetAt](#setat) и [GetAt](#getat) функции.

```
TYPE& operator[](int_ptr nindex);
const TYPE& operator[](int_ptr nindex) const;
```

### <a name="parameters"></a>Параметры

*ТИП*<br/>
Параметр шаблона, указывающий тип элементов в этом массиве.

*nIndex*<br/>
Индекс элемента для доступа.

### <a name="remarks"></a>Примечания

Первый оператор, вызывается для массивов, которые не являются **const**, может быть использована для (r-значение) справа или слева от оператора присваивания (l значение). Второй, вызывается для **const** массивы, может использоваться только в правой части.

Отладочная версия библиотеки утверждает, если индекс (либо слева или справа от оператора присваивания) выходит за границы.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCCollections#34](../../mfc/codesnippet/cpp/carray-class_10.cpp)]

##  <a name="relocateelements"></a>  CArray::RelocateElements

Перемещает данные в новый буфер, когда следует увеличить или уменьшить размер массива.

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

*pData*<br/>
Старый массив элементов.

*nCount*<br/>
Число элементов в массиве старого.

### <a name="remarks"></a>Примечания

*pNewData* всегда является достаточным для хранения всех *pData* элементов.

[CArray](../../mfc/reference/carray-class.md) реализация использует этот метод для копирования старые данные в новый буфер при следует увеличить или уменьшить размер массива (когда [SetSize](#setsize) или [FreeExtra](#freeextra) называются). Реализация по умолчанию просто копирует данные.

Для массивов, в которых элемент содержит указатель на один из членов или другой структурой содержит указатель на один из элементов массива указатели, не обновляются в обычный копирования. В этом случае указатели можно устранить путем реализации специализацией `RelocateElements` соответствующими типами. Вы также несете ответственность за копирование данных.

##  <a name="removeall"></a>  CArray::RemoveAll

Удаляет все элементы из этого массива.

```
void RemoveAll();
```

### <a name="remarks"></a>Примечания

Если массив уже является пустым, функция по-прежнему работает.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCCollections#31](../../mfc/codesnippet/cpp/carray-class_11.cpp)]

##  <a name="removeat"></a>  CArray::RemoveAt

Удаляет один или несколько элементов, начиная с указанного индекса в массиве.

```
void RemoveAt(
    INT_PTR nIndex,
    INT_PTR nCount = 1);
```

### <a name="parameters"></a>Параметры

*nIndex*<br/>
Целочисленный индекс, который больше или равно 0 и меньше или равно значение, возвращенное [GetUpperBound](#getupperbound).

*nCount*<br/>
Число удаляемых элементов.

### <a name="remarks"></a>Примечания

В процессе сдвигаются вниз всех элементов, расположенных выше удаленных элементов. Он уменьшает верхняя граница массива, но не освобождает память.

Если вы попытаетесь удалить больше элементов, чем содержащиеся в массиве выше точки удаления, утверждает отладочной версии библиотеки.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCCollections#32](../../mfc/codesnippet/cpp/carray-class_12.cpp)]

##  <a name="setat"></a>  CArray::SetAt

Задает элемент массива по указанному индексу.

```
void SetAt(INT_PTR nIndex, ARG_TYPE newElement);
```

### <a name="parameters"></a>Параметры

*nIndex*<br/>
Целочисленный индекс, который больше или равно 0 и меньше или равно значение, возвращенное [GetUpperBound](#getupperbound).

*ARG_TYPE*<br/>
Параметр шаблона, указывающий тип аргументов, используемая для ссылки на элементы массива.

*newElement*<br/>
Новое значение элемента для сохранения в указанной позиции.

### <a name="remarks"></a>Примечания

`SetAt` не вызовет массива расти. Используйте [SetAtGrow](#setatgrow) Если автоматическое увеличение массива.

Необходимо убедиться, что значение индекса представляет допустимую позицию в массиве. Если он выходит за границы, утверждает отладочной версии библиотеки.

### <a name="example"></a>Пример

  См. в примере [GetAt](#getat).

##  <a name="setatgrow"></a>  CArray::SetAtGrow

Задает элемент массива по указанному индексу.

```
void SetAtGrow(INT_PTR nIndex, ARG_TYPE newElement);
```

### <a name="parameters"></a>Параметры

*nIndex*<br/>
Целочисленный индекс, который больше или равно 0.

*ARG_TYPE*<br/>
Параметр шаблона, указывающий тип элементов в массиве.

*newElement*<br/>
Элемент, добавляемый в этот массив. Допускается значение NULL.

### <a name="remarks"></a>Примечания

Массив увеличивается автоматически при необходимости (то есть верхнюю границу корректируется для размещения нового элемента).

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCCollections#33](../../mfc/codesnippet/cpp/carray-class_13.cpp)]

##  <a name="setsize"></a>  CArray::SetSize

Устанавливает размер массива пустой или существующий; Выделяет память при необходимости.

```
void SetSize(
    INT_PTR nNewSize,
    INT_PTR nGrowBy = -1);
```

### <a name="parameters"></a>Параметры

*nNewSize*<br/>
Новый размер массива (число элементов). Должно быть больше или равно 0.

*nGrowBy*<br/>
Минимальное число слотов элемент для выделения, если увеличение размера не требуется.

### <a name="remarks"></a>Примечания

Если новый размер меньше, чем старого, массив усекается, а всю неиспользуемую память освобождается.

Эта функция используется для задания размера массива, перед началом использования массива. Если не использовать функцию `SetSize`, при добавлении элементов в массив он будет часто копироваться и для него снова и снова будет повторно выделяться память. Это может привести к ухудшению производительности и фрагментации памяти.

*NGrowBy* параметр влияет на внутренней памяти, хотя массива увеличивается. Его использование не влияет на размер массива, предоставленное [GetSize](#getsize) и [GetUpperBound](#getupperbound). Если используется значение по умолчанию, MFC выделяет памяти, вычисляется, чтобы избежать фрагментации памяти и оптимизации эффективности для большинства случаев.

### <a name="example"></a>Пример

  См. в примере [GetData](#getdata).

## <a name="see-also"></a>См. также

[Пример MFC СБОР](../../overview/visual-cpp-samples.md)<br/>
[Класс CObject](../../mfc/reference/cobject-class.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Класс CObArray](../../mfc/reference/cobarray-class.md)<br/>
[Вспомогательные функции классов коллекции](../../mfc/reference/collection-class-helpers.md)
