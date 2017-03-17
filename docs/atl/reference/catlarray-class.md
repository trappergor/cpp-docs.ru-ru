---
title: "Класс CAtlArray | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CAtlArray
- ATLCOLL/ATL::CAtlArray
- ATLCOLL/ATL::Add
- ATLCOLL/ATL::Append
- ATLCOLL/ATL::AssertValid
- ATLCOLL/ATL::CAtlArray
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
dev_langs:
- C++
helpviewer_keywords:
- CAtlArray class
ms.assetid: 0b503aa8-2357-40af-a326-6654bf1da098
caps.latest.revision: 21
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
ms.openlocfilehash: 5fe987e428fc0dcf3e40bfb16aa26bcb90339aff
ms.lasthandoff: 02/24/2017

---
# <a name="catlarray-class"></a>Класс CAtlArray
Этот класс реализует объект массива.  
  
## <a name="syntax"></a>Синтаксис  
  
```
template<typename E, class ETraits = CElementTraits<E>>
class CAtlArray
```  
  
#### <a name="parameters"></a>Параметры  
 *E*  
 Тип данных для сохранения в массиве.  
  
 *ETraits*  
 Код, используемый для копирования или перемещения элементов.  
  
## <a name="members"></a>Члены  
  
### <a name="methods"></a>Методы  
  
