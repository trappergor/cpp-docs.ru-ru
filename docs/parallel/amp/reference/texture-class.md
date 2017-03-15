---
title: "Класс Texture | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- amp_graphics/Concurrency::graphics::texture
dev_langs:
- C++
ms.assetid: 16e85d4d-e80a-474a-995d-8bf63fbdf34c
caps.latest.revision: 9
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
ms.sourcegitcommit: fc190feb08d9b221cd1cc21a9c91ad567c86c848
ms.openlocfilehash: aafb23ac4d366baed37f1cf667984253160af9c3
ms.lasthandoff: 02/24/2017

---
# <a name="texture-class"></a>Класс texture
Текстура — на статистических данных `accelerator_view` в домене экстента. Это коллекция переменных, по одной для каждого элемента в домене экстента. Каждая переменная содержит значение, соответствующее примитивный тип C++ ( `unsigned int`, `int`, `float`, `double`), скалярный тип ( `norm`, или `unorm`), или тип короткого вектора.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
template <
    typename value_type,  
    int _Rank  
>  
class texture;  
```  
  
#### <a name="parameters"></a>Параметры  
 `value_type`  
 Тип элементов в текстуре.  
  
 `_Rank`  
 Ранг текстуры.  
  
## <a name="members"></a>Члены  
  
### <a name="public-typedefs"></a>Общедоступные определения типов  
  
|Имя|Описание|  
|----------|-----------------|  
|`scalar_type`|Скалярные типы.|  
|`value_type`|Типы значений.|  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[Конструктор текстуры](#ctor)|Инициализирует новый экземпляр класса `texture`.|  
|[~ texture деструктор](#ctor)|Уничтожает `texture` объекта.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[copy_to метод](#copy_to)|Копирует `texture` объекта назначения, выполняя глубокую копию.|  
|[Метод данных](#data)|Возвращает указатель ЦП необработанные данные этой текстуры.|  
|[GET-метод](#get)|Возвращает значение элемента по указанному индексу.|  
|[get_associated_accelerator_view метод](#get_associated_accelerator_view)|Возвращает [accelerator_view](accelerator-view-class.md) Это предпочтительный объект для этой текстуры для копирования.|  
|[Метод get_depth_pitch](#get_depth_pitch)|Возвращает число байтов между каждого среза глубины в трехмерном пространстве, промежуточных текстуры на ЦП.|  
|[Метод get_row_pitch](#get_row_pitch)|Возвращает число байтов между каждой строки в 2D или 3D, промежуточных текстуры на ЦП.|  
|[Метод Set](#set)|Задает значение элемента по указанному индексу.|  
  
### <a name="public-operators"></a>Открытые операторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[Оператор Operator()](#operator_call)|Возвращает значение элемента, определяются параметрами.|  
|[Оператор Operator]](#operator_at)|Возвращает элемент, который находится по указанному индексу.|  
|[оператор =-оператор](#operator_eq)|Копирует указанный [текстуры](texture-class.md) этого объекта.|  
  
### <a name="public-constants"></a>Открытые константы  
  
|Имя|Описание|  
|----------|-----------------|  
|[Ранг константа](#rank)|Возвращает ранг `texture` объекта.|  
  
### <a name="public-data-members"></a>Открытые члены данных  
  
|Имя|Описание|  
|----------|-----------------|  
|[associated_accelerator_view элемент данных](#associated_accelerator_view)|Возвращает [accelerator_view](accelerator-view-class.md) Это предпочтительный объект для этой текстуры для копирования.|  
|[depth_pitch элемент данных](#depth_pitch)|Возвращает число байтов между каждого среза глубины в промежуточной трехмерную текстуру на ЦП.|  
|[row_pitch элемент данных](#row_pitch)|Возвращает число байтов между каждой строки в 2D или 3D промежуточной текстуры на ЦП.|  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `_Texture_base`  
  
 `texture`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** amp_graphics.h  
  
 **Пространство имен:** Concurrency::graphics  
  
##  <a name="a-namedtora-texture"></a><a name="dtor"></a>~ текстуры 

 Уничтожает `texture` объекта.  
  
```  
~texture() restrict(cpu);
```  
  
##  <a name="a-nameassociatedacceleratorviewa-associatedacceleratorview"></a><a name="associated_accelerator_view"></a>associated_accelerator_view 

 Возвращает [accelerator_view](accelerator-view-class.md) Это предпочтительный объект для этой текстуры для копирования.  
  
```  
__declspec(property(get= get_associated_accelerator_view)) Concurrency::accelerator_view associated_accelerator_view;  
```  
  
##  <a name="a-namecopytoa-copyto"></a><a name="copy_to"></a>copy_to 

 Копирует `texture` объекта назначения, выполняя глубокую копию.  
  
```  
void copy_to(
    texture& _Dest) const;

 
 
