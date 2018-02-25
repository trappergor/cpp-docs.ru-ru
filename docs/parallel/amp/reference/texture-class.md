---
title: "Класс Texture | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- texture
- AMP_GRAPHICS/texture
- AMP_GRAPHICS/concurrency::graphics::texture::texture
- AMP_GRAPHICS/concurrency::graphics::texture::copy_to
- AMP_GRAPHICS/concurrency::graphics::texture::data
- AMP_GRAPHICS/concurrency::graphics::texture::get
- AMP_GRAPHICS/concurrency::graphics::texture::get_associated_accelerator_view
- AMP_GRAPHICS/concurrency::graphics::texture::get_depth_pitch
- AMP_GRAPHICS/concurrency::graphics::texture::get_row_pitch
- AMP_GRAPHICS/concurrency::graphics::texture::set
- AMP_GRAPHICS/concurrency::graphics::texture::rank
- AMP_GRAPHICS/concurrency::graphics::texture::associated_accelerator_view
- AMP_GRAPHICS/concurrency::graphics::texture::depth_pitch
- AMP_GRAPHICS/concurrency::graphics::texture::row_pitch
dev_langs:
- C++
ms.assetid: 16e85d4d-e80a-474a-995d-8bf63fbdf34c
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 822797fb04104b28cf72f8d8ea4291a5ad283d20
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/23/2018
---
# <a name="texture-class"></a>Класс texture
Текстура — на статистических данных `accelerator_view` в домене экстента. Представляет коллекцию переменных, по одной для каждого элемента в домене экстента. Каждая переменная содержит значение, соответствующее тип-примитив C++ ( `unsigned int`, `int`, `float`, `double`), скалярный тип ( `norm`, или `unorm`), или тип короткого вектора.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
template <typename value_type,  int _Rank>  
class texture;  
```  
  
#### <a name="parameters"></a>Параметры  
 `value_type`  
 Тип элементов в текстуре.  
  
 `_Rank`  
 Ранг текстуры.  
  
## <a name="members"></a>Участники  
  
### <a name="public-typedefs"></a>Общедоступные определения типов  
  
|Имя|Описание:|  
|----------|-----------------|  
|`scalar_type`|Скалярные типы.|  
|`value_type`|Типы значений.|  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[Конструктор текстуры](#ctor)|Инициализирует новый экземпляр класса `texture`.|  
|[~ texture деструктор](#ctor)|Уничтожает `texture` объекта.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[copy_to](#copy_to)|Копирует `texture` объект в место назначения, выполняя глубокой копией.|  
|[data](#data)|Возвращает необработанные данные текстуры, этот указатель ЦП.|  
|[get](#get)|Возвращает значение элемента по указанному индексу.|  
|[get_associated_accelerator_view](#get_associated_accelerator_view)|Возвращает [accelerator_view](accelerator-view-class.md) именно предпочитаемую целевую этот текстуры для копирования.|  
|[get_depth_pitch](#get_depth_pitch)|Возвращает число байтов между каждый срез глубины в трехмерной промежуточных текстур на ЦП.|  
|[get_row_pitch](#get_row_pitch)|Возвращает количество байтов всех строк в 2D или 3D промежуточных текстур на ЦП.|  
|[set](#set)|Задает значение элемента по указанному индексу.|  
  
### <a name="public-operators"></a>Открытые операторы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[operator()](#operator_call)|Возвращает значение элемента, указанный параметрами.|  
|[operator[]](#operator_at)|Возвращает элемент, расположенный по указанному индексу.|  
|[оператор=](#operator_eq)|Копирует указанный [текстуры](texture-class.md) этого объекта.|  
  
### <a name="public-constants"></a>Открытые константы  
  
|name|Описание:|  
|----------|-----------------|  
|[Ранг константа](#rank)|Возвращает ранг `texture` объекта.|  
  
### <a name="public-data-members"></a>Открытые члены данных  
  
|Имя|Описание:|  
|----------|-----------------|  
|[associated_accelerator_view](#associated_accelerator_view)|Возвращает [accelerator_view](accelerator-view-class.md) именно предпочитаемую целевую этот текстуры для копирования.|  
|[depth_pitch](#depth_pitch)|Возвращает число байтов между каждый срез глубины 3D промежуточной текстуры на ЦП.|  
|[row_pitch](#row_pitch)|Возвращает количество байтов всех строк в 2D или 3D промежуточных текстур на ЦП.|  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `_Texture_base`  
  
 `texture`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** amp_graphics.h  
  
 **Namespace:** Concurrency::graphics  
  
##  <a name="dtor"></a> ~ текстуры 

 Уничтожает `texture` объекта.  
  
```  
~texture() restrict(cpu);
```  
  
##  <a name="associated_accelerator_view"></a> associated_accelerator_view 

 Возвращает [accelerator_view](accelerator-view-class.md) именно предпочитаемую целевую этот текстуры для копирования.  
  
```  
__declspec(property(get= get_associated_accelerator_view)) Concurrency::accelerator_view associated_accelerator_view;  
```  
  
##  <a name="copy_to"></a> copy_to 

 Копирует `texture` объект в место назначения, выполняя глубокой копией.  
  
```  
void copy_to(texture& _Dest) const; 
void copy_to(writeonly_texture_view<value_type, _Rank>& _Dest) const; 
```  
  
### <a name="parameters"></a>Параметры  
 `_Dest`  
 Объект для копирования.  
  
 `_Rank`  
 Ранг текстуры.  
  
 `value_type`  
 Тип элементов в текстуре.  
  
##  <a name="data"></a> Данные 

 Возвращает необработанные данные текстуры, этот указатель ЦП.  
  
```  
void* data() restrict(cpu);

 
const void* data() const restrict(cpu);
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на необработанные данные текстуры.  
  
