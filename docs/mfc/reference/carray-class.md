---
title: "CArray-класс | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CArray
dev_langs:
- C++
helpviewer_keywords:
- CArray class
- arrays [C++], classes
- templates, collection classes
- collection classes, template-based
ms.assetid: fead8b00-4cfd-4625-ad0e-251df62ba92f
caps.latest.revision: 33
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: bac8e08540ffead565d1097c6ef1efcae5e606c2
ms.lasthandoff: 02/24/2017

---
# <a name="carray-class"></a>CArray-класс
Поддерживает массивы, которые похожи на массивы C, но может динамически увеличиваться и уменьшаться в случае необходимости.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
template <class TYPE, class ARG_TYPE = const TYPE&>  
class CArray : public CObject  
```  
  
#### <a name="parameters"></a>Параметры  
 `TYPE`  
 Параметр шаблона, который указывает тип объектов, хранящихся в массиве. `TYPE`— Это параметр, возвращаемый `CArray`.  
  
 `ARG` *_* `TYPE`  
 Параметр шаблона, определяющий тип аргумента, который используется для доступа к объектам, которые хранятся в массиве. Часто ссылку на `TYPE`. `ARG_TYPE`— параметр, который передается в `CArray`.  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CArray::CArray](#carray)|Создает пустой массив.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CArray::Add](#add)|Добавляет элемент в конец массива. При необходимости размер массива увеличивается.|  
|[CArray::Append](#append)|Добавляет другой массив массива. размер массива увеличивается при необходимости|  
|[CArray::Copy](#copy)|Копирует другой массив в этот массив. При необходимости размер массива увеличивается.|  
|[CArray::ElementAt](#elementat)|Возвращает временную ссылку на указатель элемента в массиве.|  
|[CArray::FreeExtra](#freeextra)|Освобождает всю неиспользуемую память сверх текущей верхней границы.|  
|[CArray::GetAt](#getat)|Возвращает значение по указанному индексу.|  
|[CArray::GetCount](#getcount)|Возвращает количество элементов в массиве.|  
|[CArray::GetData](#getdata)|Разрешает доступ к элементам в массиве. Может быть **NULL**.|  
|[CArray::GetSize](#getsize)|Возвращает количество элементов в массиве.|  
|[CArray::GetUpperBound](#getupperbound)|Возвращает самый большой допустимый индекс.|  
|[CArray::InsertAt](#insertat)|Вставляет элемент (или все элементы в другом массиве) по указанному индексу.|  
|[CArray::IsEmpty](#isempty)|Определяет, пуст ли массив.|  
|[CArray::RemoveAll](#removeall)|Удаляет все элементы из этого массива.|  
|[CArray::RemoveAt](#removeat)|Удаляет элемент по указанному индексу.|  
|[CArray::SetAt](#setat)|Задает значение для указанного индекса. Размер массива не увеличивается.|  
|[CArray::SetAtGrow](#setatgrow)|Задает значение для указанного индекса. При необходимости размер массива увеличивается.|  
|[CArray::SetSize](#setsize)|Задает число элементов, которые будут храниться в этом массиве.|  
  
### <a name="public-operators"></a>Открытые операторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[operator&#91;&#93;](#operator_at)|Получает или задает элемент с указанным индексом.|  
  
## <a name="remarks"></a>Примечания  
 Индексы массива всегда начинаются с позиции 0. Вы можете исправить верхнюю границу или включить массива для развертывания при добавлении элементов за пределами текущей привязки. Память выделяется последовательно с верхней границей, даже если некоторые элементы имеют значение null.  
  
> [!NOTE]
>  Большинство методов, размер которых `CArray` объекта или добавить элементы к нему используют [memcpy_s](../../c-runtime-library/reference/memcpy-s-wmemcpy-s.md) для перемещения элементов. Это является проблемой, поскольку `memcpy_s` не совместим с любые объекты, требующие вызываемый конструктор. Если элементы в `CArray` не совместимы с `memcpy_s`, необходимо создать новый `CArray` соответствующего размера. После этого необходимо использовать [CArray::Copy](#copy) и [CArray::SetAt](#setat) для заполнения нового массива, так как эти методы используют оператор присваивания, а не `memcpy_s`.  
  
 Как и в случае с массивом C времени доступа к `CArray` индексированного элемента является постоянным и не зависит от размера массива.  
  
> [!TIP]
>  Перед работой с массивом используйте [SetSize](#setsize) определить его размер и выделить под него память. Если не использовать функцию `SetSize`, при добавлении элементов в массив он будет часто копироваться и для него снова и снова будет повторно выделяться память. Это может привести к ухудшению производительности и фрагментации памяти.  
  
 Если вам требуется дамп отдельных элементов в массиве, необходимо задать глубину [CDumpContext](../../mfc/reference/cdumpcontext-class.md) объекта 1 или больше.  
  
 Некоторые функции-члены этого класса вызова глобальных вспомогательные функции, необходимо настроить для большинства случаев из `CArray` класса. См. в разделе [вспомогательные функции классов коллекции](../../mfc/reference/collection-class-helpers.md) в разделе макросов MFC и глобальные переменные.  
  
 Массив производного класса аналогично список наследования.  
  
 Дополнительные сведения об использовании `CArray`, см. в статье [коллекции](../../mfc/collections.md).  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CArray`  
  