|||  
|-|-|  
|[Добавить](#add)|Вызовите этот метод, чтобы добавить элемент в массиве.|  
|[Добавить](#append)|Этот метод используется для добавления содержимого одного массива в конец другого.|  
|[AssertValid](#assertvalid)|Вызовите этот метод, чтобы подтвердить допустимость объекта массива.|  
|[CAtlArray](#catlarray)|Конструктор.|  
|[~ CAtlArray](#dtor)|Деструктор|  
|[Копировать](#copy)|Этот метод служит для копирования элементов одного массива в другой.|  
|[FreeExtra](#freeextra)|Вызовите этот метод, чтобы удалить все пустые элементы из массива.|  
|[GetAt](#getat)|Этот метод вызывается для получения отдельного элемента из объекта массива.|  
|[GetCount](#getcount)|Этот метод используется для возврата числа элементов, хранящихся в массиве.|  
|[GetData](#getdata)|Этот метод используется для возврата указателя на первый элемент в массиве.|  
|[InsertArrayAt](#insertarrayat)|Этот метод служит для вставки одного массива в другой.|  
|[InsertAt](#insertat)|Этот метод вызывается для вставки нового элемента (или несколько копий элемента) в объект array.|  
|[IsEmpty](#isempty)|Этот метод используется для проверки, если массив пуст.|  
|[RemoveAll](#removeall)|Этот метод используется для удаления всех элементов из объекта массива.|  
|[Метод RemoveAt](#removeat)|Вызовите этот метод, чтобы удалить один или несколько элементов из массива.|  
|[SetAt](#setat)|Этот метод используется для задания значения элемента объекта массива.|  
|[SetAtGrow](#setatgrow)|Этот метод используется для задания значения элемента объекта массива, расширение массива, при необходимости.|  
|[SetCount](#setcount)|Вызовите этот метод, чтобы задать размер объекта массива.|  
  
### <a name="operators"></a>Операторы  
  
|||  
|-|-|  
|[оператор&#91;&#93;](#operator_at)|Вызовите этот оператор возвращает ссылку на элемент в массиве.|  

  
### <a name="typedefs"></a>Typedefs  
  
|||  
|-|-|  
|[INARGTYPE](#inargtype)|Тип данных, используемый для добавления элементов в массив.|  
|[OUTARGTYPE](#outargtype)|Тип данных, использовать для получения элементов из массива.|  
  
## <a name="remarks"></a>Примечания  
 **CAtlArray** предоставляет методы для создания и управления массив элементов типа, определяемого пользователем. Несмотря на сходство с стандартные массивы C **CAtlArray** объект динамического сжатия и уменьшаться по мере необходимости. Индекс массива всегда начинается с позиции 0, и верхняя граница может фиксированной или разрешено разверните добавляются новые элементы.  
  
 Для массивов с небольшим числом элементов класса ATL [CSimpleArray](../../atl/reference/csimplearray-class.md) может использоваться.  
  
 **CAtlArray** тесно связаны с MFC **CArray** класса и будет работать в проект MFC, хотя и без поддержки сериализации.  
  
 Дополнительные сведения см. в разделе [классы коллекций ATL](../../atl/atl-collection-classes.md).  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atlcoll.h  
  
##  <a name="add"></a>CAtlArray::Add  
 Вызовите этот метод, чтобы добавить элемент в массиве.  
  
```
size_t Add(INARGTYPE element);
size_t Add();
```  
  
### <a name="parameters"></a>Параметры  
 `element`  
 Элемент, добавляемый в массив.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает индекс добавленного элемента.  
  
### <a name="remarks"></a>Примечания  
 Новый элемент добавляется в конец массива. Если элемент не указано, добавляется пустой элемент; то есть массива увеличивается размер так же, как был добавлен элемент real. Если операция завершается неудачей, [AtlThrow](http://msdn.microsoft.com/library/2bd111da-8170-488d-914a-c9bf6b6765f7) вызывается с аргументом E_OUTOFMEMORY.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATL_Utilities&#1;](../../atl/codesnippet/cpp/catlarray-class_1.cpp)]  
  
##  <a name="append"></a>CAtlArray::Append  
 Этот метод используется для добавления содержимого одного массива в конец другого.  
  
```
size_t Append(const CAtlArray<E, ETraits>& aSrc);
```  
  
### <a name="parameters"></a>Параметры  
 `aSrc`  
 Массив добавляемых.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает индекс первый добавленный элемент.  
  
### <a name="remarks"></a>Примечания  
 В заданный массив элементы добавляются в конец существующего массива. При необходимости будет выделена память для размещения новых элементов.  
  
 Массивы должны быть одного типа, и невозможно добавить сам массив.  
  
 В отладочных построениях, ATLASSERT будет создано, если `CAtlArray` аргумент не является допустимым массивом или если `aSrc` ссылается на тот же объект. В сборке выпуска недопустимые аргументы может привести к непредсказуемому поведению.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATL_Utilities&#2;](../../atl/codesnippet/cpp/catlarray-class_2.cpp)]  
  
##  <a name="assertvalid"></a>CAtlArray::AssertValid  
 Вызовите этот метод, чтобы подтвердить допустимость объекта массива.  
  
```
void AssertValid() const;
```  
  
### <a name="remarks"></a>Примечания  
 Если объект массива является недопустимым, `ATLASSERT` вызовет утверждение. Этот метод доступен только в том случае, если определен _DEBUG.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATL_Utilities&#3;](../../atl/codesnippet/cpp/catlarray-class_3.cpp)]  
  
##  <a name="catlarray"></a>CAtlArray::CAtlArray  
 Конструктор.  
  
```
CAtlArray() throw();
```  
  
### <a name="remarks"></a>Примечания  
 Инициализирует объект массива.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATL_Utilities&#4;](../../atl/codesnippet/cpp/catlarray-class_4.cpp)]  
  
##  <a name="dtor"></a>CAtlArray:: ~ CAtlArray  
 Деструктор  
  
```
~CAtlArray() throw();
```  
  
### <a name="remarks"></a>Примечания  
 Освобождает все ресурсы, используемые в массиве.  
  
##  <a name="copy"></a>CAtlArray::Copy  
 Этот метод служит для копирования элементов одного массива в другой.  
  
```
void Copy(const CAtlArray<E, ETraits>& aSrc);
```  
  
### <a name="parameters"></a>Параметры  
 `aSrc`  
 Источник элементов, копируемых в массив.  
  
### <a name="remarks"></a>Примечания  
 Этот метод вызывается для перезаписи элементы одного массива с элементами другого массива. При необходимости будет выделена память для размещения новых элементов. Копирование элементов в массиве на себя невозможна.  
  
 Если существующее содержимое массива должен быть сохранен, используйте [CAtlArray::Append](#append) вместо.  
  
 В отладочных построениях, ATLASSERT будет создано, если существующий `CAtlArray` объекта является недопустимым, или если `aSrc` ссылается на тот же объект. В сборке выпуска недопустимые аргументы может привести к непредсказуемому поведению.  
  
> [!NOTE]
> `CAtlArray::Copy`не поддерживает массивы, состоящий из элементов, созданных с помощью [CAutoPtr](../../atl/reference/cautoptr-class.md) класса.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATL_Utilities&#5;](../../atl/codesnippet/cpp/catlarray-class_5.cpp)]  
  
##  <a name="freeextra"></a>CAtlArray::FreeExtra  
 Вызовите этот метод, чтобы удалить все пустые элементы из массива.  
  
```
void FreeExtra() throw();
```  
  
### <a name="remarks"></a>Примечания  
 Любые пустые элементы будут удалены, но размер и верхней границы массива остаются без изменений.  
  
 В отладочных построениях ATLASSERT возникает, если недопустимый CAtlArray объект или массив приведет к превышению максимального размера.  
  
##  <a name="getat"></a>CAtlArray::GetAt  
 Вызов, что этот метод, чтобы возвращает один элемент из объекта массива.  
  
```
const E& GetAt(size_t iElement) const throw();
E& GetAt(size_t iElement) throw();
```  
  
### <a name="parameters"></a>Параметры  
 `iElement`  
 Значение индекса элемента массива для возврата.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает ссылку на элемент массива требуется.  
  
### <a name="remarks"></a>Примечания  
 В отладочных построениях, ATLASSERT будет создано, если `iElement` превышает число элементов в массиве. В сборке выпуска недопустимый аргумент может привести к непредсказуемому поведению.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATL_Utilities №&6;](../../atl/codesnippet/cpp/catlarray-class_6.cpp)]  
  
##  <a name="getcount"></a>CAtlArray::GetCount  
 Этот метод используется для возврата числа элементов, хранящихся в массиве.  
  
```
size_t GetCount() const throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает количество элементов, хранящихся в массиве.  
  
### <a name="remarks"></a>Примечания  
 Как первый элемент в массиве находится в положении 0, значение, возвращаемое `GetCount` всегда равно 1 больше, чем самый большой индекс.  
  
### <a name="example"></a>Пример  
 В примере показано [CAtlArray::GetAt](#getat).  
  
##  <a name="getdata"></a>CAtlArray::GetData  
 Этот метод используется для возврата указателя на первый элемент в массиве.  
  
```
E* GetData() throw();
const E* GetData() const throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает указатель на область памяти, хранения первого элемента в массиве. Если нет элементов, возвращается значение NULL.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATL_Utilities&#7;](../../atl/codesnippet/cpp/catlarray-class_7.cpp)]  
  
##  <a name="inargtype"></a>CAtlArray::INARGTYPE  
 Тип данных, используемый для добавления элементов в массив.  
  
```
typedef ETraits::INARGTYPE INARGTYPE;
```  
  
##  <a name="insertarrayat"></a>CAtlArray::InsertArrayAt  
 Этот метод служит для вставки одного массива в другой.  
  
```
void InsertArrayAt(size_t iStart, const CAtlArray<E, ETraits>* paNew);
```  
  
### <a name="parameters"></a>Параметры  
 `iStart`  
 Индекс, по которому вставляется массива.  
  
 `paNew`  
 Массив для вставки.  
  
### <a name="remarks"></a>Примечания  
 Элементы массива `paNew` копируются в объект массива, начиная с элемента `iStart`. Чтобы избежать перезаписи перемещаются существующих элементов массива.  
  
 В отладочных построениях, ATLASSERT будет создано, если `CAtlArray` объекта является недопустимым, или если `paNew` указатель имеет значение NULL или недопустим.  
  
> [!NOTE]
> `CAtlArray::InsertArrayAt`не поддерживает массивы, состоящий из элементов, созданных с помощью [CAutoPtr](../../atl/reference/cautoptr-class.md) класса.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATL_Utilities №&8;](../../atl/codesnippet/cpp/catlarray-class_8.cpp)]  
  
##  <a name="insertat"></a>CAtlArray::InsertAt  
 Этот метод вызывается для вставки нового элемента (или несколько копий элемента) в объект array.  
  
```
void InsertAt(size_t iElement, INARGTYPE element, size_t nCount = 1);
```  
  
### <a name="parameters"></a>Параметры  
 `iElement`  
 Индекс, где или несколько элементов, которые должны быть вставлены.  
  
 `element`  
 Значение элемента или вставляемые элементы.  
  
 `nCount`  
 Количество элементов для добавления.  
  
### <a name="remarks"></a>Примечания  
 Вставляет один или несколько элементов в массиве, начиная с индекса `iElement`. Существующие элементы перемещаются во избежание перезаписи.  
  
 В отладочных построениях, ATLASSERT будет создано, если `CAtlArray` объект является недопустимым, количество добавляемых элементов равно нулю или общее количество элементов слишком велико для массива для хранения. В окончательных построениях передачей неверных параметров может привести к непредсказуемым результатам.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATL_Utilities №&9;](../../atl/codesnippet/cpp/catlarray-class_9.cpp)]  
  
##  <a name="isempty"></a>CAtlArray::IsEmpty  
 Этот метод используется для проверки, если массив пуст.  
  
```
bool IsEmpty() const throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение true, если массив пуст, значение false в противном случае.  
  
### <a name="remarks"></a>Примечания  
 Массив считается пустым, если он не содержит элементов. Таким образом даже если массив содержит пустые элементы, не пустой.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATL_Utilities&#10;](../../atl/codesnippet/cpp/catlarray-class_10.cpp)]  
  
##  <a name="operator_at"></a>[CAtlArray::operator]  
 Вызовите этот оператор возвращает ссылку на элемент в массиве.  
  
```
E& operator[](size_t ielement) throw();
const E& operator[](size_t ielement) const throw();
```  
  
### <a name="parameters"></a>Параметры  
 `iElement`  
 Значение индекса элемента массива для возврата.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает ссылку на элемент массива требуется.  
  
### <a name="remarks"></a>Примечания  
 Выполняет те же функции для [CAtlArray::GetAt](#getat). В отличие от классов MFC [CArray](../../mfc/reference/carray-class.md), этот оператор не может использоваться в качестве замены для [CAtlArray::SetAt](#setat).  
  
 В отладочных построениях, ATLASSERT будет создано, если `iElement` превышает общее число элементов в массиве. В розничных сборках недопустимого параметра может привести к непредсказуемым результатам.  
  
##  <a name="outargtype"></a>CAtlArray::OUTARGTYPE  
 Тип данных, использовать для получения элементов из массива.  
  
```
typedef ETraits::OUTARGTYPE OUTARGTYPE;
```  
  
##  <a name="removeall"></a>CAtlArray::RemoveAll  
 Этот метод используется для удаления всех элементов из объекта массива.  
  
```
void RemoveAll() throw();
```  
  
### <a name="remarks"></a>Примечания  
 Удаляет все элементы из объекта массива.  
  
 Этот метод вызывает метод [CAtlArray::SetCount](#setcount) для изменения размера массива и затем освобождает любой выделенной памяти.  
  
### <a name="example"></a>Пример  
 В примере показано [CAtlArray::IsEmpty](#isempty).  
  
##  <a name="removeat"></a>CAtlArray::RemoveAt  
 Вызовите этот метод, чтобы удалить один или несколько элементов из массива.  
  
```
void RemoveAt(size_t iElement, size_t nCount = 1);
```  
  
### <a name="parameters"></a>Параметры  
 `iElement`  
 Индекс первого элемента для удаления.  
  
 `nCount`  
 Число удаляемых элементов.  
  
### <a name="remarks"></a>Примечания  
 Удаляет один или несколько элементов из массива. Все оставшиеся элементы сдвигаются вниз. Верхняя граница уменьшается, но память не освобождается до вызова [CAtlArray::FreeExtra](#freeextra) выполняется.  
  
 В отладочных построениях, ATLASSERT будет создано, если `CAtlArray` объекта является недопустимым, или, если общее число `iElement` и `nCount` превышает общее число элементов в массиве. В розничных сборках недопустимые параметры могут привести к непредсказуемым результатам.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATL_Utilities&11;](../../atl/codesnippet/cpp/catlarray-class_11.cpp)]  
  
##  <a name="setat"></a>CAtlArray::SetAt  
 Этот метод используется для задания значения элемента объекта массива.  
  
```
void SetAt(size_t iElement, INARGTYPE element);
```  
  
### <a name="parameters"></a>Параметры  
 `iElement`  
 Индекс, указывающий на элемент массива для задания.  
  
 `element`  
 Новое значение указанного элемента.  
  
### <a name="remarks"></a>Примечания  
 В отладочных построениях, ATLASSERT будет создано, если `iElement` превышает число элементов в массиве. Недопустимый параметр в розничных сборках, может привести к непредсказуемым результатам.  
  
### <a name="example"></a>Пример  
 В примере показано [CAtlArray::GetAt](#getat).  
  
##  <a name="setcount"></a>CAtlArray::SetCount  
 Вызовите этот метод, чтобы задать размер объекта массива.  
  
```
bool SetCount(size_t nNewSize, int nGrowBy = - 1);
```  
  
### <a name="parameters"></a>Параметры  
 `nNewSize`  
 Требуется размер массива.  
  
 `nGrowBy`  
 Значение, используемое для определения размера буфера. Значение-1 вызывает внутренне вычисляемого значения для использования.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение true, если массив успешно измененным размером, и false в противном случае.  
  
### <a name="remarks"></a>Примечания  
 Можно увеличить или уменьшить размер массива. Если увеличить, дополнительные пустые элементы добавляются в массив. Если уменьшилось, элементы с наибольшим индексы будут удалены и освобождение памяти.  
  
 Используйте этот метод, чтобы задать размер массива перед его использованием. Если `SetCount` не используется, процесс добавления элементов — и выполнить распределение памяти, последующие — будет привести к снижению производительности и фрагментации памяти.  
  
### <a name="example"></a>Пример  
 В примере показано [CAtlArray::GetData](#getdata).  
  
##  <a name="setatgrow"></a>CAtlArray::SetAtGrow  
 Этот метод используется для задания значения элемента объекта массива, расширение массива, при необходимости.  
  
```
void SetAtGrow(size_t iElement, INARGTYPE element);
```  
  
### <a name="parameters"></a>Параметры  
 `iElement`  
 Индекс, указывающий на элемент массива для задания.  
  
 `element`  
 Новое значение указанного элемента.  
  
### <a name="remarks"></a>Примечания  
 Заменяет значение элемента, на который указывает индекс. Если `iElement` больше, чем текущий размер массива, массив автоматически увеличивается с помощью вызова [CAtlArray::SetCount](#setcount). В отладочных построениях, ATLASSERT будет создано, если `CAtlArray` недопустимый объект. В розничных сборках недопустимые параметры могут привести к непредсказуемым результатам.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATL_Utilities&#12;](../../atl/codesnippet/cpp/catlarray-class_12.cpp)]  
  
## <a name="see-also"></a>См. также  
 [Образец MMXSwarm](../../visual-cpp-samples.md)   
 [Образец DynamicConsumer](../../visual-cpp-samples.md)   
 [Пример в этом примере](../../visual-cpp-samples.md)   
 [Образец бегущей строки](../../visual-cpp-samples.md)   
 [CArray-класс](../../mfc/reference/carray-class.md)   
 [Общие сведения о классе](../../atl/atl-class-overview.md)