##  <a name="depth_pitch"></a> depth_pitch 

 Возвращает число байтов между каждый срез глубины 3D промежуточной текстуры на ЦП.  
  
```  
__declspec(property(get= get_depth_pitch)) unsigned int depth_pitch;  
```  
  
##  <a name="get"></a> Получить 

 Возвращает значение элемента по указанному индексу.  
  
```  
const value_type get(const index<_Rank>& _Index) const restrict(amp);
```  
  
### <a name="parameters"></a>Параметры  
 `_Index`  
 Индекс элемента.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение элемента по указанному индексу.  
  
##  <a name="get_associated_accelerator_view"></a> get_associated_accelerator_view 

 Возвращает accelerator_view, которая является целью предпочтительный для этого текстуры для копирования.  
  
```  
Concurrency::accelerator_view get_associated_accelerator_view() const restrict(cpu);
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 [Accelerator_view](accelerator-view-class.md) именно предпочитаемую целевую этот текстуры для копирования.  
  
##  <a name="get_depth_pitch"></a> get_depth_pitch 

 Возвращает число байтов между каждый срез глубины в трехмерной промежуточных текстур на ЦП.  
  
```  
unsigned int get_depth_pitch() const restrict(cpu);
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Число байтов между каждый срез глубины в трехмерной промежуточных текстур на ЦП.  
  
##  <a name="get_row_pitch"></a> get_row_pitch 

 Возвращает число байтов, между каждой строки в двумерные промежуточных текстур или каждой строки среза глубину объемного промежуточных текстур.  
  
```  
unsigned int get_row_pitch() const restrict(cpu);
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Число байтов между каждой строки в двумерные промежуточных текстур или каждой строки среза глубину объемного промежуточных текстур.  
  
##  <a name="operator_call"></a> Operator() 

 Возвращает значение элемента, указанный параметрами.  
  
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
 Старший значащий компонент индекса.  
  
 `_I1`  
 Далее к старший значащий компонент индекса.  
  
 `_I2`  
 Компонент наименьшего индекса.  
  
 `_Rank`  
 Ранг индекса.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение элемента, указанный параметрами.  
  
##  <a name="operator_at"></a> оператор] 

 Возвращает элемент, расположенный по указанному индексу.  
  
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
 Элемент, расположенный по указанному индексу.  
  
##  <a name="operator_eq"></a> оператор = 

 Копирует указанный [текстуры](texture-class.md) этого объекта.  
  
```  
texture& operator= (
    const texture& _Other);

 
texture& operator= (
    texture<value_type, _Rank>&& _Other);
