---
title: CArray-класс | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
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
dev_langs:
- CPP
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: f946a7af93a8cbf7a285f0c01ebd0512231f7b3f
ms.sourcegitcommit: c6b095c5f3de7533fd535d679bfee0503e5a1d91
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/26/2018
ms.locfileid: "36953392"
---
# <a name="carray-class"></a>CArray-класс
Поддерживает массивы, которые похожи на массивы C, но позволяет динамически снизить и уменьшаться по мере необходимости.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
template <class TYPE, class ARG_TYPE = const TYPE&>  
class CArray : public CObject  
```  
  
#### <a name="parameters"></a>Параметры  
 *ТИП*  
 Параметр шаблона, который указывает тип объектов, хранящихся в массиве. *Тип* — это параметр, возвращаемый `CArray`.  
  
 *ARG* *_* *ТИПА*  
 Параметр шаблона, определяющий тип аргумента, который используется для доступа к объектам, которые хранятся в массиве. Часто ссылку на *ТИПА*. *ARG_TYPE* — это параметр, передаваемый `CArray`.  
  
## <a name="members"></a>Участники  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CArray::CArray](#carray)|Создает пустой массив.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание:|  
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
  
|Имя|Описание:|  
|----------|-----------------|  
|[operator&#91;&#93;](#operator_at)|Получает или задает элемент с указанным индексом.|  
  
## <a name="remarks"></a>Примечания  
 Индексы массива всегда начинаются в позиции 0. Можно решить, будет ли исправить верхнюю границу или включить массив, в который разверните при добавлении элементов за пределами текущей привязки. Последовательно выделяется память для верхней границы, даже если некоторые элементы имеют значение null.  
  
> [!NOTE]
>  Большинство методов, размер которых `CArray` объекта или добавить элементы к нему используют [memcpy_s](../../c-runtime-library/reference/memcpy-s-wmemcpy-s.md) для перемещения элементов. Это является проблемой, так как `memcpy_s` не совместим с все объекты, которые требуют вызываемый конструктор. Если элементы в `CArray` не совместимы с `memcpy_s`, необходимо создать новый `CArray` соответствующего размера. После этого необходимо использовать [CArray::Copy](#copy) и [CArray::SetAt](#setat) для заполнения нового массива, так как эти методы используют оператор присваивания вместо `memcpy_s`.  
  
 Как и в случае с массивом C времени доступа к `CArray` индексированного элемента является константой и не зависит от размера массива.  
  
> [!TIP]
>  Перед работой с массивом используйте [SetSize](#setsize) определить его размер и выделить под него память. Если не использовать функцию `SetSize`, при добавлении элементов в массив он будет часто копироваться и для него снова и снова будет повторно выделяться память. Это может привести к ухудшению производительности и фрагментации памяти.  
  
 Если вам требуется дамп отдельных элементов в массиве, необходимо задать глубину [CDumpContext](../../mfc/reference/cdumpcontext-class.md) 1 или большего размера объекта.  
  
 Некоторые функции-члены этого класса вызова глобальных вспомогательные функции, следует настроить для использования большинства `CArray` класса. См. в разделе [вспомогательные функции классов коллекции](../../mfc/reference/collection-class-helpers.md) в разделе макросов MFC и глобальные переменные.  
  
 Массив производного класса аналогично вывода списка.  
  
 Дополнительные сведения об использовании `CArray`, см. в статье [коллекции](../../mfc/collections.md).  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CArray`  
  
## <a name="requirements"></a>Требования  
 `Header:` afxtempl.h  
  
##  <a name="add"></a>  CArray::Add  
 Добавляет новый элемент в конец массива, увеличение массива на 1.  
  
```  
INT_PTR Add(ARG_TYPE newElement);
```  
  
### <a name="parameters"></a>Параметры  
 *ARG_TYPE*  
 Параметр шаблона, указывающий тип аргументов, создание ссылок на элементы в этом массиве.  
  
 *newElement*  
 Элемент, добавляемый в этот массив.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Индекс добавленного элемента.  
  
