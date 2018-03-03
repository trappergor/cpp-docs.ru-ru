---
title: "Класс CAtlMap | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CAtlMap
- ATLCOLL/ATL::CAtlMap
- ATLCOLL/ATL::CAtlMap::KINARGTYPE
- ATLCOLL/ATL::CAtlMap::KOUTARGTYPE
- ATLCOLL/ATL::CAtlMap::VINARGTYPE
- ATLCOLL/ATL::CAtlMap::VOUTARGTYPE
- ATLCOLL/ATL::CPair::m_key
- ATLCOLL/ATL::CPair::m_value
- ATLCOLL/ATL::CAtlMap::CAtlMap
- ATLCOLL/ATL::CAtlMap::AssertValid
- ATLCOLL/ATL::CAtlMap::DisableAutoRehash
- ATLCOLL/ATL::CAtlMap::EnableAutoRehash
- ATLCOLL/ATL::CAtlMap::GetAt
- ATLCOLL/ATL::CAtlMap::GetCount
- ATLCOLL/ATL::CAtlMap::GetHashTableSize
- ATLCOLL/ATL::CAtlMap::GetKeyAt
- ATLCOLL/ATL::CAtlMap::GetNext
- ATLCOLL/ATL::CAtlMap::GetNextAssoc
- ATLCOLL/ATL::CAtlMap::GetNextKey
- ATLCOLL/ATL::CAtlMap::GetNextValue
- ATLCOLL/ATL::CAtlMap::GetStartPosition
- ATLCOLL/ATL::CAtlMap::GetValueAt
- ATLCOLL/ATL::CAtlMap::InitHashTable
- ATLCOLL/ATL::CAtlMap::IsEmpty
- ATLCOLL/ATL::CAtlMap::Lookup
- ATLCOLL/ATL::CAtlMap::Rehash
- ATLCOLL/ATL::CAtlMap::RemoveAll
- ATLCOLL/ATL::CAtlMap::RemoveAtPos
- ATLCOLL/ATL::CAtlMap::RemoveKey
- ATLCOLL/ATL::CAtlMap::SetAt
- ATLCOLL/ATL::CAtlMap::SetOptimalLoad
- ATLCOLL/ATL::CAtlMap::SetValueAt
dev_langs:
- C++
helpviewer_keywords:
- CAtlMap class
ms.assetid: 5e2fe028-8e6d-4686-93df-1433d2080ec3
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 9166e8f7804a3138d3e891fbe15b54cb0e270811
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="catlmap-class"></a>Класс CAtlMap
Этот класс предоставляет методы для создания и управления объекта map.  
  
## <a name="syntax"></a>Синтаксис  
  
```
template <typename K,
          typename V, 
          class KTraits = CElementTraits<K>, 
          class VTraits = CElementTraits<V>>
class CAtlMap
```  
  
#### <a name="parameters"></a>Параметры  
 `K`  
 Тип ключа элемента.  
  
 V  
 Тип значения элемента.  
  
 `KTraits`  
 Код, используемый для копирования или перемещения элементов ключа. В разделе [CElementTraits класса](../../atl/reference/celementtraits-class.md) для получения дополнительных сведений.  
  
 `VTraits`  
 Код, используемый для копирования или перемещения элементов значение.  
  
## <a name="members"></a>Участники  
  