```  
  
### <a name="parameters"></a>Параметры  
 `_Other`  
 `texture` Объект для копирования из.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ссылку на это `texture` объекта.  
  
##  <a name="rank"></a> Ранг 

 Возвращает ранг `texture` объекта.  
  
```  
static const int rank = _Rank;  
```  
  
##  <a name="row_pitch"></a> row_pitch 

 Возвращает количество байтов всех строк в 2D или 3D промежуточных текстур на ЦП.  
  
```  
__declspec(property(get= get_row_pitch)) unsigned int row_pitch;  
```  
  
##  <a name="set"></a> Набор 

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
  
##  <a name="ctor"></a> текстуры 

 Инициализирует новый экземпляр класса `texture`.  
  
```  
texture(const Concurrency::extent<_Rank>& _Ext) restrict(cpu);
 
texture(int _E0) restrict(cpu);
 
texture(int _E0, int _E1) restrict(cpu);
 
texture(int _E0, int _E1, int _E2) restrict(cpu);
 
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


template<typename _Input_iterator>  
texture(
    const Concurrency::extent<_Rank>& _Ext, 
    _Input_iterator _Src_first, 
    _Input_iterator _Src_last) restrict(cpu);

 
template<typename _Input_iterator>  
texture(
    int _E0, _Input_iterator _Src_first, _Input_iterator _Src_last) restrict(cpu);

 
template<typename _Input_iterator>  
texture(
    int _E0,  
    int _E1, 
    _Input_iterator _Src_first, 
    _Input_iterator _Src_last) restrict(cpu);

 
template<typename _Input_iterator>  
texture(
    int _E0,  
    int _E1,  
    int _E2, 
    _Input_iterator _Src_first, 
    _Input_iterator _Src_last) restrict(cpu);

 
template<typename _Input_iterator>  
texture(
    const Concurrency::extent<_Rank>& _Ext, 
    _Input_iterator _Src_first, 
    _Input_iterator _Src_last,  
    const Concurrency::accelerator_view& _Av) restrict(cpu);

 
template<typename _Input_iterator>  
texture(
    int _E0, 
    _Input_iterator _Src_first, 
    _Input_iterator _Src_last,  
    const Concurrency::accelerator_view& _Av) restrict(cpu);

 
template<typename _Input_iterator>  
texture(
    int _E0,  
    int _E1, 
    _Input_iterator _Src_first, 
    _Input_iterator _Src_last,  
    const Concurrency::accelerator_view& _Av) restrict(cpu);

 
template<typename _Input_iterator>  
texture(
    int _E0,  
    int _E1,  
    int _E2, 
    _Input_iterator _Src_first, 
    _Input_iterator _Src_last,  
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
 [Accelerator_view](accelerator-view-class.md) , задающий расположение, текстуры.  
  
 `_Av`  
 [Accelerator_view](accelerator-view-class.md) , задающий расположение, текстуры.  
  
 `_Associated_av`  
 Accelerator_view, задает предпочитаемую целевую копий или из этого текстуры.  
  
 `_Bits_per_scalar_element`  
 Число битов на каждый скалярный элемент в базовом типе скалярные текстуры. В общем случае поддерживаемые значения, 8, 16, 32 и 64. Если указано значение 0, число битов совпадает базового scalar_type. 64 допустим только для текстур, на основе типа double.  
  
 `_Ext`  
 Степень, в каждом измерении текстуры.  
  
 `_E0`  
 Наиболее значимые компонент текстуры.  
  
 `_E1`  
 Далее к старший значащий компонент текстуры.  
  
 `_E2`  
 Наименее значащие компонент экстента текстуры.  
  
 `_Input_iterator`  
 Тип входного interator.  
  
 `_Mipmap_levels`  
 Количество уровней MIP-карты в базовой текстуры. Если указано значение 0, текстуры будет иметь полный диапазон уровней MIP-карты до наименьший возможный размер для указанную область.  
  
 `_Rank`  
 Ранг экстента.  
  
 `_Source`  
 Указатель на буфер узла.  
  
 `_Src`  
 Для текстуры для копирования.  
  
 `_Src_byte_size`  
 Число байтов в исходном буфере.  
  
 `_Src_first`  
 Итератор с начала в контейнер источника.  
  
 `_Src_last`  
 Итератор конца в контейнер источника.  
  
 `_Other`  
 Другой источник данных.  
  
 `_Rank`  
 Ранг раздела.  
  
## <a name="see-also"></a>См. также  
 [Пространство имен Concurrency::graphics](concurrency-graphics-namespace.md)