### <a name="remarks"></a>Примечания  
 Если [SetSize](#setsize) был использован с *nGrowBy* значение больше 1, то дополнительная память может выделяться. Тем не менее значение верхней границы увеличивается на 1 только.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCCollections#22](../../mfc/codesnippet/cpp/carray-class_1.cpp)]  
  
##  <a name="append"></a>  CArray::Append  
 Вызовите эту функцию-член для добавления содержимого одного массива в другой конец.  
  
```  
INT_PTR Append(const CArray& src);
```  
  
### <a name="parameters"></a>Параметры  
 *src*  
 Источник элементов, добавляемых в массив.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Индекс первый добавленный элемент.  
  
### <a name="remarks"></a>Примечания  
 Массивы должны быть одного типа.  
  
 При необходимости `Append` может выделить дополнительный объем памяти для размещения элементов, добавляемый в конец массива.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCCollections#23](../../mfc/codesnippet/cpp/carray-class_2.cpp)]  
  
##  <a name="carray"></a>  CArray::CArray  
 Создает пустой массив.  
  
```  
CArray();
```  
  
### <a name="remarks"></a>Примечания  
 Массив увеличивает размер одного элемента за раз.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCCollections#24](../../mfc/codesnippet/cpp/carray-class_3.cpp)]  
  
##  <a name="copy"></a>  CArray::Copy  
 Используйте эту функцию-член для копирования элементов одного массива в другой.  
  
```  
void Copy(const CArray& src);
```  
  
### <a name="parameters"></a>Параметры  
 *src*  
 Источник элементов, копируемых в массив.  
  
### <a name="remarks"></a>Примечания  
 Вызовите эту функцию-член для перезаписи элементы одного массива с элементами другого массива.  
  
 **Копировать** не освобождает память, однако при необходимости `Copy` может выделить дополнительный объем памяти для размещения элементов, копируемых в массив.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCCollections#25](../../mfc/codesnippet/cpp/carray-class_4.cpp)]  
  
##  <a name="elementat"></a>  CArray::ElementAt  
 Возвращает временную ссылку на указанный элемент в массиве.  
  
```  
TYPE& ElementAt(INT_PTR nIndex);  
const TYPE& ElementAt(INT_PTR nIndex) const;  
```  
  
### <a name="parameters"></a>Параметры  
 *nIndex*  
 Целочисленный индекс, который больше или равно 0 и меньше или равно значения, возвращенного [GetUpperBound](#getupperbound).  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ссылка на элемент массива.  
  
### <a name="remarks"></a>Примечания  
 Он используется для реализации оператор слева от оператора присваивания для массивов.  
  
### <a name="example"></a>Пример  
  Далее приведен пример [GetSize](#getsize).  
  
##  <a name="freeextra"></a>  CArray::FreeExtra  
 Освобождает все дополнительную память, выделенную пока массива был увеличил.  
  
```  
void FreeExtra();
```  
  
### <a name="remarks"></a>Примечания  
 Эта функция не оказывает влияния на размер или верхней границы массива.  
  
### <a name="example"></a>Пример  
  Далее приведен пример [GetData](#getdata).  
  
##  <a name="getat"></a>  CArray::GetAt  
 Возвращает элемент массива по указанному индексу.  
  
```  
TYPE& GetAt(INT_PTR nIndex);  
const TYPE& GetAt(INT_PTR nIndex) const;  
```  
  
### <a name="parameters"></a>Параметры  
 *ТИП*  
 Параметр шаблона, задающее тип элементов массива.  
  
 *nIndex*  
 Целочисленный индекс, который больше или равно 0 и меньше или равно значения, возвращенного [GetUpperBound](#getupperbound).  
  
### <a name="return-value"></a>Возвращаемое значение  
 Элемент массива, в настоящее время по этому индексу.  
  
### <a name="remarks"></a>Примечания  
 Передача отрицательное значение или значение больше, чем значение, возвращаемое `GetUpperBound` приведет к утверждение, вызвавшее сбой.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCCollections#26](../../mfc/codesnippet/cpp/carray-class_5.cpp)]  
  
##  <a name="getcount"></a>  CArray::GetCount  
 Возвращает число элементов массива.  
  
```  
INT_PTR GetCount() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Количество элементов в массиве.  
  
### <a name="remarks"></a>Примечания  
 Этот метод вызывается для получения количества элементов в массиве. Так как индексы отсчитываются от нуля, размер составляет 1 больше, чем наибольший индекс. Вызов этого метода будет создавать один и тот же результат как [CArray::GetSize](#getsize) метод.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCCollections#27](../../mfc/codesnippet/cpp/carray-class_6.cpp)]  
  
##  <a name="getdata"></a>  CArray::GetData  
 Используйте эту функцию-член для прямого доступа к элементам в массиве.  
  
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
 Если нет элементов, `GetData` возвращает значение null.  
  
 При прямой доступ к элементам массива может помочь вам работать быстрее, соблюдайте осторожность при вызове `GetData`; все ошибки, внесенные непосредственно влияют на элементы массива.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCCollections#28](../../mfc/codesnippet/cpp/carray-class_7.cpp)]  
  
##  <a name="getsize"></a>  CArray::GetSize  
 Возвращает размер массива.  
  
```  
INT_PTR GetSize() const;  
```  
  
### <a name="remarks"></a>Примечания  
 Так как индексы отсчитываются от нуля, размер составляет 1 больше, чем наибольший индекс. Вызов этого метода будет создавать один и тот же результат как [CArray::GetCount](#getcount) метод.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCCollections#29](../../mfc/codesnippet/cpp/carray-class_8.cpp)]  
  
##  <a name="getupperbound"></a>  CArray::GetUpperBound  
 Возвращает текущий верхнюю границу данного массива.  
  
```  
INT_PTR GetUpperBound() const;  
```  
  
### <a name="remarks"></a>Примечания  
 Так как индексы массива отсчитываются от нуля, эта функция возвращает значение 1 меньше, чем `GetSize`.  
  
 Условие `GetUpperBound( )` = -1 означает, что массив не содержит элементов.  
  
### <a name="example"></a>Пример  
  Далее приведен пример [CArray::GetAt](#getat).  
  
##  <a name="insertat"></a>  CArray::InsertAt  
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
 *nIndex*  
 Целое значение индекса, может быть больше, чем значение, возвращаемое `GetUpperBound`.  
  
 *ARG_TYPE*  
 Параметр шаблона, указывающий тип элементов в этом массиве.  
  
 *newElement*  
 Элемент должен располагаться в этом массиве.  
  
 *nCount*  
 Количество раз, когда этот элемент должен быть вставлен (по умолчанию-1).  
  
 *nStartIndex*  
 Целое значение индекса, может быть больше, чем значение, возвращаемое [GetUpperBound](#getupperbound).  
  
 *pNewArray*  
 Другой массив, содержащий элементы для добавления в этот массив.  
  
### <a name="remarks"></a>Примечания  
 В процессе его передвигается (путем увеличения или уменьшения индекс) существующий элемент в этот индекс и его передвигается элементы над ним.  
  
 Вторая версия вставляет все элементы из другого `CArray` коллекции, начиная с *nStartIndex* позиции.  
  
 `SetAt` Функции, напротив, заменяет один элемент указанного массива и не переместится какие-либо элементы.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCCollections#30](../../mfc/codesnippet/cpp/carray-class_9.cpp)]  
  
##  <a name="isempty"></a>  CArray::IsEmpty  
 Определяет, пуст ли массив.  
  
```  
BOOL IsEmpty() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если массив не содержит элементов; в противном случае — 0.  
  
##  <a name="operator_at"></a>  CArray::operator \[\]  
 Все эти подстрочного оператора удобный заменяют [SetAt](#setat) и [GetAt](#getat) функции.  
  
```  
TYPE& operator[](int_ptr nindex);  
const TYPE& operator[](int_ptr nindex) const;  
```  
  
### <a name="parameters"></a>Параметры  
 *ТИП*  
 Параметр шаблона, указывающий тип элементов в этом массиве.  
  
 *nIndex*  
 Индекс элемента, должен быть предоставлен доступ.  
  
### <a name="remarks"></a>Примечания  
 Первый оператор вызывается для массивов, которые не являются **const**, могут быть использованы в правом (r-значение) или (l значение) слева от оператора присваивания. Второе, вызывается для **const** массивов, могут быть использованы только в правой части окна.  
  
 Отладочная версия библиотеки утверждения, если индекс (либо левой или правой части оператора присваивания) выходит за границы.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCCollections#34](../../mfc/codesnippet/cpp/carray-class_10.cpp)]  
  
##  <a name="relocateelements"></a>  CArray::RelocateElements  
 Перемещает данные в новый буфер при массива должен разрастании или сжатии.  
  
```  
template<class TYPE, class ARG_TYPE>  
AFX_INLINE void CArray<TYPE, ARG_TYPE>::RelocateElements(
    TYPE* pNewData,  
    const TYPE* pData,  
    INT_PTR nCount);
```  
  
### <a name="parameters"></a>Параметры  
 *pNewData*  
 Новый буфер массив элементов.  
  
 *pData*  
 Старый массив элементов.  
  
 *nCount*  
 Число элементов в массиве старого.  
  
### <a name="remarks"></a>Примечания  
 *pNewData* всегда является достаточным для хранения всех *pData* элементов.  
  
 [CArray](../../mfc/reference/carray-class.md) реализация использует этот метод для копирования старые данные в новый буфер при массива должен увеличения или сжатия (когда [SetSize](#setsize) или [FreeExtra](#freeextra) называются). Реализация по умолчанию просто копирует данные.  
  
 Для массивов, в которых элемент содержит указатель на один из членов или другую структуру содержит указатель на один из элементов массива указатели, не обновляются в обычный копирования. В этом случае можно исправить путем реализации специализацией указатели `RelocateElements` соответствующими типами. Также вы отвечаете за копировать данные.  
  
##  <a name="removeall"></a>  CArray::RemoveAll  
 Удаляет все элементы из этого массива.  
  
```  
void RemoveAll();
```  
  
### <a name="remarks"></a>Примечания  
 Если массив уже является пустым, функция все еще работает.  
  
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
 *nIndex*  
 Целочисленный индекс, который больше или равно 0 и меньше или равно значения, возвращенного [GetUpperBound](#getupperbound).  
  
 *nCount*  
 Число удаляемых элементов.  
  
### <a name="remarks"></a>Примечания  
 В процессе сдвигаются вниз элементы выше удаленных элементов. Он уменьшает верхняя граница массива, но не освобождает память.  
  
 Если вы попытаетесь удалить элементы, содержащиеся в массиве над точкой удаления, отладочная версия библиотеки утверждения.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCCollections#32](../../mfc/codesnippet/cpp/carray-class_12.cpp)]  
  
##  <a name="setat"></a>  CArray::SetAt  
 Задает элемент массива по указанному индексу.  
  
```  
void SetAt(INT_PTR nIndex, ARG_TYPE newElement);
```  
  
### <a name="parameters"></a>Параметры  
 *nIndex*  
 Целочисленный индекс, который больше или равно 0 и меньше или равно значения, возвращенного [GetUpperBound](#getupperbound).  
  
 *ARG_TYPE*  
 Параметр шаблона, указывающий тип аргументы, используемые для ссылки на элементы массива.  
  
 *newElement*  
 Новое значение элемента для сохранения в указанной позиции.  
  
### <a name="remarks"></a>Примечания  
 `SetAt` не вызовет массива может увеличиваться. Используйте [SetAtGrow](#setatgrow) Если разрешено автоматическое увеличение массива.  
  
 Необходимо убедиться, что значение индекса представляет является допустимой позицией в массиве. Если вне допустимых границ, отладочная версия библиотеки утверждения.  
  
### <a name="example"></a>Пример  
  Далее приведен пример [GetAt](#getat).  
  
##  <a name="setatgrow"></a>  CArray::SetAtGrow  
 Задает элемент массива по указанному индексу.  
  
```  
void SetAtGrow(INT_PTR nIndex, ARG_TYPE newElement);
```  
  
### <a name="parameters"></a>Параметры  
 *nIndex*  
 Целочисленный индекс, который больше или равно 0.  
  
 *ARG_TYPE*  
 Параметр шаблона, указывающий тип элементов в массиве.  
  
 *newElement*  
 Элемент, добавляемый в этот массив. Объект **NULL** является допустимым значением.  
  
### <a name="remarks"></a>Примечания  
 При необходимости массива увеличился автоматически (то есть, верхняя граница корректируется для размещения нового элемента).  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCCollections#33](../../mfc/codesnippet/cpp/carray-class_13.cpp)]  
  
##  <a name="setsize"></a>  CArray::SetSize  
 Устанавливает размер массива пустой или существующей; Выделяет память при необходимости.  
  
```  
void SetSize(
    INT_PTR nNewSize,  
    INT_PTR nGrowBy = -1);
```  
  
### <a name="parameters"></a>Параметры  
 *nNewSize*  
 Новый размер массива (число элементов). Должно быть больше или равно 0.  
  
 *nGrowBy*  
 Минимальное число слотов элемент для выделения, если увеличение размера не требуется.  
  
### <a name="remarks"></a>Примечания  
 Если новый размер меньше, чем старого, массив усекается, а всю неиспользуемую память освобождается.  
  
 Эта функция используется для установки размера массива, прежде чем начать использование массива. Если не использовать функцию `SetSize`, при добавлении элементов в массив он будет часто копироваться и для него снова и снова будет повторно выделяться память. Это может привести к ухудшению производительности и фрагментации памяти.  
  
 *NGrowBy* параметр влияет на выделения внутренней памяти, пока увеличение массива. Его использование никогда не влияет на размер массива, сообщаемые [GetSize](#getsize) и [GetUpperBound](#getupperbound). Если используется значение по умолчанию, MFC выделяет память таким образом, для уменьшения фрагментации памяти и оптимизации эффективности для большинства случаев.  
  
### <a name="example"></a>Пример  
  Далее приведен пример [GetData](#getdata).  
  
## <a name="see-also"></a>См. также  
 [Пример MFC СБОРА](../../visual-cpp-samples.md)   
 [CObject-класс](../../mfc/reference/cobject-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Класс CObArray](../../mfc/reference/cobarray-class.md)   
 [Вспомогательные функции классов коллекции](../../mfc/reference/collection-class-helpers.md)