void copy_to(
    writeonly_texture_view<value_type, _Rank>& _Dest) const;

 
```  
  
### <a name="parameters"></a>Параметры  
 `_Dest`  
 Объект для копирования.  
  
 `_Rank`  
 Ранг текстуры.  
  
 `value_type`  
 Тип элементов в текстуре.  
  
##  <a name="a-namedataa-data"></a><a name="data"></a>данные 

 Возвращает указатель ЦП необработанные данные этой текстуры.  
  
```  
void* data() restrict(cpu);

 
const void* data() const restrict(cpu);
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на необработанные данные текстуры.  
  
##  <a name="a-namedepthpitcha-depthpitch"></a><a name="depth_pitch"></a>depth_pitch 

 Возвращает число байтов между каждого среза глубины в промежуточной трехмерную текстуру на ЦП.  
  
```  
__declspec(property(get= get_depth_pitch)) unsigned int depth_pitch;  
```  
  
##  <a name="a-namegeta-get"></a><a name="get"></a>Получить 

 Возвращает значение элемента по указанному индексу.  
  
```  
const value_type get(const index<_Rank>& _Index) const restrict(amp);
```  
  
### <a name="parameters"></a>Параметры  
 `_Index`  
 Индекс элемента.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение элемента по указанному индексу.  
  
##  <a name="a-namegetassociatedacceleratorviewa-getassociatedacceleratorview"></a><a name="get_associated_accelerator_view"></a>get_associated_accelerator_view 

 Возвращает accelerator_view, который является основной целью для этой текстуры для копирования.  
  
```  
Concurrency::accelerator_view get_associated_accelerator_view() const restrict(cpu);
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 [Accelerator_view](accelerator-view-class.md) Это предпочтительный объект для этой текстуры для копирования.  
  
##  <a name="a-namegetdepthpitcha-getdepthpitch"></a><a name="get_depth_pitch"></a>get_depth_pitch 

 Возвращает число байтов между каждого среза глубины в трехмерном пространстве, промежуточных текстуры на ЦП.  
  
```  
unsigned int get_depth_pitch() const restrict(cpu);
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Число байтов между каждого среза глубины в трехмерном пространстве, промежуточных текстуры на ЦП.  
  
##  <a name="a-namegetrowpitcha-getrowpitch"></a><a name="get_row_pitch"></a>get_row_pitch 

 Возвращает число байтов, между каждой строки в двумерные промежуточной текстуры или каждой строки срез глубиной в 3-мерная промежуточной текстуры.  
  
```  
unsigned int get_row_pitch() const restrict(cpu);
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Число байтов между каждой строки в двумерные промежуточной текстуры или каждой строки срез глубиной в 3-мерная промежуточной текстуры.  
  
##  <a name="a-nameoperatorcalla-operator"></a><a name="operator_call"></a>Operator() 

 Возвращает значение элемента, определяются параметрами.  
  
```  
const value_type operator() (
    const index<_Rank>& _Index) const restrict(amp);

 
const value_type operator() (
    int _I0) const restrict(amp);

 
const value_type operator() (
    int _I0,  
    int _I1) const restrict(amp);

 
const value_type operator() (
    int _I0,  
    int _I1,  
    int _I2) const restrict(amp);
```  
  
### <a name="parameters"></a>Параметры  
 `_Index`  
 Индекс.  
  
 `_I0`  
 Наиболее значимый компонент индекса.  
  
 `_I1`  
 Далее к значащий компонент индекса.  
  
 `_I2`  
 Наименее значимый компонент индекса.  
  
 `_Rank`  
 Ранг индекса.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение элемента, определяются параметрами.  
  
##  <a name="a-nameoperatorata-operator"></a><a name="operator_at"></a>оператор] 

 Возвращает элемент, который находится по указанному индексу.  
  
```  
const value_type operator[] (const index<_Rank>& _Index) const restrict(amp);

 
const value_type operator[] (int _I0) const restrict(amp);
```  
  
### <a name="parameters"></a>Параметры  
 `_Index`  
 Индекс.  
  
 `_I0`  
 Индекс.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Элемент, который находится по указанному индексу.  
  
##  <a name="a-nameoperatoreqa-operator"></a><a name="operator_eq"></a>оператор = 

 Копирует указанный [текстуры](texture-class.md) этого объекта.  
  
```  
texture& operator= (
    const texture& _Other);

 