### <a name="public-typedefs"></a>Общедоступные определения типов  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CAtlMap::KINARGTYPE](#kinargtype)|Тип, используемый при передаче ключа в качестве входного аргумента|  
|[CAtlMap::KOUTARGTYPE](#koutargtype)|Тип, используемый при возврате ключ в виде выходного аргумент.|  
|[CAtlMap::VINARGTYPE](#vinargtype)|Тип, используемый, когда значение передается в качестве входного аргумента.|  
|[CAtlMap::VOUTARGTYPE](#voutargtype)|Тип, используемый при передаче значения в виде выходного аргумент.|  
  
### <a name="public-classes"></a>Открытые классы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[Класс CAtlMap::CPair](#cpair_class)|Класс, содержащий ключ и значение элементов.|  

  
### <a name="cpair-data-members"></a>Члены данных CPair  
  
|name|Описание:|  
|----------|-----------------|  
|[CPair::m_key](#m_key)|Элемент данных хранения ключа элемента.|  
|[CPair::m_value](#m_value)|Элемент данных хранения значение элемента.|  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CAtlMap::CAtlMap](#catlmap)|Конструктор.|  
|[CAtlMap:: ~ CAtlMap](#dtor)|Деструктор|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CAtlMap::AssertValid](#assertvalid)|Вызовите этот метод, чтобы вызвать метод ASSERT, если `CAtlMap` является недопустимым.|  
|[CAtlMap::DisableAutoRehash](#disableautorehash)|Вызовите этот метод, чтобы отключить автоматическое проведя пересчет контрольной суммы из `CAtlMap` объекта.|  
|[CAtlMap::EnableAutoRehash](#enableautorehash)|Вызовите этот метод, чтобы включить автоматическое проведя пересчет контрольной суммы из `CAtlMap` объекта.|  
|[CAtlMap::GetAt](#getat)|Этот метод используется для возвращения элемента в указанной позиции в схеме.|  
|[CAtlMap::GetCount](#getcount)|Вызовите этот метод для извлечения нескольких элементов в объекте map.|  
|[CAtlMap::GetHashTableSize](#gethashtablesize)|Этот метод используется для определения количества сегментов в хэш-таблице карты.|  
|[CAtlMap::GetKeyAt](#getkeyat)|Вызовите этот метод, чтобы получить ключ, хранящийся в заданном положении в `CAtlMap` объекта.|  
|[CAtlMap::GetNext](#getnext)|Этот метод вызывается для получения указателя на следующий элемент, пара хранится в `CAtlMap` объекта.|  
|[CAtlMap::GetNextAssoc](#getnextassoc)|Получает следующий элемент для выполнения итерации.|  
|[CAtlMap::GetNextKey](#getnextkey)|Этот метод вызывается для получения следующего ключа из `CAtlMap` объекта.|  
|[CAtlMap::GetNextValue](#getnextvalue)|Этот метод вызывается для получения следующего значения из `CAtlMap` объекта.|  
|[CAtlMap::GetStartPosition](#getstartposition)|Этот метод перед началом итерации карты.|  
|[CAtlMap::GetValueAt](#getvalueat)|Этот метод вызывается для получения значения, хранящиеся в заданном положении в `CAtlMap` объекта.|  
|[CAtlMap::InitHashTable](#inithashtable)|Этот метод вызывается для инициализации хэш-таблицы.|  
|[CAtlMap::IsEmpty](#isempty)|Этот метод используется для проверки объекта пустое сопоставление.|  
|[CAtlMap::Lookup](#lookup)|Вызовите этот метод для поиска разделов или значений в `CAtlMap` объекта.|  
|[CAtlMap::Rehash](#rehash)|Этот метод вызывается для rehash `CAtlMap` объекта.|  
|[CAtlMap::RemoveAll](#removeall)|Этот метод вызывается для удаления всех элементов из `CAtlMap` объекта.|  
|[CAtlMap::RemoveAtPos](#removeatpos)|Этот метод вызывается для удаления элемента в заданном положении в `CAtlMap` объекта.|  
|[CAtlMap::RemoveKey](#removekey)|Этот метод вызывается для удаления элемента из `CAtlMap` объекту, заданному ключу.|  
|[CAtlMap::SetAt](#setat)|Этот метод служит для вставки пары элементов в сопоставление.|  
|[CAtlMap::SetOptimalLoad](#setoptimalload)|Вызовите этот метод, чтобы задать оптимальную загрузку `CAtlMap` объекта.|  
|[CAtlMap::SetValueAt](#setvalueat)|Вызовите этот метод, чтобы изменить значение, хранящееся в заданном положении в `CAtlMap` объекта.|  
  
### <a name="public-operators"></a>Открытые операторы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CAtlMap::operator\[\]](catlmap-class.md#operator_at)|Заменяет или добавляет новый элемент в `CAtlMap`.|  

  
## <a name="remarks"></a>Примечания  
 `CAtlMap`предоставляет поддержку для любого конкретного типа управления массив неупорядоченных ключевые элементы и связанные с ними значения массива сопоставления. Элементов (состоящие из ключа и значения) хранятся с использованием хэш-алгоритма, позволяя большой объем данных, эффективно хранить и получить.  
  
 `KTraits` И `VTraits` являются классов признаки, которые содержат любой дополнительный код, необходимые для копирования или перемещения элементов.  
  
 Это альтернатива `CAtlMap` предлагаемых [CRBMap](../../atl/reference/crbmap-class.md) класса. `CRBMap`также хранит пары "ключ значение", но существуют различные характеристики производительности. Время, необходимое для вставки элемента, поиска ключа или удаления ключа из `CRBMap` объект является заказа *log(n)*, где  *n*  — число элементов. Для `CAtlMap`, все эти операции обычно занять константой времени, несмотря на то, что наихудших сценариев может быть заказа  *n* . Таким образом, в типичный случай `CAtlMap` выполняется быстрее.  
  
 Разница между `CRBMap` и `CAtlMap` становится очевидной при проходе по хранимых элементов. В `CRBMap`, элементы являются посетит в отсортированном порядке. В `CAtlMap`, элементы не упорядочены и порядок не могут быть заданы.  
  
 При необходимости храниться небольшое количество элементов, рассмотрите возможность использования [CSimpleMap](../../atl/reference/csimplemap-class.md) вместо этого класс.  
  
 Дополнительные сведения см. в разделе [классы коллекций ATL](../../atl/atl-collection-classes.md).  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atlcoll.h  
  
##  <a name="assertvalid"></a>CAtlMap::AssertValid  
 Вызовите этот метод, чтобы вызвать метод ASSERT, если `CAtlMap` недопустимый объект.  
  
```
void AssertValid() const;
```  
  
### <a name="remarks"></a>Примечания  
 В отладочных построениях, этот метод вызовет ASSERT Если `CAtlMap` недопустимый объект.  
  
### <a name="example"></a>Пример  
 Далее приведен пример [CAtlMap::CAtlMap](#catlmap).  
  
##  <a name="catlmap"></a>CAtlMap::CAtlMap  
 Конструктор.  
  
```
CAtlMap(
    UINT nBins = 17,
    float fOptimalLoad = 0.75f,
    float fLoThreshold = 0.25f,
    float fHiThreshold = 2.25f,
    UINT nBlockSize = 10) throw ();
```  
  
### <a name="parameters"></a>Параметры  
 `nBins`  
 Количество ячеек, ссылки на элементы хранимой. Далее в этом разделе для объяснения ячеек см. заметки.  
  
 `fOptimalLoad`  
 Отношение оптимальной нагрузки.  
  
 `fLoThreshold`  
 Нижнее пороговое значение для коэффициента нагрузки.  
  
 `fHiThreshold`  
 Верхнее пороговое значение для коэффициента нагрузки.  
  
 `nBlockSize`  
 Размер блока.  
  
### <a name="remarks"></a>Примечания  
 `CAtlMap`ссылается на все его элементы хранимых путем первоначального создания индекса при помощи алгоритма хэширования по ключу. Этот индекс ссылается на «bin», который содержит указатель на элементы, хранимые. Если ячейка уже используется, для доступа к элементам последующих создается в связанном списке. Обход списка выполняется медленнее, чем прямой доступ к правильный элемент и поэтому структуре карты необходимо сбалансировать требования к хранилищу с точки зрения производительности. Для предоставления хорошие результаты в большинстве случаев были выбраны параметры по умолчанию.  
  
 Коэффициента нагрузки — это отношение количества ячеек в число элементов, хранящихся в объекте map. При пересчете структуре карты *fOptimalLoad* значение параметра будет использоваться для вычисления числа ячеек, которые требуется. Это значение можно изменить с помощью [CAtlMap::SetOptimalLoad](#setoptimalload) метод.  
  
 `fLoThreshold` Параметр имеет меньшее значение, при достижении коэффициента нагрузки `CAtlMap` приведет к пересчету оптимальный размер карты.  
  
 `fHiThreshold` Параметр является верхним значением, при достижении коэффициента нагрузки `CAtlMap` объект будет повторно вычислить оптимальный размер карты.  
  
 Этот процесс повторного вычисления (известный как проведя пересчет контрольной суммы) включен по умолчанию. Если вы хотите отключить этот процесс, возможно, при вводе большой объем данных за один раз вызов [CAtlMap::DisableAutoRehash](#disableautorehash) метод. Повторно активировать его с [CAtlMap::EnableAutoRehash](#enableautorehash) метод.  
  
 `nBlockSize` Параметр — это мера объем памяти, выделяемый при новый элемент является обязательным. Увеличенный размер блока, уменьшите количество вызовов процедур выделения памяти, но использует больше ресурсов.  
  
 Прежде чем могут храниться любые данные, это необходимо для инициализации хэш-таблицы с помощью вызова [CAtlMap::InitHashTable](#inithashtable).  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATL_Utilities#72](../../atl/codesnippet/cpp/catlmap-class_1.cpp)]  
  
##  <a name="dtor"></a>CAtlMap:: ~ CAtlMap  
 Деструктор  
  
```
~CAtlMap() throw();
```  
  
### <a name="remarks"></a>Примечания  
 Освобождает все ресурсы, выделенные.  
  
##  <a name="cpair_class"></a>Класс CAtlMap::CPair  
 Класс, содержащий ключ и значение элементов.  
  
```
class CPair : public __POSITION
```  
  
### <a name="remarks"></a>Примечания  
 Этот класс используется с помощью методов [CAtlMap::GetNext](#getnext) и [CAtlMap::Lookup](#lookup) для доступа к элементам ключ и значение, хранящееся в структуре сопоставления.  
  
##  <a name="disableautorehash"></a>CAtlMap::DisableAutoRehash  
 Вызовите этот метод, чтобы отключить автоматическое проведя пересчет контрольной суммы из `CAtlMap` объекта.  
  
```
void DisableAutoRehash() throw();
```  
  
### <a name="remarks"></a>Примечания  
 Если автоматическое проведя пересчет контрольной суммы включена (что и происходит по умолчанию), количество сегментов в хэш-таблице автоматически повторное вычисление, если значение load (соотношение числа ячеек на количество элементов, хранящихся в массиве) превышает максимальное и минимальное значения указан во время создания карты.  
  
 `DisableAutoRehash`особенно полезен при большое количество элементов будет добавлен на карту за один раз. Вместо инициирует rehashing каждый раз при превышении ограничений, эффективнее вызывать `DisableAutoRehash`, добавьте элементы и вызвать [CAtlMap::EnableAutoRehash](#enableautorehash).  
  
##  <a name="enableautorehash"></a>CAtlMap::EnableAutoRehash  
 Вызовите этот метод, чтобы включить автоматическое проведя пересчет контрольной суммы из `CAtlMap` объекта.  
  
```
void EnableAutoRehash() throw();
```  
  
### <a name="remarks"></a>Примечания  
 Если автоматическое проведя пересчет контрольной суммы включена (что и происходит по умолчанию), количество сегментов в хэш-таблице автоматически повторное вычисление, если значение load (соотношение числа ячеек на количество элементов, хранящихся в массиве) превышает максимальное и минимальное значения указан во время создания карты.  
  
 **EnableAutoRefresh** наиболее часто используется после вызова [CAtlMap::DisableAutoRehash](#disableautorehash).  
  
##  <a name="getat"></a>CAtlMap::GetAt  
 Этот метод используется для возвращения элемента в указанной позиции в схеме.  
  
```
void GetAt(
    POSITION pos,
    KOUTARGTYPE key,
    VOUTARGTYPE value) const;

CPair* GetAt(POSITION& pos) throw();
```  
  
### <a name="parameters"></a>Параметры  
 `pos`  
 Счетчик позиции, возвращенный предыдущим вызовом [CAtlMap::GetNextAssoc](#getnextassoc) или [CAtlMap::GetStartPosition](#getstartposition).  
  
 `key`  
 Параметр шаблона, указывающий тип ключа карты.  
  
 *значение*  
 Параметр шаблона, указывающий тип значения карты.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает указатель на текущей паре ключ значение элементов, содержащейся в схеме.  
  
### <a name="remarks"></a>Примечания  
 В отладочных построениях, произойдет ошибка утверждения, если `pos` равен NULL.  
  
##  <a name="getcount"></a>CAtlMap::GetCount  
 Вызовите этот метод для извлечения нескольких элементов в объекте map.  
  
```
size_t GetCount() const throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает число элементов в объекте map. Один элемент является парой ключ значение.  
  
### <a name="example"></a>Пример  
 Далее приведен пример [CAtlMap::CAtlMap](#catlmap).  
  
##  <a name="gethashtablesize"></a>CAtlMap::GetHashTableSize  
 Этот метод используется для определения количества сегментов в хэш-таблице карты.  
  
```
UINT GetHashTableSize() const throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает количество сегментов в хэш-таблице. В разделе [CAtlMap::CAtlMap](#catlmap) объяснение.  
  
##  <a name="getkeyat"></a>CAtlMap::GetKeyAt  
 Вызовите этот метод, чтобы получить ключ, хранящийся в заданном положении в `CAtlMap` объекта.  
  
```
const K& GetKeyAt(POSITION pos) const throw();
```  
  
### <a name="parameters"></a>Параметры  
 `pos`  
 Счетчик позиции, возвращенный предыдущим вызовом [CAtlMap::GetNextAssoc](#getnextassoc) или [CAtlMap::GetStartPosition](#getstartposition).  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает ссылку на ключ, хранящийся в заданном положении в `CAtlMap` объекта.  
  
### <a name="example"></a>Пример  
 Далее приведен пример [CAtlMap::CAtlMap](#catlmap).  
  
##  <a name="getnext"></a>CAtlMap::GetNext  
 Этот метод вызывается для получения указателя на следующий элемент, пара хранится в `CAtlMap` объекта.  
  
```
CPair* GetNext(POSITION& pos) throw();
const CPair* GetNext(POSITION& pos) const throw();
```  
  
### <a name="parameters"></a>Параметры  
 `pos`  
 Счетчик позиции, возвращенный предыдущим вызовом [CAtlMap::GetNextAssoc](#getnextassoc) или [CAtlMap::GetStartPosition](#getstartposition).  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает указатель на следующий пару ключ значение элементов, содержащейся в схеме. `pos` Позиции счетчик обновляется после каждого вызова. Если полученный элемент является последним в сопоставлении `pos` имеет значение NULL.  
  
##  <a name="getnextassoc"></a>CAtlMap::GetNextAssoc  
 Получает следующий элемент для выполнения итерации.  
  
```
void GetNextAssoc(
    POSITION& pos,
    KOUTARGTYPE key,
    VOUTARGTYPE value) const;
```  
  
### <a name="parameters"></a>Параметры  
 `pos`  
 Счетчик позиции, возвращенный предыдущим вызовом [CAtlMap::GetNextAssoc](#getnextassoc) или [CAtlMap::GetStartPosition](#getstartposition).  
  
 `key`  
 Параметр шаблона, указывающий тип ключа карты.  
  
 *значение*  
 Параметр шаблона, указывающий тип значения карты.  
  
### <a name="remarks"></a>Примечания  
 `pos` Позиции счетчик обновляется после каждого вызова. Если полученный элемент является последним в сопоставлении `pos` имеет значение NULL.  
  
##  <a name="getnextkey"></a>CAtlMap::GetNextKey  
 Этот метод вызывается для получения следующего ключа из `CAtlMap` объекта.  
  
```
const K& GetNextKey(POSITION& pos) const throw();
```  
  
### <a name="parameters"></a>Параметры  
 `pos`  
 Счетчик позиции, возвращенный предыдущим вызовом [CAtlMap::GetNextAssoc](#getnextassoc) или [CAtlMap::GetStartPosition](#getstartposition).  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает ссылку на следующий ключ в схеме.  
  
### <a name="remarks"></a>Примечания  
 Обновляет текущий счетчик позиции `pos`. Если больше нет элементов на карте, счетчик позиции будет равно NULL.  
  
##  <a name="getnextvalue"></a>CAtlMap::GetNextValue  
 Этот метод вызывается для получения следующего значения из `CAtlMap` объекта.  
  
```
V& GetNextValue(POSITION& pos) throw();
const V& GetNextValue(POSITION& pos) const throw();
```  
  
### <a name="parameters"></a>Параметры  
 `pos`  
 Счетчик позиции, возвращенный предыдущим вызовом [CAtlMap::GetNextAssoc](#getnextassoc) или [CAtlMap::GetStartPosition](#getstartposition).  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает ссылку на следующее значение в схеме.  
  
### <a name="remarks"></a>Примечания  
 Обновляет текущий счетчик позиции `pos`. Если больше нет элементов на карте, счетчик позиции будет равно NULL.  
  
### <a name="example"></a>Пример  
 Далее приведен пример [CAtlMap::CAtlMap](#catlmap).  
  
##  <a name="getstartposition"></a>CAtlMap::GetStartPosition  
 Этот метод перед началом итерации карты.  
  
```
POSITION GetStartPosition() const throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает начальную позицию, или значение NULL возвращается, если сопоставление пусто.  
  
### <a name="remarks"></a>Примечания  
 Этот метод вызывается для запуска итерации карты, возвращая **ПОЗИЦИИ** значение, которое может быть передан `GetNextAssoc` метод.  
  
> [!NOTE]
>  Порядковый номер итерации не является прогнозируемым  
  
### <a name="example"></a>Пример  
 Далее приведен пример [CAtlMap::CAtlMap](#catlmap).  
  
##  <a name="getvalueat"></a>CAtlMap::GetValueAt  
 Этот метод вызывается для получения значения, хранящиеся в заданном положении в `CAtlMap` объекта.  
  
```
V& GetValueAt(POSITION pos) throw();
const V& GetValueAt(POSITION pos) const throw();
```  
  
### <a name="parameters"></a>Параметры  
 `pos`  
 Счетчик позиции, возвращенный предыдущим вызовом [CAtlMap::GetNextAssoc](#getnextassoc) или [CAtlMap::GetStartPosition](#getstartposition).  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает ссылку на значение, хранящееся в заданном положении в `CAtlMap` объекта.  
  
##  <a name="inithashtable"></a>CAtlMap::InitHashTable  
 Этот метод вызывается для инициализации хэш-таблицы.  
  
```
bool InitHashTable(
    UINT nBins,
    bool bAllocNow = true);
```  
  
### <a name="parameters"></a>Параметры  
 `nBins`  
 Количество ячеек, используемый в хэш-таблице. В разделе [CAtlMap::CAtlMap](#catlmap) объяснение.  
  
 `bAllocNow`  
 Флаг указывает, когда следует выделить память.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает **true** на успешной инициализации **false** при сбое.  
  
### <a name="remarks"></a>Примечания  
 `InitHashTable`должен быть вызван, прежде чем какие-либо элементы хранятся в хэш-таблице.  Если этот метод не вызывается явно, он будет вызываться автоматически при первом добавлении число ячеек, заданные с помощью элемента **CAtlMap** конструктор.  В противном случае карты будет инициализирован с помощью нового числа bin, заданные `nBins` параметра.  
  
 Если `bAllocNow` параметр имеет значение false, не будет выделена память, необходимые для хэш-таблицы, пока это сначала требуется. Это может быть полезно, если неясно, будет ли использоваться карты.  
  
### <a name="example"></a>Пример  
 Далее приведен пример [CAtlMap::CAtlMap](#catlmap).  
  
##  <a name="isempty"></a>CAtlMap::IsEmpty  
 Этот метод используется для проверки объекта пустое сопоставление.  
  
```
bool IsEmpty() const throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает **true** Если сопоставление пусто, **false** в противном случае.  
  
##  <a name="kinargtype"></a>CAtlMap::KINARGTYPE  
 Тип, используемый при передаче ключа в качестве входного аргумента.  
  
```
typedef KTraits::INARGTYPE KINARGTYPE;
```  
  
##  <a name="koutargtype"></a>CAtlMap::KOUTARGTYPE  
 Тип, используемый при возврате ключ в виде выходного аргумент.  
  
```
typedef KTraits::OUTARGTYPE KOUTARGTYPE;
```  
  
##  <a name="lookup"></a>CAtlMap::Lookup  
 Вызовите этот метод для поиска разделов или значений в `CAtlMap` объекта.  
  
```
bool Lookup(KINARGTYPE key, VOUTARGTYPE value) const;
const CPair* Lookup(KINARGTYPE key) const throw();
CPair* Lookup(KINARGTYPE key) throw();
```  
  
### <a name="parameters"></a>Параметры  
 `key`  
 Задает ключ, определяющий элемента, который требуется найти.  
  
 *значение*  
 Переменная, принимающая значение поиск вверх.  
  
### <a name="return-value"></a>Возвращаемое значение  
 В первой форме метода возвращает значение true, если ключ найден, в противном случае — значение false. Второй и третий формы возвращают указатель на [CPair](#cpair_class) которого может использоваться в качестве позиции для вызовов [CAtlMap::GetNext](#getnext) и т. д.  
  
### <a name="remarks"></a>Примечания  
 `Lookup`использует алгоритм хэширования для быстрого поиска элемента карты, содержащего ключ, который совпадает с заданным параметром ключа.  
  
##  <a name="operator_at"></a>CAtlMap::operator\[\]  
 Заменяет или добавляет новый элемент в `CAtlMap`.  
  
```
V& operator[](kinargtype key) throw();
```  
  
### <a name="parameters"></a>Параметры  
 `key`  
 Ключ элемента для добавления или замены.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает ссылку на значение, связанное с указанным ключом.  
  
### <a name="example"></a>Пример  
 Если ключ уже существует, заменяется элемент. Если ключ не существует, добавляется новый элемент. Далее приведен пример [CAtlMap::CAtlMap](#catlmap).  
  
##  <a name="rehash"></a>CAtlMap::Rehash  
 Этот метод вызывается для rehash `CAtlMap` объекта.  
  
```
void Rehash(UINT nBins = 0);
```  
  
### <a name="parameters"></a>Параметры  
 `nBins`  
 Новое количество сегментов в хэш-таблице. В разделе [CAtlMap::CAtlMap](#catlmap) объяснение.  
  
### <a name="remarks"></a>Примечания  
 Если `nBins` равно 0, `CAtlMap` вычисляет разумные количества зависимости от числа элементов в карте и настройку оптимальной нагрузки. Обычно rehashing процесс происходит автоматически, но если [CAtlMap::DisableAutoRehash](#disableautorehash) был вызван, этот метод будет выполнять необходимые изменения размера.  
  
##  <a name="removeall"></a>CAtlMap::RemoveAll  
 Этот метод вызывается для удаления всех элементов из `CAtlMap` объекта.  
  
```
void RemoveAll() throw();
```  
  
### <a name="remarks"></a>Примечания  
 Очищает `CAtlMap` объект, память, используемую для хранения элементов.  
  
##  <a name="removeatpos"></a>CAtlMap::RemoveAtPos  
 Этот метод вызывается для удаления элемента в заданном положении в `CAtlMap` объекта.  
  
```
void RemoveAtPos(POSITION pos) throw();
```  
  
### <a name="parameters"></a>Параметры  
 `pos`  
 Счетчик позиции, возвращенный предыдущим вызовом [CAtlMap::GetNextAssoc](#getnextassoc) или [CAtlMap::GetStartPosition](#getstartposition).  
  
### <a name="remarks"></a>Примечания  
 Удаляет пара ключ значение, хранящиеся в указанной позиции. Память, используемая для сохранения элемента освобождается. ПОЗИЦИЯ ссылается `pos` становится недействительным, а пока положения других элементов в карте остается действительным, это не обязательно хранить том же порядке.  
  
##  <a name="removekey"></a>CAtlMap::RemoveKey  
 Этот метод вызывается для удаления элемента из `CAtlMap` объекту, заданному ключу.  
  
```
bool RemoveKey(KINARGTYPE key) throw();
```  
  
### <a name="parameters"></a>Параметры  
 `key`  
 Ключ, соответствующий пары элементов требуется удалить.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает **true** , если ключ найден и удален, **false** при сбое.  
  
### <a name="example"></a>Пример  
 Далее приведен пример [CAtlMap::CAtlMap](#catlmap).  
  
##  <a name="setat"></a>CAtlMap::SetAt  
 Этот метод служит для вставки пары элементов в сопоставление.  
  
```
POSITION SetAt(
    KINARGTYPE key,
    VINARGTYPE value);
```  
  
### <a name="parameters"></a>Параметры  
 `key`  
 Чтобы добавить значение ключа `CAtlMap` объекта.  
  
 *значение*  
 Значение для добавления `CAtlMap` объекта.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает позицию пары ключ значение элемента в `CAtlMap` объекта.  
  
### <a name="remarks"></a>Примечания  
 `SetAt`заменяет существующий элемент, если найден соответствующий ключ. Если ключ не найден, создается новый пара ключ значение.  
  
##  <a name="setoptimalload"></a>CAtlMap::SetOptimalLoad  
 Вызовите этот метод, чтобы задать оптимальную загрузку `CAtlMap` объекта.  
  
```
void SetOptimalLoad(
    float fOptimalLoad,
    float fLoThreshold,
    float fHiThreshold,
    bool bRehashNow = false);
```  
  
### <a name="parameters"></a>Параметры  
 `fOptimalLoad`  
 Отношение оптимальной нагрузки.  
  
 `fLoThreshold`  
 Нижнее пороговое значение для коэффициента нагрузки.  
  
 `fHiThreshold`  
 Верхнее пороговое значение для коэффициента нагрузки.  
  
 `bRehashNow`  
 Флаг, указывающий, хэш-таблицы должны быть пересчитаны.  
  
### <a name="remarks"></a>Примечания  
 Этот метод переопределяет значение оптимальной нагрузки для `CAtlMap` объекта. В разделе [CAtlMap::CAtlMap](#catlmap) Описание различных параметров. Если `bRehashNow` имеет значение true и число элементов, которое находится за пределами минимальное и максимальное значения, вычисляется хэш-таблицы.  
  
##  <a name="setvalueat"></a>CAtlMap::SetValueAt  
 Вызовите этот метод, чтобы изменить значение, хранящееся в заданном положении в `CAtlMap` объекта.  
  
```
void SetValueAt(
    POSITION pos,
    VINARGTYPE value);
```  
  
### <a name="parameters"></a>Параметры  
 `pos`  
 Счетчик позиции, возвращенный предыдущим вызовом [CAtlMap::GetNextAssoc](#getnextassoc) или [CAtlMap::GetStartPosition](#getstartposition).  
  
 *значение*  
 Значение для добавления `CAtlMap` объекта.  
  
### <a name="remarks"></a>Примечания  
 Изменяет значение элемента, хранимых в заданном положении в `CAtlMap` объекта.  
  
##  <a name="vinargtype"></a>CAtlMap::VINARGTYPE  
 Тип, используемый, когда значение передается в качестве входного аргумента.  
  
```
typedef VTraits::INARGTYPE VINARGTYPE;
```  
  
##  <a name="voutargtype"></a>CAtlMap::VOUTARGTYPE  
 Тип, используемый при передаче значения в виде выходного аргумент.  
  
```
typedef VTraits::OUTARGTYPE VOUTARGTYPE;
```  
  
##  <a name="m_key"></a>CAtlMap::CPair::m_key  
 Элемент данных хранения ключа элемента.  
  
```
const K m_key;
```    
  
### <a name="parameters"></a>Параметры  
 `K`  
 Тип ключа элемента.  
  
##  <a name="m_value"></a>CAtlMap::CPair::m_value  
 Элемент данных хранения значение элемента.  
  
```
V  m_value;
```    
  
### <a name="parameters"></a>Параметры  
 *V*  
 Тип значения элемента.  
  
## <a name="see-also"></a>См. также  
 [Образец Marquee](../../visual-cpp-samples.md)   
 [Образец UpdatePV](../../visual-cpp-samples.md)   
 [Общие сведения о классе](../../atl/atl-class-overview.md)