## <a name="requirements"></a>Требования  
 `Header:`afxtempl.h  
  
##  <a name="a-nameadda--carrayadd"></a><a name="add"></a>CArray::Add  
 Добавляет новый элемент в конец массива, увеличение массива на 1.  
  
```  
INT_PTR Add(ARG_TYPE newElement);
```  
  
### <a name="parameters"></a>Параметры  
 `ARG_TYPE`  
 Параметр шаблона, указав тип ссылок на элементы в этот массив аргументов.  
  
 `newElement`  
 Элемент, добавляемый в этот массив.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Индекс добавленного элемента.  
  
### <a name="remarks"></a>Примечания  
 Если [SetSize](#setsize) был использован с `nGrowBy` значение больше 1, то дополнительная память может выделяться. Тем не менее верхнюю границу только 1 будет увеличиваться.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCCollections&#22;](../../mfc/codesnippet/cpp/carray-class_1.cpp)]  
  
##  <a name="a-nameappenda--carrayappend"></a><a name="append"></a>CArray::Append  
 Вызовите эту функцию-член для добавления содержимого одного массива в конец другого.  
  
```  
INT_PTR Append(const CArray& src);
```  
  
### <a name="parameters"></a>Параметры  
 *src*  
 Источник элементов, добавляемый в массив.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Индекс первый добавленный элемент.  
  
### <a name="remarks"></a>Примечания  
 Массивы должны быть одного типа.  
  
 При необходимости **Append** может выделить дополнительную память для размещения элементов, добавляемый в конец массива.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCCollections&#23;](../../mfc/codesnippet/cpp/carray-class_2.cpp)]  
  
##  <a name="a-namecarraya--carraycarray"></a><a name="carray"></a>CArray::CArray  
 Создает пустой массив.  
  
```  
CArray();
```  
  
### <a name="remarks"></a>Примечания  
 Массив растет одного элемента за раз.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCCollections&#24;](../../mfc/codesnippet/cpp/carray-class_3.cpp)]  
  
##  <a name="a-namecopya--carraycopy"></a><a name="copy"></a>CArray::Copy  
 Используйте эту функцию-член для копирования элементов одного массива в другой.  
  
```  
void Copy(const CArray& src);
```  
  
### <a name="parameters"></a>Параметры  
 *src*  
 Источник копируемых в массив элементов.  
  
### <a name="remarks"></a>Примечания  
 Вызовите эту функцию-член для перезаписи элементы одного массива с элементами другого массива.  
  
 **Копировать** не освобождает память, однако при необходимости **копирования** может выделить дополнительную память для размещения элементов, копируемых в массив.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCCollections&#25;](../../mfc/codesnippet/cpp/carray-class_4.cpp)]  
  
##  <a name="a-nameelementata--carrayelementat"></a><a name="elementat"></a>CArray::ElementAt  
 Возвращает временную ссылку на указанный элемент в массиве.  
  
```  
TYPE& ElementAt(INT_PTR nIndex);  
const TYPE& ElementAt(INT_PTR nIndex) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `nIndex`  
 Целочисленный индекс, который больше или равно 0 и меньше или равно значение, возвращаемое [GetUpperBound](#getupperbound).  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ссылка на элемент массива.  
  
### <a name="remarks"></a>Примечания  
 Он используется для реализации оператор присваивания слева для массивов.  
  
### <a name="example"></a>Пример  
  В примере показано [GetSize](#getsize).  
  
##  <a name="a-namefreeextraa--carrayfreeextra"></a><a name="freeextra"></a>CArray::FreeExtra  
 Освобождает любой дополнительной памяти, выделенной хотя массив был растет.  
  
```  
void FreeExtra();
```  
  
### <a name="remarks"></a>Примечания  
 Эта функция не влияет на размер или верхней границы массива.  
  
### <a name="example"></a>Пример  
  В примере показано [GetData](#getdata).  
  
##  <a name="a-namegetata--carraygetat"></a><a name="getat"></a>CArray::GetAt  
 Возвращает элемент массива с заданным индексом.  
  
```  
TYPE& GetAt(INT_PTR nIndex);  
const TYPE& GetAt(INT_PTR nIndex) const;  
```  
  
### <a name="parameters"></a>Параметры  
 *ТИП*  
 Параметр шаблона, задающее тип элементов массива.  
  
 `nIndex`  
 Целочисленный индекс, который больше или равно 0 и меньше или равно значение, возвращаемое [GetUpperBound](#getupperbound).  
  
### <a name="return-value"></a>Возвращаемое значение  
 Элемент массива в данный момент по этому индексу.  
  
### <a name="remarks"></a>Примечания  
 Передача отрицательное значение или значение больше, чем значение, возвращаемое `GetUpperBound` приведет к ошибочного утверждения.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCCollections&#26;](../../mfc/codesnippet/cpp/carray-class_5.cpp)]  
  
##  <a name="a-namegetcounta--carraygetcount"></a><a name="getcount"></a>CArray::GetCount  
 Возвращает число элементов массива.  
  
```  
INT_PTR GetCount() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Количество элементов в массиве.  
  
### <a name="remarks"></a>Примечания  
 Этот метод используется для получения числа элементов в массиве. Так как индексы отсчитываются от нуля, размер составляет 1 больше наибольшего индекса. Вызов этого метода будет создавать тот же результат, как [CArray::GetSize](#getsize) метод.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCCollections&#27;](../../mfc/codesnippet/cpp/carray-class_6.cpp)]  
  
##  <a name="a-namegetdataa--carraygetdata"></a><a name="getdata"></a>CArray::GetData  
 Используйте эту функцию-член для прямого доступа к элементам массива.  
  
```  
const TYPE* GetData() const; 
TYPE* GetData();
```  
  
### <a name="parameters"></a>Параметры  
 *ТИП*  
 Параметр шаблона, задающее тип элементов массива.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на элемент массива.  
  
### <a name="remarks"></a>Примечания  
 Если элементы не доступны, `GetData` возвращает значение null.  
  
 Хотя прямой доступ к элементам массива помогает работать быстрее, будьте осторожны при вызове `GetData`; все ошибки, внесенные непосредственно влияют на элементы массива.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCCollections&#28;](../../mfc/codesnippet/cpp/carray-class_7.cpp)]  
  
##  <a name="a-namegetsizea--carraygetsize"></a><a name="getsize"></a>CArray::GetSize  
 Возвращает размер массива.  
  
```  
INT_PTR GetSize() const;  
```  
  
### <a name="remarks"></a>Примечания  
 Так как индексы отсчитываются от нуля, размер составляет 1 больше наибольшего индекса. Вызов этого метода будет создавать тот же результат, как [CArray::GetCount](#getcount) метод.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCCollections&#29;](../../mfc/codesnippet/cpp/carray-class_8.cpp)]  
  
##  <a name="a-namegetupperbounda--carraygetupperbound"></a><a name="getupperbound"></a>CArray::GetUpperBound  
 Возвращает текущее верхней границы данного массива.  
  
```  
INT_PTR GetUpperBound() const;  
```  
  
### <a name="remarks"></a>Примечания  
 Так как массив индексы отсчитываются от нуля, эта функция возвращает значение 1 меньше, чем `GetSize`.  
  
 Условие **(GetUpperBound)** = -1 указывает, что массив не содержит элементов.  
  
### <a name="example"></a>Пример  
  В примере показано [CArray::GetAt](#getat).  
  
##  <a name="a-nameinsertata--carrayinsertat"></a><a name="insertat"></a>CArray::InsertAt  
 Первая версия `InsertAt` вставляет один элемент (или несколько копий элемента) по указанному индексу в массиве.  
  
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
 `nIndex`  
 Целое значение индекса, может быть больше, чем значение, возвращаемое `GetUpperBound`.  
  
 `ARG_TYPE`  
 Параметр шаблона, указав тип элементов в этом массиве.  
  
 `newElement`  
 Элемент следует поместить в этот массив.  
  
 `nCount`  
 Количество раз, когда этот элемент должен быть вставлен (по умолчанию 1).  
  
 `nStartIndex`  
 Целое значение индекса, может быть больше, чем значение, возвращаемое [GetUpperBound](#getupperbound).  
  
 `pNewArray`  
 Другой массив, содержащий элементы для добавления в этот массив.  
  
### <a name="remarks"></a>Примечания  
 В процессе его передвигается (путем увеличения или уменьшения индекс) существующего элемента в этот индекс и передвигается элементы над ним.  
  
 Вторая версия вставляет все элементы из другого `CArray` коллекции, начиная с `nStartIndex` позиции.  
  
 `SetAt` Функции, напротив, заменяет один элемент указанного массива и не переместится какие-либо элементы.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCCollections&#30;](../../mfc/codesnippet/cpp/carray-class_9.cpp)]  
  
##  <a name="a-nameisemptya--carrayisempty"></a><a name="isempty"></a>CArray::IsEmpty  
 Определяет, пуст ли массив.  
  
```  
BOOL IsEmpty() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если массив не содержит элементов; в противном случае — 0.  
  
##  <a name="a-nameoperatorata--carrayoperator-"></a><a name="operator_at"></a>CArray::operator\[\]  
 Все эти подстрочного оператора удобный заменяют [SetAt](#setat) и [GetAt](#getat) функции.  
  
```  
TYPE& operator[](int_ptr nindex);  
const TYPE& operator[](int_ptr nindex) const;  
```  
  
### <a name="parameters"></a>Параметры  
 *ТИП*  
 Параметр шаблона, указав тип элементов в этом массиве.  
  
 `nIndex`  
 Индекс элемента для доступа.  
  
### <a name="remarks"></a>Примечания  
 Первый оператор вызывается для массивов, которые не **const**, может быть использовано для вправо (r-значение) или (l значение) слева от оператора присваивания. Второй, вызывается для **const** массивов, могут использоваться только справа.  
  
 Отладочная версия библиотеки утверждает, если индекс (либо слева или справа от оператора присваивания) выходит за допустимые пределы.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCCollections&#34;](../../mfc/codesnippet/cpp/carray-class_10.cpp)]  
  
##  <a name="a-namerelocateelementsa--carrayrelocateelements"></a><a name="relocateelements"></a>CArray::RelocateElements  
 Перемещает данные в новый буфер, когда массив должен увеличения или уменьшения.  
  
```  
template<class TYPE, class ARG_TYPE>  
AFX_INLINE void CArray<TYPE, ARG_TYPE>::RelocateElements(
    TYPE* pNewData,  
    const TYPE* pData,  
    INT_PTR nCount);
```  
  
### <a name="parameters"></a>Параметры  
 `pNewData`  
 Новый буфер для массива элементов.  
  
 `pData`  
 Старый массив элементов.  
  
 `nCount`  
 Число элементов в массиве старого.  
  
### <a name="remarks"></a>Примечания  
 `pNewData`всегда является достаточным для хранения всех `pData` элементов.  
  
 [CArray](../../mfc/reference/carray-class.md) реализация использует этот метод для копирования старые данные новый буфер, когда массив должен увеличения или сжатия (если [SetSize](#setsize) или [FreeExtra](#freeextra) называются). Реализация по умолчанию просто копирует данные.  
  
 Для массивов, в которых элемент содержит указатель на один из своих членов или другую структуру содержит указатель на один из элементов массива указатели не обновляются в обычный копии. В этом случае можно исправить указатели, реализовав специализации `RelocateElements` соответствующими типами. Вы также несете ответственность за копированием данных.  
  
##  <a name="a-nameremovealla--carrayremoveall"></a><a name="removeall"></a>CArray::RemoveAll  
 Удаляет все элементы из этого массива.  
  
```  
void RemoveAll();
```  
  
### <a name="remarks"></a>Примечания  
 Если массив пуст, уже, функция по-прежнему работает.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCCollections&#31;](../../mfc/codesnippet/cpp/carray-class_11.cpp)]  
  
##  <a name="a-nameremoveata--carrayremoveat"></a><a name="removeat"></a>CArray::RemoveAt  
 Удаляет один или несколько элементов, начиная с указанного индекса в массиве.  
  
```  
void RemoveAt(
    INT_PTR nIndex,  
    INT_PTR nCount = 1);
```  
  
### <a name="parameters"></a>Параметры  
 `nIndex`  
 Целочисленный индекс, который больше или равно 0 и меньше или равно значение, возвращаемое [GetUpperBound](#getupperbound).  
  
 `nCount`  
 Число удаляемых элементов.  
  
### <a name="remarks"></a>Примечания  
 В процессе сдвигаются вниз элементы выше удаленных элементов. Он уменьшает верхняя граница массива, но не освобождает память.  
  
 При попытке удалить больше элементов, чем содержится в массиве над точкой удаления утверждает отладочная версия библиотеки.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCCollections&#32;](../../mfc/codesnippet/cpp/carray-class_12.cpp)]  
  
##  <a name="a-namesetata--carraysetat"></a><a name="setat"></a>CArray::SetAt  
 Задает элемент массива с заданным индексом.  
  
```  
void SetAt(INT_PTR nIndex, ARG_TYPE newElement);
```  
  
### <a name="parameters"></a>Параметры  
 `nIndex`  
 Целочисленный индекс, который больше или равно 0 и меньше или равно значение, возвращаемое [GetUpperBound](#getupperbound).  
  
 `ARG_TYPE`  
 Параметр шаблона, указывающие тип аргументы, используемые для ссылки на элементы массива.  
  
 `newElement`  
 Новое значение элемента для хранения в указанной позиции.  
  
### <a name="remarks"></a>Примечания  
 `SetAt`не вызовет увеличение массива. Используйте [SetAtGrow](#setatgrow) Если разрешено автоматическое увеличение массива.  
  
 Необходимо убедиться, что значение индекса представляет допустимую позицию в массиве. Если он выходит за допустимые пределы, отладочная версия библиотеки утверждения.  
  
### <a name="example"></a>Пример  
  В примере показано [GetAt](#getat).  
  
##  <a name="a-namesetatgrowa--carraysetatgrow"></a><a name="setatgrow"></a>CArray::SetAtGrow  
 Задает элемент массива с заданным индексом.  
  
```  
void SetAtGrow(INT_PTR nIndex, ARG_TYPE newElement);
```  
  
### <a name="parameters"></a>Параметры  
 `nIndex`  
 Целочисленный индекс, который больше или равно 0.  
  
 `ARG_TYPE`  
 Параметр шаблона, указав тип элементов в массиве.  
  
 `newElement`  
 Элемент, добавляемый в этот массив. Объект **NULL** допустимое значение.  
  
### <a name="remarks"></a>Примечания  
 При необходимости массива увеличивается автоматически (то есть верхняя граница корректируется для размещения нового элемента).  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCCollections&#33;](../../mfc/codesnippet/cpp/carray-class_13.cpp)]  
  
##  <a name="a-namesetsizea--carraysetsize"></a><a name="setsize"></a>CArray::SetSize  
 Устанавливает размер пустой или существующего массива; Выделяет память при необходимости.  
  
```  
void SetSize(
    INT_PTR nNewSize,  
    INT_PTR nGrowBy = -1);
```  
  
### <a name="parameters"></a>Параметры  
 `nNewSize`  
 Новый размер массива (число элементов). Должен быть больше или равно 0.  
  
 `nGrowBy`  
 Минимальное количество элемент слотов для выделения, если увеличение размера не требуется.  
  
### <a name="remarks"></a>Примечания  
 Если новый размер меньше, чем старого, массив усекается, а всю неиспользуемую память освобождается.  
  
 Эту функцию можно используйте для установки размера массива перед использованием массива. Если не использовать функцию `SetSize`, при добавлении элементов в массив он будет часто копироваться и для него снова и снова будет повторно выделяться память. Это может привести к ухудшению производительности и фрагментации памяти.  
  
 `nGrowBy` Параметр влияет на внутренней области памяти, хотя увеличение массива. Его использование никогда не влияет на размер массива, сообщаемые [GetSize](#getsize) и [GetUpperBound](#getupperbound). Если используется значение по умолчанию MFC выделяет памяти, вычисляется, чтобы избежать фрагментации памяти и оптимизации эффективности для большинства случаев.  
  
### <a name="example"></a>Пример  
  В примере показано [GetData](#getdata).  
  
## <a name="see-also"></a>См. также  
 [Пример MFC сбор данных](../../visual-cpp-samples.md)   
 [CObject-класс](../../mfc/reference/cobject-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Класс CObArray](../../mfc/reference/cobarray-class.md)   
 [Вспомогательные функции классов коллекции](../../mfc/reference/collection-class-helpers.md)