texture& operator= (
    texture<value_type, _Rank>&& _Other);
```  
  
### <a name="parameters"></a>Параметры  
 `_Other`  
 `texture` Для копирования.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ссылку на это `texture` объекта.  
  
##  <a name="a-nameranka-rank"></a><a name="rank"></a>Ранг 

 Возвращает ранг `texture` объекта.  
  
```  
static const int rank = _Rank;  
```  
  
##  <a name="a-namerowpitcha-rowpitch"></a><a name="row_pitch"></a>row_pitch 

 Возвращает число байтов между каждой строки в 2D или 3D промежуточной текстуры на ЦП.  
  
```  
__declspec(property(get= get_row_pitch)) unsigned int row_pitch;  
```  
  
##  <a name="a-nameseta-set"></a><a name="set"></a>набор 

 Задает значение элемента по указанному индексу.  
  
```  
void set(
    const index<_Rank>& _Index,  
    const value_type& value) restrict(amp);
```  
  
### <a name="parameters"></a>Параметры  
 `_Index`  
 Индекс элемента.  
  
 `_Rank`  
 Ранг индекса.  
  
 `value`  
 Новое значение элемента.  
  
##  <a name="a-namectora-texture"></a><a name="ctor"></a>текстуры 

 Инициализирует новый экземпляр класса `texture`.  
  
```  
texture(
    const Concurrency::extent<_Rank>& _Ext) restrict(cpu);

 
texture(
    int _E0) restrict(cpu);

 
texture(
    int _E0,  
    int _E1) restrict(cpu);

 
texture(
    int _E0,  
    int _E1,  
    int _E2) restrict(cpu);

 
texture(
    const Concurrency::extent<_Rank>& _Ext,  
    const Concurrency::accelerator_view& _Av) restrict(cpu);

 
texture(
    int _E0,  
    const Concurrency::accelerator_view& _Av) restrict(cpu);

 
texture(
    int _E0,  
    int _E1,  
    const Concurrency::accelerator_view& _Av) restrict(cpu);

 
texture(
    int _E0,  
    int _E1,  
    int _E2,  
    const Concurrency::accelerator_view& _Av) restrict(cpu);

 
template<
    typename _Input_iterator  
>  
texture(
    const Concurrency::extent<_Rank>& _Ext, _Input_iterator _Src_first, _Input_iterator _Src_last) restrict(cpu);

 
template<
    typename _Input_iterator  
>  
texture(
    int _E0, _Input_iterator _Src_first, _Input_iterator _Src_last) restrict(cpu);

 
template<
    typename _Input_iterator  
>  
texture(
    int _E0,  
    int _E1, _Input_iterator _Src_first, _Input_iterator _Src_last) restrict(cpu);

 
template<
    typename _Input_iterator  
>  
texture(
    int _E0,  
    int _E1,  
    int _E2, _Input_iterator _Src_first, _Input_iterator _Src_last) restrict(cpu);

 
template<
    typename _Input_iterator  
>  
texture(
    const Concurrency::extent<_Rank>& _Ext, _Input_iterator _Src_first, _Input_iterator _Src_last,  
    const Concurrency::accelerator_view& _Av) restrict(cpu);

 
template<
    typename _Input_iterator  
>  
texture(
    int _E0, _Input_iterator _Src_first, _Input_iterator _Src_last,  
    const Concurrency::accelerator_view& _Av) restrict(cpu);

 
template<
    typename _Input_iterator  
>  
texture(
    int _E0,  
    int _E1, _Input_iterator _Src_first, _Input_iterator _Src_last,  
    const Concurrency::accelerator_view& _Av) restrict(cpu);

 
template<
    typename _Input_iterator  
>  
texture(
    int _E0,  
    int _E1,  
    int _E2, _Input_iterator _Src_first, _Input_iterator _Src_last,  
    const Concurrency::accelerator_view& _Av) restrict(cpu))  ;  
 
texture(
    int _E0,  
    unsigned int _Bits_per_scalar_element) restrict(cpu);

 
texture(
    int _E0,  
    int _E1,  
    unsigned int _Bits_per_scalar_element) restrict(cpu);

 
texture(
    int _E0,  
    int _E1,  
    int _E2,  
    unsigned int _Bits_per_scalar_element) restrict(cpu);

 
texture(
    const Concurrency::extent<_Rank>& _Ext,  
    unsigned int _Bits_per_scalar_element,  
    const Concurrency::accelerator_view& _Av) restrict(cpu);

 
texture(
    int _E0,  
    unsigned int _Bits_per_scalar_element,  
    const Concurrency::accelerator_view& _Av)  ;  
 
