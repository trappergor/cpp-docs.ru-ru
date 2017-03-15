---
title: "Класс CAtlMap | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- ATL.CAtlMap
- CAtlMap
- ATL::CAtlMap
dev_langs:
- C++
helpviewer_keywords:
- CAtlMap class
ms.assetid: 5e2fe028-8e6d-4686-93df-1433d2080ec3
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
ms.openlocfilehash: 3730827a56c47497db2fd8324f54c7ba88a584d6
ms.lasthandoff: 02/24/2017

---
# <a name="catlmap-class"></a>Класс CAtlMap
Этот класс предоставляет методы для создания и управления объект схемы.  
  
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
 Код, используемый для копирования или перемещения ключа элементов. В разделе [CElementTraits класса](../../atl/reference/celementtraits-class.md) для получения дополнительных сведений.  
  
 `VTraits`  
 Код, используемый для копирования или перемещения элементов значение.  
  
## <a name="members"></a>Члены  
  
### <a name="public-typedefs"></a>Общедоступные определения типов  
  
|Имя|Описание|  
|----------|-----------------|  
|[CAtlMap::KINARGTYPE](#kinargtype)|Тип, используемый при передаче ключа в качестве входного аргумента|  
|[CAtlMap::KOUTARGTYPE](#koutargtype)|Тип, используемый при возврате ключа в виде выходного аргумента.|  
|[CAtlMap::VINARGTYPE](#vinargtype)|Тип, используемый, когда значение передается в качестве входного аргумента.|  
|[CAtlMap::VOUTARGTYPE](#voutargtype)|Тип, используемый при передаче значения в виде выходного аргумент.|  
  
### <a name="public-classes"></a>Открытые классы  
  
|Имя|Описание|  
|----------|-----------------|  
|[Класс CAtlMap::CPair](#cpair_class)|Класс, содержащий ключ и значение элементов.|  

  
### <a name="cpair-data-members"></a>Члены данных CPair  
  
|Имя|Описание|  
|----------|-----------------|  
|[CPair::m_key](#m_key)|Элемент данных хранения ключа элемента.|  
|[CPair::m_value](#m_value)|Элемент данных хранения значение элемента.|  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CAtlMap::CAtlMap](#catlmap)|Конструктор.|  
|[CAtlMap:: ~ CAtlMap](#dtor)|Деструктор|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CAtlMap::AssertValid](#assertvalid)|Этот метод вызовет метод ASSERT, если `CAtlMap` является недопустимым.|  
|[CAtlMap::DisableAutoRehash](#disableautorehash)|Вызовите этот метод, чтобы отключить автоматическое проведя пересчет контрольной суммы из `CAtlMap` объекта.|  
|[CAtlMap::EnableAutoRehash](#enableautorehash)|Вызовите этот метод, чтобы включить автоматическое проведя пересчет контрольной суммы из `CAtlMap` объекта.|  
|[CAtlMap::GetAt](#getat)|Этот метод используется для возврата элемента в указанной позиции в сопоставлении.|  
|[CAtlMap::GetCount](#getcount)|Этот метод вызывается для получения количества элементов в сопоставлении.|  
|[CAtlMap::GetHashTableSize](#gethashtablesize)|Вызовите этот метод, чтобы определить количество сегментов в хэш-таблице карты.|  
|[CAtlMap::GetKeyAt](#getkeyat)|Этот метод вызывается для получения ключа, хранящегося в заданном положении в `CAtlMap` объекта.|  
|[CAtlMap::GetNext](#getnext)|Этот метод вызывается для получения указателя на следующий элемент, пара хранится в `CAtlMap` объекта.|  
|[CAtlMap::GetNextAssoc](#getnextassoc)|Получает следующий элемент для итерации.|  
|[CAtlMap::GetNextKey](#getnextkey)|Этот метод вызывается для получения следующего ключа из `CAtlMap` объекта.|  
|[CAtlMap::GetNextValue](#getnextvalue)|Этот метод вызывается для получения следующего значения из `CAtlMap` объекта.|  
|[CAtlMap::GetStartPosition](#getstartposition)|Этот метод перед началом итерации карты.|  
|[CAtlMap::GetValueAt](#getvalueat)|Вызовите этот метод, чтобы получить значение, хранящееся в заданном положении в `CAtlMap` объекта.|  
|[CAtlMap::InitHashTable](#inithashtable)|Этот метод вызывается для инициализации хэш-таблицы.|  
|[CAtlMap::IsEmpty](#isempty)|Этот метод используется для проверки объекта пустое сопоставление.|  
|[CAtlMap::Lookup](#lookup)|Этот метод вызывается для поиска разделов или значений в `CAtlMap` объекта.|  
|[CAtlMap::Rehash](#rehash)|Этот метод вызывается для rehash `CAtlMap` объекта.|  
|[CAtlMap::RemoveAll](#removeall)|Этот метод вызывается для удаления всех элементов из `CAtlMap` объекта.|  
|[CAtlMap::RemoveAtPos](#removeatpos)|Этот метод вызывается для удаления элемента в заданном положении в `CAtlMap` объекта.|  
|[CAtlMap::RemoveKey](#removekey)|Этот метод вызывается для удаления элемента из `CAtlMap` объекту, заданному ключу.|  
|[CAtlMap::SetAt](#setat)|Этот метод используется для вставки пары элементов в схеме.|  
|[CAtlMap::SetOptimalLoad](#setoptimalload)|Вызовите этот метод, чтобы задать оптимальной нагрузки из `CAtlMap` объекта.|  
|[CAtlMap::SetValueAt](#setvalueat)|Вызовите этот метод, чтобы изменить значение, хранящееся в заданном положении в `CAtlMap` объекта.|  
  
### <a name="public-operators"></a>Открытые операторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CAtlMap::operator\[\]](catlmap-class.md#operator_at)|Заменяет или добавляет новый элемент в `CAtlMap`.|  

  
## <a name="remarks"></a>Примечания  
 `CAtlMap`обеспечивает поддержку для любого заданного типа, управление массив неупорядоченных ключевые элементы и связанные с ними значения массива сопоставления. Элементы (состоящие из ключа и значения) хранятся с использованием хэш-алгоритм, позволяя большой объем данных, чтобы эффективно хранить и извлекать.  
  
 `KTraits` И `VTraits` параметры являются признаками классы, содержащие любой дополнительный код, необходимые для копирования или перемещения элементов.  
  
 Альтернатива `CAtlMap` предлагаемых [CRBMap](../../atl/reference/crbmap-class.md) класса. `CRBMap`также хранит пары «ключ значение», но демонстрирует различные характеристики производительности. Время, необходимое для вставки элемента, поиска ключа или удалить ключ из `CRBMap` объект является заказа *log(n)*, где *n* — число элементов. Для `CAtlMap`, все эти операции обычно занять константой времени, несмотря на то, что пессимистичный сценарии могут быть заказа *n*. Таким образом, в обычном случае `CAtlMap` выполняется быстрее.  
  
 Другое различие между `CRBMap` и `CAtlMap` становится очевидной при итерации хранимых элементов. В `CRBMap`, элементы, обходятся в отсортированном порядке. В `CAtlMap`, элементы не упорядочены и порядок не может быть выведен.  
  
 Когда небольшое количество элементов должны храниться, рассмотрите возможность использования [CSimpleMap](../../atl/reference/csimplemap-class.md) вместо этого класс.  
  
 Дополнительные сведения см. в разделе [классы коллекций ATL](../../atl/atl-collection-classes.md).  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atlcoll.h  
  
##  <a name="a-nameassertvalida--catlmapassertvalid"></a><a name="assertvalid"></a>CAtlMap::AssertValid  
 Этот метод вызовет метод ASSERT, если `CAtlMap` недопустимый объект.  
  
```
void AssertValid() const;
```  
  
### <a name="remarks"></a>Примечания  
 В отладочных построениях, этот метод вызовет ASSERT Если `CAtlMap` недопустимый объект.  
  
### <a name="example"></a>Пример  
 В примере показано [CAtlMap::CAtlMap](#catlmap).  
  
##  <a name="a-namecatlmapa--catlmapcatlmap"></a><a name="catlmap"></a>CAtlMap::CAtlMap  
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
 Количество ячеек, ссылки на хранимых элементов. Далее в этом разделе для пояснения ячейки см. заметки.  
  
 `fOptimalLoad`  
 Отношение оптимальной нагрузки.  
  
 `fLoThreshold`  
 Нижнее пороговое значение коэффициента нагрузки.  
  
 `fHiThreshold`  
 Верхнее пороговое значение коэффициента нагрузки.  
  
 `nBlockSize`  
 Размер блока.  
  
### <a name="remarks"></a>Примечания  
 `CAtlMap`ссылается на все его элементы хранимых создав с помощью хэш-алгоритм для ключа индекса. Этот индекс ссылается на «bin», который содержит указатель на хранимых элементов. Если ячейка уже используется, для доступа к элементам последующих создается в связанном списке. Обход списка выполняется медленнее, чем прямой доступ к правильный элемент и поэтому структуры карты необходимо сбалансировать требования к хранилищу с точки зрения производительности. Параметры по умолчанию были выбраны для предоставления хорошие результаты в большинстве случаев.  
  
 Коэффициент нагрузки — это отношение числа ячеек на количество элементов, хранящихся в объекте map. При пересчете структуры карты *fOptimalLoad* значение параметра будет использоваться для вычисления числа ячеек, которые требуется. Это значение можно изменить с помощью [CAtlMap::SetOptimalLoad](#setoptimalload) метод.  
  
 `fLoThreshold` Параметр имеет меньшее значение, коэффициент нагрузки, при достижении `CAtlMap` приведет к пересчету оптимальный размер карты.  
  
 `fHiThreshold` Параметра значение в верхнем коэффициент нагрузки, при достижении `CAtlMap` объекта приведет к пересчету оптимальный размер карты.  
  
 Этот процесс пересчета (известный как проведя пересчет контрольной суммы) включен по умолчанию. Если вы хотите отключить этот процесс, возможно, при вводе множества данных за один раз вызов [CAtlMap::DisableAutoRehash](#disableautorehash) метод. Повторно активировать его с [CAtlMap::EnableAutoRehash](#enableautorehash) метод.  
  
 `nBlockSize` Параметр измеряется объем памяти, выделяемый при новый элемент является обязательным. Размер блока Уменьшите количество вызовов процедур выделения памяти, но использует больше ресурсов.  
  
 Прежде чем можно будет сохранить любые данные, он необходим для инициализации хэш-таблицы с помощью вызова [CAtlMap::InitHashTable](#inithashtable).  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATL_Utilities&#72;](../../atl/codesnippet/cpp/catlmap-class_1.cpp)]  
  
##  <a name="a-namedtora--catlmapcatlmap"></a><a name="dtor"></a>CAtlMap:: ~ CAtlMap  
 Деструктор  
  
```
~CAtlMap() throw();
```  
  
### <a name="remarks"></a>Примечания  
 Освобождает все ресурсы, выделенные.  
  
##  <a name="a-namecpairclassa--catlmapcpair-class"></a><a name="cpair_class"></a>Класс CAtlMap::CPair  
 Класс, содержащий ключ и значение элементов.  
  
```
class CPair : public __POSITION
```  
  
### <a name="remarks"></a>Примечания  
 Этот класс используется методами [CAtlMap::GetNext](#getnext) и [CAtlMap::Lookup](#lookup) для доступа к элементам ключ и значение, хранящееся в структуре сопоставления.  
  
##  <a name="a-namedisableautorehasha--catlmapdisableautorehash"></a><a name="disableautorehash"></a>CAtlMap::DisableAutoRehash  
 Вызовите этот метод, чтобы отключить автоматическое проведя пересчет контрольной суммы из `CAtlMap` объекта.  
  
```
void DisableAutoRehash() throw();
```  
  
### <a name="remarks"></a>Примечания  
 Если автоматическое проведя пересчет контрольной суммы включена (что и происходит по умолчанию), количество сегментов в хэш-таблице автоматически повторное вычисление, если значение load (отношение числа ячеек на количество элементов, хранящихся в массиве) превышает максимальное или минимальное значения, указанного во время создания карты.  
  
 `DisableAutoRehash`может пригодиться, когда большое количество элементов будут добавлены на карту за один раз. Вместо запуска процесса rehashing каждый раз при превышении ограничений, эффективнее вызывать `DisableAutoRehash`, добавить элементы и Наконец вызовите [CAtlMap::EnableAutoRehash](#enableautorehash).  
  
##  <a name="a-nameenableautorehasha--catlmapenableautorehash"></a><a name="enableautorehash"></a>CAtlMap::EnableAutoRehash  
 Вызовите этот метод, чтобы включить автоматическое проведя пересчет контрольной суммы из `CAtlMap` объекта.  
  
```
void EnableAutoRehash() throw();
```  
  
### <a name="remarks"></a>Примечания  
 Если автоматическое проведя пересчет контрольной суммы включена (что и происходит по умолчанию), количество сегментов в хэш-таблице автоматически повторное вычисление, если значение load (отношение числа ячеек на количество элементов, хранящихся в массиве) превышает максимальное или минимальное значения, указанного во время создания карты.  
  
 **EnableAutoRefresh** наиболее часто используется после вызова [CAtlMap::DisableAutoRehash](#disableautorehash).  
  
##  <a name="a-namegetata--catlmapgetat"></a><a name="getat"></a>CAtlMap::GetAt  
 Этот метод используется для возврата элемента в указанной позиции в сопоставлении.  
  
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
 Параметр шаблона, указав тип ключа карты.  
  
 *value*  
 Параметр шаблона, указав тип значения карты.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает указатель текущей паре ключ значение элементов в сопоставлении.  
  
### <a name="remarks"></a>Примечания  
 В отладочных построениях, произойдет ошибка утверждения, если `pos` равен NULL.  
  
##  <a name="a-namegetcounta--catlmapgetcount"></a><a name="getcount"></a>CAtlMap::GetCount  
 Этот метод вызывается для получения количества элементов в сопоставлении.  
  
```
size_t GetCount() const throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает число элементов в объекте map. Единственный элемент является парой ключ значение.  
  
### <a name="example"></a>Пример  
 В примере показано [CAtlMap::CAtlMap](#catlmap).  
  
##  <a name="a-namegethashtablesizea--catlmapgethashtablesize"></a><a name="gethashtablesize"></a>CAtlMap::GetHashTableSize  
 Вызовите этот метод, чтобы определить количество сегментов в хэш-таблице карты.  
  
```
UINT GetHashTableSize() const throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает количество сегментов в хэш-таблице. В разделе [CAtlMap::CAtlMap](#catlmap) объяснение.  
  
##  <a name="a-namegetkeyata--catlmapgetkeyat"></a><a name="getkeyat"></a>CAtlMap::GetKeyAt  
 Этот метод вызывается для получения ключа, хранящегося в заданном положении в `CAtlMap` объекта.  
  
```
const K& GetKeyAt(POSITION pos) const throw();
```  
  
### <a name="parameters"></a>Параметры  
 `pos`  
 Счетчик позиции, возвращенный предыдущим вызовом [CAtlMap::GetNextAssoc](#getnextassoc) или [CAtlMap::GetStartPosition](#getstartposition).  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает ссылку на ключ, хранящийся в заданном положении в `CAtlMap` объекта.  
  
### <a name="example"></a>Пример  
 В примере показано [CAtlMap::CAtlMap](#catlmap).  
  
##  <a name="a-namegetnexta--catlmapgetnext"></a><a name="getnext"></a>CAtlMap::GetNext  
 Этот метод вызывается для получения указателя на следующий элемент, пара хранится в `CAtlMap` объекта.  
  
```
CPair* GetNext(POSITION& pos) throw();
const CPair* GetNext(POSITION& pos) const throw();
```  
  
### <a name="parameters"></a>Параметры  
 `pos`  
 Счетчик позиции, возвращенный предыдущим вызовом [CAtlMap::GetNextAssoc](#getnextassoc) или [CAtlMap::GetStartPosition](#getstartposition).  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает указатель на следующая пара ключ значение элементов в сопоставлении. `pos` Положение счетчик обновляется после каждого вызова. Если полученный элемент является последним в схеме, `pos` имеет значение NULL.  
  
##  <a name="a-namegetnextassoca--catlmapgetnextassoc"></a><a name="getnextassoc"></a>CAtlMap::GetNextAssoc  
 Получает следующий элемент для итерации.  
  
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
 Параметр шаблона, указав тип ключа карты.  
  
 *value*  
 Параметр шаблона, указав тип значения карты.  
  
### <a name="remarks"></a>Примечания  
 `pos` Положение счетчик обновляется после каждого вызова. Если полученный элемент является последним в схеме, `pos` имеет значение NULL.  
  
##  <a name="a-namegetnextkeya--catlmapgetnextkey"></a><a name="getnextkey"></a>CAtlMap::GetNextKey  
 Этот метод вызывается для получения следующего ключа из `CAtlMap` объекта.  
  
```
const K& GetNextKey(POSITION& pos) const throw();
```  
  
### <a name="parameters"></a>Параметры  
 `pos`  
 Счетчик позиции, возвращенный предыдущим вызовом [CAtlMap::GetNextAssoc](#getnextassoc) или [CAtlMap::GetStartPosition](#getstartposition).  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает ссылку на следующий ключ в сопоставлении.  
  
### <a name="remarks"></a>Примечания  
 Обновляет текущий счетчик позиции `pos`. Если в схеме есть больше нет записей, положение счетчика имеет значение NULL.  
  
##  <a name="a-namegetnextvaluea--catlmapgetnextvalue"></a><a name="getnextvalue"></a>CAtlMap::GetNextValue  
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
 Обновляет текущий счетчик позиции `pos`. Если в схеме есть больше нет записей, положение счетчика имеет значение NULL.  
  
### <a name="example"></a>Пример  
 В примере показано [CAtlMap::CAtlMap](#catlmap).  
  
##  <a name="a-namegetstartpositiona--catlmapgetstartposition"></a><a name="getstartposition"></a>CAtlMap::GetStartPosition  
 Этот метод перед началом итерации карты.  
  
```
POSITION GetStartPosition() const throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает начальную позицию, или значение NULL возвращается, если сопоставление является пустым.  
  
### <a name="remarks"></a>Примечания  
 Этот метод перед началом выполнения итерации карты, возвращая **ПОЗИЦИИ** значение, которое может быть передан `GetNextAssoc` метод.  
  
> [!NOTE]
>  Последовательности итерации не является прогнозируемым  
  
### <a name="example"></a>Пример  
 В примере показано [CAtlMap::CAtlMap](#catlmap).  
  
##  <a name="a-namegetvalueata--catlmapgetvalueat"></a><a name="getvalueat"></a>CAtlMap::GetValueAt  
 Вызовите этот метод, чтобы получить значение, хранящееся в заданном положении в `CAtlMap` объекта.  
  
```
V& GetValueAt(POSITION pos) throw();
const V& GetValueAt(POSITION pos) const throw();
```  
  
### <a name="parameters"></a>Параметры  
 `pos`  
 Счетчик позиции, возвращенный предыдущим вызовом [CAtlMap::GetNextAssoc](#getnextassoc) или [CAtlMap::GetStartPosition](#getstartposition).  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает ссылку на значение, хранящееся в заданном положении в `CAtlMap` объекта.  
  
##  <a name="a-nameinithashtablea--catlmapinithashtable"></a><a name="inithashtable"></a>CAtlMap::InitHashTable  
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
 Возвращает **true** на успешной инициализации **false** в случае сбоя.  
  
### <a name="remarks"></a>Примечания  
 `InitHashTable`должен быть вызван, прежде чем какие-либо элементы хранятся в хэш-таблице.  Если этот метод не вызывается явно, он будет вызываться автоматически при первом добавлении число ячеек, заданные с помощью элемента **CAtlMap** конструктор.  В противном случае — карты будет инициализирована с использованием нового bin счетчика, `nBins` параметр.  
  
 Если `bAllocNow` параметр имеет значение false, пока это сначала требуется не будет выделена памяти, необходимый для хэш-таблицы. Это может быть полезно, если неясно, будет ли использоваться карты.  
  
### <a name="example"></a>Пример  
 В примере показано [CAtlMap::CAtlMap](#catlmap).  
  
##  <a name="a-nameisemptya--catlmapisempty"></a><a name="isempty"></a>CAtlMap::IsEmpty  
 Этот метод используется для проверки объекта пустое сопоставление.  
  
```
bool IsEmpty() const throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает **true** Если сопоставление является пустым, **false** в противном случае.  
  
##  <a name="a-namekinargtypea--catlmapkinargtype"></a><a name="kinargtype"></a>CAtlMap::KINARGTYPE  
 Тип, используемый при передаче ключа в качестве входного аргумента.  
  
```
typedef KTraits::INARGTYPE KINARGTYPE;
```  
  
##  <a name="a-namekoutargtypea--catlmapkoutargtype"></a><a name="koutargtype"></a>CAtlMap::KOUTARGTYPE  
 Тип, используемый при возврате ключа в виде выходного аргумента.  
  
```
typedef KTraits::OUTARGTYPE KOUTARGTYPE;
```  
  
##  <a name="a-namelookupa--catlmaplookup"></a><a name="lookup"></a>CAtlMap::Lookup  
 Этот метод вызывается для поиска разделов или значений в `CAtlMap` объекта.  
  
```
bool Lookup(KINARGTYPE key, VOUTARGTYPE value) const;
const CPair* Lookup(KINARGTYPE key) const throw();
CPair* Lookup(KINARGTYPE key) throw();
```  
  
### <a name="parameters"></a>Параметры  
 `key`  
 Задает ключ, определяющий элемента, который требуется найти.  
  
 *value*  
 Переменная, получающая значение поиск вверх.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Первая форма метода возвращает значение true, если ключ найден, в противном случае — значение false. Второй и третий форм возвращать указатель [CPair](#cpair_class) которого может использоваться в качестве позиции для вызовов [CAtlMap::GetNext](#getnext) и т. д.  
  
### <a name="remarks"></a>Примечания  
 `Lookup`Чтобы быстро найти элемент карты, содержащий ключ, который совпадает с заданным параметром ключа использует алгоритм хэширования.  
  
##  <a name="a-nameoperatorata--catlmapoperator-"></a><a name="operator_at"></a>CAtlMap::operator\[\]  
 Заменяет или добавляет новый элемент в `CAtlMap`.  
  
```
V& operator[](kinargtype key) throw();
```  
  
### <a name="parameters"></a>Параметры  
 `key`  
 Ключ элемента, который требуется добавить или заменить.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает ссылку на значение, связанное с указанным ключом.  
  
### <a name="example"></a>Пример  
 Если ключ уже существует, заменяется элемент. Если ключ не существует, добавляется новый элемент. В примере показано [CAtlMap::CAtlMap](#catlmap).  
  
##  <a name="a-namerehasha--catlmaprehash"></a><a name="rehash"></a>CAtlMap::Rehash  
 Этот метод вызывается для rehash `CAtlMap` объекта.  
  
```
void Rehash(UINT nBins = 0);
```  
  
### <a name="parameters"></a>Параметры  
 `nBins`  
 Новое количество сегментов в хэш-таблице. В разделе [CAtlMap::CAtlMap](#catlmap) объяснение.  
  
### <a name="remarks"></a>Примечания  
 Если `nBins` равно 0, `CAtlMap` вычисляет разумные количества, в зависимости от числа элементов в схеме и оптимальной нагрузочного. Обычно rehashing процесс происходит автоматически, но если [CAtlMap::DisableAutoRehash](#disableautorehash) был вызван, этот метод будет выполнять необходимые изменения размера.  
  
##  <a name="a-nameremovealla--catlmapremoveall"></a><a name="removeall"></a>CAtlMap::RemoveAll  
 Этот метод вызывается для удаления всех элементов из `CAtlMap` объекта.  
  
```
void RemoveAll() throw();
```  
  
### <a name="remarks"></a>Примечания  
 Очищает `CAtlMap` объект, память, используемую для хранения элементов.  
  
##  <a name="a-nameremoveatposa--catlmapremoveatpos"></a><a name="removeatpos"></a>CAtlMap::RemoveAtPos  
 Этот метод вызывается для удаления элемента в заданном положении в `CAtlMap` объекта.  
  
```
void RemoveAtPos(POSITION pos) throw();
```  
  
### <a name="parameters"></a>Параметры  
 `pos`  
 Счетчик позиции, возвращенный предыдущим вызовом [CAtlMap::GetNextAssoc](#getnextassoc) или [CAtlMap::GetStartPosition](#getstartposition).  
  
### <a name="remarks"></a>Примечания  
 Удаляет пар ключ/значение, хранящееся в указанной позиции. Освобождается память, используемая для сохранения элемента. ПОЗИЦИЯ ссылается `pos` становится недействительным и хотя положения других элементов в сопоставлении остается действительным, это не обязательно сохраняйте порядке.  
  
##  <a name="a-nameremovekeya--catlmapremovekey"></a><a name="removekey"></a>CAtlMap::RemoveKey  
 Этот метод вызывается для удаления элемента из `CAtlMap` объекту, заданному ключу.  
  
```
bool RemoveKey(KINARGTYPE key) throw();
```  
  
### <a name="parameters"></a>Параметры  
 `key`  
 Ключ, соответствующий пары элементов требуется удалить.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает **true** , если ключ найден и удален, **false** в случае сбоя.  
  
### <a name="example"></a>Пример  
 В примере показано [CAtlMap::CAtlMap](#catlmap).  
  
##  <a name="a-namesetata--catlmapsetat"></a><a name="setat"></a>CAtlMap::SetAt  
 Этот метод используется для вставки пары элементов в схеме.  
  
```
POSITION SetAt(
    KINARGTYPE key,
    VINARGTYPE value);
```  
  
### <a name="parameters"></a>Параметры  
 `key`  
 Значение ключа, чтобы добавить `CAtlMap` объекта.  
  
 *value*  
 Значение для добавления `CAtlMap` объекта.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает позицию первого элемента пары ключ значение в `CAtlMap` объекта.  
  
### <a name="remarks"></a>Примечания  
 `SetAt`заменяет существующий элемент, если найден соответствующий ключ. Если ключ не найден, создается новую пару ключ значение.  
  
##  <a name="a-namesetoptimalloada--catlmapsetoptimalload"></a><a name="setoptimalload"></a>CAtlMap::SetOptimalLoad  
 Вызовите этот метод, чтобы задать оптимальной нагрузки из `CAtlMap` объекта.  
  
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
 Нижнее пороговое значение коэффициента нагрузки.  
  
 `fHiThreshold`  
 Верхнее пороговое значение коэффициента нагрузки.  
  
 `bRehashNow`  
 Флаг, обозначающий хэш-таблицы должны быть пересчитаны.  
  
### <a name="remarks"></a>Примечания  
 Этот метод переопределяет значение оптимальной нагрузки `CAtlMap` объекта. В разделе [CAtlMap::CAtlMap](#catlmap) для обсуждения различных параметров. Если `bRehashNow` имеет значение true и число элементов, которое находится за пределами минимального и максимального значений, пересчитываются хэш-таблицы.  
  
##  <a name="a-namesetvalueata--catlmapsetvalueat"></a><a name="setvalueat"></a>CAtlMap::SetValueAt  
 Вызовите этот метод, чтобы изменить значение, хранящееся в заданном положении в `CAtlMap` объекта.  
  
```
void SetValueAt(
    POSITION pos,
    VINARGTYPE value);
```  
  
### <a name="parameters"></a>Параметры  
 `pos`  
 Счетчик позиции, возвращенный предыдущим вызовом [CAtlMap::GetNextAssoc](#getnextassoc) или [CAtlMap::GetStartPosition](#getstartposition).  
  
 *value*  
 Значение для добавления `CAtlMap` объекта.  
  
### <a name="remarks"></a>Примечания  
 Изменяет значение элемента, хранимых в заданном положении в `CAtlMap` объекта.  
  
##  <a name="a-namevinargtypea--catlmapvinargtype"></a><a name="vinargtype"></a>CAtlMap::VINARGTYPE  
 Тип, используемый, когда значение передается в качестве входного аргумента.  
  
```
typedef VTraits::INARGTYPE VINARGTYPE;
```  
  
##  <a name="a-namevoutargtypea--catlmapvoutargtype"></a><a name="voutargtype"></a>CAtlMap::VOUTARGTYPE  
 Тип, используемый при передаче значения в виде выходного аргумент.  
  
```
typedef VTraits::OUTARGTYPE VOUTARGTYPE;
```  
  
##  <a name="a-namemkeya--catlmapcpairmkey"></a><a name="m_key"></a>CAtlMap::CPair::m_key  
 Элемент данных хранения ключа элемента.  
  
```
const K m_key;
```    
  
### <a name="parameters"></a>Параметры  
 `K`  
 Тип ключа элемента.  
  
##  <a name="a-namemvaluea--catlmapcpairmvalue"></a><a name="m_value"></a>CAtlMap::CPair::m_value  
 Элемент данных хранения значение элемента.  
  
```
V  m_value;
```    
  
### <a name="parameters"></a>Параметры  
 *V*  
 Тип значения элемента.  
  
## <a name="see-also"></a>См. также  
 [Образец бегущей строки](../../visual-cpp-samples.md)   
 [Пример в этом примере](../../visual-cpp-samples.md)   
 [Общие сведения о классе](../../atl/atl-class-overview.md)

