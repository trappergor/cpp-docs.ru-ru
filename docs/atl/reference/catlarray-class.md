---
title: Класс CAtlArray | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- CAtlArray class
ms.assetid: 0b503aa8-2357-40af-a326-6654bf1da098
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c54771b7cf66cb980c2b711760589ffd41019799
ms.sourcegitcommit: 7d68f8303e021e27dc8f4d36e764ed836e93d24f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/06/2018
ms.locfileid: "37880486"
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
  
## <a name="members"></a>Участники  
  
### <a name="methods"></a>Методы  
  
|||  
|-|-|  
|[Добавить](#add)|Вызовите этот метод, чтобы добавить элемент в массиве.|  
|[добавить](#append)|Вызовите этот метод, чтобы добавить содержимое одного массива в другой конец.|  
|[AssertValid](#assertvalid)|Вызовите этот метод, чтобы подтвердить правильность объект массива.|  
|[CAtlArray](#catlarray)|Конструктор.|  
|[~ CAtlArray](#dtor)|Деструктор|  
|[Копировать](#copy)|Этот метод используется для копирования элементов одного массива в другой.|  
|[FreeExtra](#freeextra)|Вызовите этот метод, чтобы удалить все пустые элементы из массива.|  
|[GetAt](#getat)|Вызовите этот метод для получения отдельного элемента в объекте массива.|  
|[GetCount](#getcount)|Этот метод используется для возврата количества элементов, которые хранятся в массиве.|  
|[GetData](#getdata)|Этот метод используется для возврата указателя на первый элемент в массиве.|  
|[InsertArrayAt](#insertarrayat)|Этот метод используется для вставки одного массива в другой.|  
|[InsertAt](#insertat)|Этот метод для вставки нового элемента (или несколько копий элемента) в объект массива.|  
|[IsEmpty](#isempty)|Этот метод используется для проверки, если массив пуст.|  
|[RemoveAll](#removeall)|Этот метод используется для удаления всех элементов в объекте массива.|  
|[RemoveAt](#removeat)|Вызовите этот метод, чтобы удалить один или несколько элементов из массива.|  
|[SetAt](#setat)|Этот метод используется для задания значения элемента в объекте массива.|  
|[SetAtGrow](#setatgrow)|Этот метод используется для задания значения элемента в объекте массива, развернув массив при необходимости.|  
|[SetCount](#setcount)|Этот метод используется для задания размера массива объекта.|  
  
### <a name="operators"></a>Операторы  
  
|||  
|-|-|  
|[оператор&#91;&#93;](#operator_at)|Вызовите этот оператор, чтобы вернуть ссылку на элемент в массиве.|  

  
### <a name="typedefs"></a>Определения типов  
  
|||  
|-|-|  
|[INARGTYPE](#inargtype)|Тип данных, который нужно использовать для добавления элементов в массиве.|  
|[OUTARGTYPE](#outargtype)|Тип данных, который нужно использовать для извлечения элементов из массива.|  
  
## <a name="remarks"></a>Примечания  
 `CAtlArray` Предоставляет методы для создания и управления ими массив элементов из определяемого пользователем типа. Хотя они похожи на стандартные массивы C `CAtlArray` объект динамически можно сжать и увеличиваться при необходимости. Индекс массива всегда начинается с позиции 0, а верхняя граница может быть исправлено или разрешено увеличиваться при добавлении новых элементов.  
  
 Для массивов с небольшим числом элементов, класс ATL [CSimpleArray](../../atl/reference/csimplearray-class.md) может использоваться.  
  
 `CAtlArray` тесно связано с MFC `CArray` класса и будет работать в проекте MFC, хотя и без поддержки сериализации.  
  
 Дополнительные сведения см. в разделе [классы коллекций ATL](../../atl/atl-collection-classes.md).  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atlcoll.h  
  
##  <a name="add"></a>  CAtlArray::Add  
 Вызовите этот метод, чтобы добавить элемент в массиве.  
  
```
size_t Add(INARGTYPE element);
size_t Add();
```  
  
### <a name="parameters"></a>Параметры  
 *Элемент*  
 Элемент, добавляемый в массив.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает индекс добавленного элемента.  
  
### <a name="remarks"></a>Примечания  
 Новый элемент добавляется в конец массива. Если ни один элемент не указан, добавляется пустой элемент; то есть массив увеличивающиеся в размере так, будто реальных элемент был добавлен. Если операция завершается ошибкой, [AtlThrow](debugging-and-error-reporting-global-functions.md#atlthrow) вызывается с аргументом E_OUTOFMEMORY.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATL_Utilities#1](../../atl/codesnippet/cpp/catlarray-class_1.cpp)]  
  
##  <a name="append"></a>  CAtlArray::Append  
 Вызовите этот метод, чтобы добавить содержимое одного массива в другой конец.  
  
```
size_t Append(const CAtlArray<E, ETraits>& aSrc);
```  
  
### <a name="parameters"></a>Параметры  
 *aSrc*  
 Массив, для добавления.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает индекс первый добавленный элемент.  
  
### <a name="remarks"></a>Примечания  
 Элементы предоставленного массива добавляются в конец существующего массива. При необходимости будет выделена память для размещения новых элементов.  
  
 Массивы должны быть одного типа и его уже не сможете добавить сам массив.  
  
 В отладочных сборках ATLASSERT будет вызвано, если `CAtlArray` аргумент не является допустимым массивом или если *aSrc* ссылается на тот же объект. В сборках выпуска недопустимые аргументы могут привести к непредсказуемому поведению.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATL_Utilities#2](../../atl/codesnippet/cpp/catlarray-class_2.cpp)]  
  
##  <a name="assertvalid"></a>  CAtlArray::AssertValid  
 Вызовите этот метод, чтобы подтвердить правильность объект массива.  
  
```
void AssertValid() const;
```  
  
### <a name="remarks"></a>Примечания  
 Если объект массива не является допустимым, ATLASSERT вызовет утверждение. Этот метод доступен только в том случае, если определен _DEBUG.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATL_Utilities#3](../../atl/codesnippet/cpp/catlarray-class_3.cpp)]  
  
##  <a name="catlarray"></a>  CAtlArray::CAtlArray  
 Конструктор.  
  
```
CAtlArray() throw();
```  
  
### <a name="remarks"></a>Примечания  
 Инициализирует объект массива.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATL_Utilities#4](../../atl/codesnippet/cpp/catlarray-class_4.cpp)]  
  
##  <a name="dtor"></a>  CAtlArray:: ~ CAtlArray  
 Деструктор  
  
```
~CAtlArray() throw();
```  
  
### <a name="remarks"></a>Примечания  
 Освобождает все ресурсы, используемые объектом массива.  
  
##  <a name="copy"></a>  CAtlArray::Copy  
 Этот метод используется для копирования элементов одного массива в другой.  
  
```
void Copy(const CAtlArray<E, ETraits>& aSrc);
```  
  
### <a name="parameters"></a>Параметры  
 *aSrc*  
 Источник копируемых в массив элементов.  
  
### <a name="remarks"></a>Примечания  
 Вызовите этот метод, чтобы перезаписать элементы одного массива с элементами другого массива. При необходимости будет выделена память для размещения новых элементов. Не поддерживается для копирования элементов в массиве на самого себя.  
  
 Если существующее содержимое массива, должны сохраняться, используйте [CAtlArray::Append](#append) вместо этого.  
  
 В отладочных сборках ATLASSERT будет вызвано, если существующий `CAtlArray` объект не является допустимым, или если *aSrc* ссылается на тот же объект. В сборках выпуска недопустимые аргументы могут привести к непредсказуемому поведению.  
  
> [!NOTE]
> `CAtlArray::Copy` не поддерживает массивы, состоящий из элементов, созданных с помощью [CAutoPtr](../../atl/reference/cautoptr-class.md) класса.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATL_Utilities#5](../../atl/codesnippet/cpp/catlarray-class_5.cpp)]  
  
##  <a name="freeextra"></a>  CAtlArray::FreeExtra  
 Вызовите этот метод, чтобы удалить все пустые элементы из массива.  
  
```
void FreeExtra() throw();
```  
  
### <a name="remarks"></a>Примечания  
 Любые пустые элементы удаляются, но размер и верхнюю границу массива остаются неизменными.  
  
 В отладочных сборках ATLASSERT возникает, если недопустимый CAtlArray объект или массив приведет к превышению максимального размера.  
  
##  <a name="getat"></a>  CAtlArray::GetAt  
 Вызовите этот метод, чтобы получает один элемент из массива объекта.  
  
```
const E& GetAt(size_t iElement) const throw();
E& GetAt(size_t iElement) throw();
```  
  
### <a name="parameters"></a>Параметры  
 *iElement*  
 Значение индекса элемента массива для возврата.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает ссылку на элемент массива требуется.  
  
### <a name="remarks"></a>Примечания  
 В отладочных сборках ATLASSERT будет вызвано, если *iElement* превышает число элементов в массиве. В сборках выпуска недопустимый аргумент может привести к непредсказуемому поведению.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATL_Utilities#6](../../atl/codesnippet/cpp/catlarray-class_6.cpp)]  
  
##  <a name="getcount"></a>  CAtlArray::GetCount  
 Этот метод используется для возврата количества элементов, которые хранятся в массиве.  
  
```
size_t GetCount() const throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает количество элементов, содержащихся в массиве.  
  
### <a name="remarks"></a>Примечания  
 Так как первый элемент в массиве в позиции 0, значение, возвращаемое функцией `GetCount` всегда равно 1 больше, чем наибольший индекс.  
  
### <a name="example"></a>Пример  
 См. в примере [CAtlArray::GetAt](#getat).  
  
##  <a name="getdata"></a>  CAtlArray::GetData  
 Этот метод используется для возврата указателя на первый элемент в массиве.  
  
```
E* GetData() throw();
const E* GetData() const throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает указатель на область памяти, хранения первого элемента в массиве. Если ни один элемент, возвращается значение NULL.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATL_Utilities#7](../../atl/codesnippet/cpp/catlarray-class_7.cpp)]  
  
##  <a name="inargtype"></a>  CAtlArray::INARGTYPE  
 Тип данных, который нужно использовать для добавления элементов в массиве.  
  
```
typedef ETraits::INARGTYPE INARGTYPE;
```  
  
##  <a name="insertarrayat"></a>  CAtlArray::InsertArrayAt  
 Этот метод используется для вставки одного массива в другой.  
  
```
void InsertArrayAt(size_t iStart, const CAtlArray<E, ETraits>* paNew);
```  
  
### <a name="parameters"></a>Параметры  
 *iStart*  
 Индекс, по которому вставляется массив.  
  
 *paNew*  
 Массив для вставки.  
  
### <a name="remarks"></a>Примечания  
 Элементы массива *paNew* копируются в объекте массива, начиная с элемента *iStart*. Существующие элементы массива, перемещаются во избежание перезаписи.  
  
 В отладочных сборках ATLASSERT будет вызвано, если `CAtlArray` объект не является допустимым, или если *paNew* указатель имеет значение NULL или недопустим.  
  
> [!NOTE]
> `CAtlArray::InsertArrayAt` не поддерживает массивы, состоящий из элементов, созданных с помощью [CAutoPtr](../../atl/reference/cautoptr-class.md) класса.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATL_Utilities#8](../../atl/codesnippet/cpp/catlarray-class_8.cpp)]  
  
##  <a name="insertat"></a>  CAtlArray::InsertAt  
 Этот метод для вставки нового элемента (или несколько копий элемента) в объект массива.  
  
```
void InsertAt(size_t iElement, INARGTYPE element, size_t nCount = 1);
```  
  
### <a name="parameters"></a>Параметры  
 *iElement*  
 Индекс, где один или несколько элементов, которые должны быть вставлены.  
  
 *Элемент*  
 Значение или несколько элементов для вставки.  
  
 *nCount*  
 Число элементов для добавления.  
  
### <a name="remarks"></a>Примечания  
 Вставляет один или несколько элементов в массиве, начиная с индекса *iElement*. Существующие элементы перемещаются во избежание перезаписи.  
  
 В отладочных сборках ATLASSERT будет вызвано, если `CAtlArray` становится недействительным, число добавляемых элементов равно нулю или общее количество элементов слишком велико для массива для хранения. В окончательных сборках передачей неверных параметров может привести к непредсказуемым результатам.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATL_Utilities#9](../../atl/codesnippet/cpp/catlarray-class_9.cpp)]  
  
##  <a name="isempty"></a>  CAtlArray::IsEmpty  
 Этот метод используется для проверки, если массив пуст.  
  
```
bool IsEmpty() const throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение true, если массив пуст, значение false в противном случае.  
  
### <a name="remarks"></a>Примечания  
 Считается, что массив является пустым, если он не содержит элементов. Таким образом даже если массив содержит пустые элементы, он не пустой.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATL_Utilities#10](../../atl/codesnippet/cpp/catlarray-class_10.cpp)]  
  
##  <a name="operator_at"></a>  [CAtlArray::operator]  
 Вызовите этот оператор, чтобы вернуть ссылку на элемент в массиве.  
  
```
E& operator[](size_t ielement) throw();
const E& operator[](size_t ielement) const throw();
```  
  
### <a name="parameters"></a>Параметры  
 *iElement*  
 Значение индекса элемента массива для возврата.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает ссылку на элемент массива требуется.  
  
### <a name="remarks"></a>Примечания  
 Выполняет ту же функцию [CAtlArray::GetAt](#getat). В отличие от классов MFC [CArray](../../mfc/reference/carray-class.md), этот оператор не может использоваться в качестве замены для [CAtlArray::SetAt](#setat).  
  
 В отладочных сборках ATLASSERT будет вызвано, если *iElement* превышает общее число элементов в массиве. В окончательных сборках недопустимый параметр может привести к непредсказуемым результатам.  
  
##  <a name="outargtype"></a>  CAtlArray::OUTARGTYPE  
 Тип данных, который нужно использовать для извлечения элементов из массива.  
  
```
typedef ETraits::OUTARGTYPE OUTARGTYPE;
```  
  
##  <a name="removeall"></a>  CAtlArray::RemoveAll  
 Этот метод используется для удаления всех элементов в объекте массива.  
  
```
void RemoveAll() throw();
```  
  
### <a name="remarks"></a>Примечания  
 Удаляет все элементы из объекта массива.  
  
 Этот метод вызывает метод [CAtlArray::SetCount](#setcount) для изменения размера массива и затем освобождает память, выделенную.  
  
### <a name="example"></a>Пример  
 См. в примере [CAtlArray::IsEmpty](#isempty).  
  
##  <a name="removeat"></a>  CAtlArray::RemoveAt  
 Вызовите этот метод, чтобы удалить один или несколько элементов из массива.  
  
```
void RemoveAt(size_t iElement, size_t nCount = 1);
```  
  
### <a name="parameters"></a>Параметры  
 *iElement*  
 Индекс первого удаляемого элемента.  
  
 *nCount*  
 Число удаляемых элементов.  
  
### <a name="remarks"></a>Примечания  
 Удаляет один или несколько элементов из массива. Все оставшиеся элементы сдвигаются. Верхняя граница уменьшается, но память не освобождается до вызова [CAtlArray::FreeExtra](#freeextra) выполняется.  
  
 В отладочных сборках ATLASSERT будет вызвано, если `CAtlArray` объект не является допустимым, или, если общее число *iElement* и *nCount* превышает общее число элементов в массиве. В окончательных сборках недопустимые параметры могут привести к непредсказуемым результатам.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATL_Utilities#11](../../atl/codesnippet/cpp/catlarray-class_11.cpp)]  
  
##  <a name="setat"></a>  CAtlArray::SetAt  
 Этот метод используется для задания значения элемента в объекте массива.  
  
```
void SetAt(size_t iElement, INARGTYPE element);
```  
  
### <a name="parameters"></a>Параметры  
 *iElement*  
 Индекс, указывающий на элемент массива для задания.  
  
 *Элемент*  
 Новое значение указанного элемента.  
  
### <a name="remarks"></a>Примечания  
 В отладочных сборках ATLASSERT будет вызвано, если *iElement* превышает число элементов в массиве. Недопустимый параметр в окончательных сборках, может привести к непредсказуемым результатам.  
  
### <a name="example"></a>Пример  
 См. в примере [CAtlArray::GetAt](#getat).  
  
##  <a name="setcount"></a>  CAtlArray::SetCount  
 Этот метод используется для задания размера массива объекта.  
  
```
bool SetCount(size_t nNewSize, int nGrowBy = - 1);
```  
  
### <a name="parameters"></a>Параметры  
 *nNewSize*  
 Требуемый размер массива.  
  
 *nGrowBy*  
 Значение, используемое для определения размера буфера. Значение-1 вызывает внутренне вычисляемого значения, используемого.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение true, если массив успешно измененным размером, и false в противном случае.  
  
### <a name="remarks"></a>Примечания  
 Можно увеличивать или уменьшать размер массива. При увеличении, дополнительные пустые элементы добавляются в массив. Если уменьшилось, элементы, имеющие наибольшее индексы будут удалены и освобождение памяти.  
  
 Этот метод позволяет задать размер массива перед его использованием. Если `SetCount` не используется, процесс добавления элементов — и выполнить распределение памяти, последующие — будет привести к снижению производительности и фрагментации памяти.  
  
### <a name="example"></a>Пример  
 См. в примере [CAtlArray::GetData](#getdata).  
  
##  <a name="setatgrow"></a>  CAtlArray::SetAtGrow  
 Этот метод используется для задания значения элемента в объекте массива, развернув массив при необходимости.  
  
```
void SetAtGrow(size_t iElement, INARGTYPE element);
```  
  
### <a name="parameters"></a>Параметры  
 *iElement*  
 Индекс, указывающий на элемент массива для задания.  
  
 *Элемент*  
 Новое значение указанного элемента.  
  
### <a name="remarks"></a>Примечания  
 Заменяет значение элемента, на которые указывает индекс. Если *iElement* больше, чем текущий размер массива, массив автоматически увеличивается с помощью вызова [CAtlArray::SetCount](#setcount). В отладочных сборках ATLASSERT будет вызвано, если `CAtlArray` объект не является допустимым. В окончательных сборках недопустимые параметры могут привести к непредсказуемым результатам.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATL_Utilities#12](../../atl/codesnippet/cpp/catlarray-class_12.cpp)]  
  
## <a name="see-also"></a>См. также  
 [Пример MMXSwarm](../../visual-cpp-samples.md)   
 [Образец DynamicConsumer](../../visual-cpp-samples.md)   
 [Образец UpdatePV](../../visual-cpp-samples.md)   
 [Пример бегущей строки](../../visual-cpp-samples.md)   
 [CArray-класс](../../mfc/reference/carray-class.md)   
 [Общие сведения о классе](../../atl/atl-class-overview.md)