texture(
    int _E0,  
    int _E1,  
    unsigned int _Bits_per_scalar_element,  
    const Concurrency::accelerator_view& _Av) restrict(cpu);

 
texture(
    int _E0,  
    int _E1,  
    int _E2,  
    unsigned int _Bits_per_scalar_element,  
    const Concurrency::accelerator_view& _Av) restrict(cpu);

 
texture(
    const Concurrency::extent<_Rank>& _Ext,  
    _In_ void* _Source,  
    unsigned int _Src_byte_size,  
    unsigned int _Bits_per_scalar_element) restrict(cpu);

 
texture(
    int _E0,  
    _In_ void* _Source,  
    unsigned int _Src_byte_size,  
    unsigned int _Bits_per_scalar_element) restrict(cpu);

 
texture(
    int _E0,  
    int _E1,  
    _In_ void* _Source,  
    unsigned int _Src_byte_size,  
    unsigned int _Bits_per_scalar_element) restrict(cpu);

 
texture(
    int _E0,  
    int _E1,  
    int _E2,  
    _In_ void* _Source,  
    unsigned int _Src_byte_size,  
    unsigned int _Bits_per_scalar_element) restrict(cpu);

 
texture(
    const Concurrency::extent<_Rank>& _Ext,  
    _In_ void* _Source,  
    unsigned int _Src_byte_size,  
    unsigned int _Bits_per_scalar_element,  
    const Concurrency::accelerator_view& _Av)  ;  
 
texture(
    int _E0,  
    _In_ void* _Source,  
    unsigned int _Src_byte_size,  
    unsigned int _Bits_per_scalar_element,  
    const Concurrency::accelerator_view& _Av) restrict(cpu);

 
texture(
    int _E0,  
    int _E1,  
    _In_ void* _Source,  
    unsigned int _Src_byte_size,  
    unsigned int _Bits_per_scalar_element,  
    const Concurrency::accelerator_view& _Av) restrict(cpu);

 
texture(
    int _E0,  
    int _E1,  
    int _E2,  
    _In_ void* _Source,  
    unsigned int _Src_byte_size,  
    unsigned int _Bits_per_scalar_element,  
    const Concurrency::accelerator_view& _Av) restrict(cpu);

 
texture(
    const texture& _Src,  
    const Concurrency::accelerator_view& _Acc_view);

 
texture(
    texture&& _Other);

 
texture(
    const Concurrency::extent<_Rank>& _Ext,   
    unsigned int _Bits_per_scalar_element,   
    const Concurrency::accelerator_view& _Av);

 
texture(
    const texture& _Src);
```  
  
### <a name="parameters"></a>Параметры  
 `_Acc_view`  
 [Accelerator_view](accelerator-view-class.md) , определяющий расположение текстуры.  
  
 `_Av`  
 [Accelerator_view](accelerator-view-class.md) , определяющий расположение текстуры.  
  
 `_Associated_av`  
 Accelerator_view, указывающее Предпочитаемая копий или из этой текстуры.  
  
 `_Bits_per_scalar_element`  
 Число бит на каждый скалярный элемент в базовый тип скалярных текстуры. Как правило поддерживаемое значение — 8, 16, 32 и 64. Если указано значение 0, число битов совпадает базового scalar_type. 64 действителен только для текстур, на основе типа double.  
  
 `_Ext`  
 Область, в каждом измерении текстуры.  
  
 `_E0`  
 Наиболее значимые компонент текстуры.  
  
 `_E1`  
 Далее к значащий компонент текстуры.  
  
 `_E2`  
 Компонент младших экстента текстуры.  
  
 `_Input_iterator`  
 Тип ввода interator.  
  
 `_Mipmap_levels`  
 Количество уровней MIP-карты в базовом текстуры. Если указано значение 0, текстуры будет иметь полный диапазон уровней MIP-карты до наименьший возможный размер для указанного экстента.  
  
 `_Rank`  
 Ранг экстента.  
  
 `_Source`  
 Указатель на буфер узла.  
  
 `_Src`  
 Для текстуры для копирования.  
  
 `_Src_byte_size`  
 Число байтов в буфере источника.  
  
 `_Src_first`  
 Итератор начало в контейнер источника.  
  
 `_Src_last`  
 Итератор конца в контейнер источника.  
  
 `_Other`  
 Другой источник данных.  
  
 `_Rank`  
 Ранг раздела.  
  
## <a name="see-also"></a>См. также  
 [Пространство имен Concurrency::Graphics](concurrency-graphics-namespace.md)

