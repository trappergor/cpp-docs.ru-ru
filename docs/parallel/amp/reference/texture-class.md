---
title: Класс Texture | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-amp
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 369ca34eb75b33208365d34756312e23e85afd92
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46029641"
---
# <a name="texture-class"></a>Класс texture
Текстура — это агрегат данных в `accelerator_view` в домене области памяти. Это коллекция переменных, по одной для каждого элемента в домене области памяти. Каждая переменная содержит значение, соответствующее типу-примитиву C++ ( `unsigned int`, `int`, `float`, `double`), скалярный тип ( `norm`, или `unorm`), или типу короткого вектора.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
template <typename value_type,  int _Rank>  
class texture;  
```  
  
#### <a name="parameters"></a>Параметры  
*value_type*<br/>
Тип элементов в текстуре.  
  
*_Rank*<br/>
Ранг текстуры.  
  
## <a name="members"></a>Участники  
  
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
|[copy_to](#copy_to)|Копирует `texture` в место назначения, выполнив глубокое копирование.|  
|[data](#data)|Возвращает указатель ЦП на необработанные данные этой текстуры.|  
|[get](#get)|Возвращает значение элемента по указанному индексу.|  
|[get_associated_accelerator_view](#get_associated_accelerator_view)|Возвращает [accelerator_view](accelerator-view-class.md) то есть предпочтительным целевым объектом для копирования для этой текстуры.|  
|[get_depth_pitch](#get_depth_pitch)|Возвращает число байтов между каждым срезом глубины в трехмерной промежуточной текстуре ЦП.|  
|[get_row_pitch](#get_row_pitch)|Возвращает число байтов между каждой строкой в двухмерной или трехмерной промежуточной текстуре ЦП.|  
|[set](#set)|Задает значение элемента по указанному индексу.|  
  
### <a name="public-operators"></a>Открытые операторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[Operator()](#operator_call)|Возвращает значение элемента, который указан в параметрах.|  
|[оператор]](#operator_at)|Возвращает элемент, находящийся по указанному индексу.|  
|[оператор=](#operator_eq)|Копирует указанный [текстуры](texture-class.md) в данный объект.|  
  
### <a name="public-constants"></a>Открытые константы  
  
|name|Описание|  
|----------|-----------------|  
|[Ранг константа](#rank)|Получает ранг объекта `texture` объекта.|  
  
### <a name="public-data-members"></a>Открытые члены данных  
  
|Имя|Описание|  
|----------|-----------------|  
|[associated_accelerator_view](#associated_accelerator_view)|Получает [accelerator_view](accelerator-view-class.md) то есть предпочтительным целевым объектом для копирования для этой текстуры.|  
|[depth_pitch](#depth_pitch)|Возвращает число байтов между каждым срезом глубины в трехмерной промежуточной текстуре ЦП.|  
|[row_pitch](#row_pitch)|Возвращает число байтов между каждой строкой в двухмерной или трехмерной промежуточной текстуре ЦП.|  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `_Texture_base`  
  
 `texture`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** amp_graphics.h  
  
 **Пространство имен:** Concurrency::graphics  
  
##  <a name="dtor"></a> ~ текстуры 

 Уничтожает `texture` объекта.  
  
```  
~texture() restrict(cpu);
```  
  
##  <a name="associated_accelerator_view"></a> associated_accelerator_view 

 Получает [accelerator_view](accelerator-view-class.md) то есть предпочтительным целевым объектом для копирования для этой текстуры.  
  
```  
__declspec(property(get= get_associated_accelerator_view)) Concurrency::accelerator_view associated_accelerator_view;  
```  
  
##  <a name="copy_to"></a> copy_to 

 Копирует `texture` в место назначения, выполнив глубокое копирование.  
  
```  
void copy_to(texture& _Dest) const; 
void copy_to(writeonly_texture_view<value_type, _Rank>& _Dest) const; 
```  
  
### <a name="parameters"></a>Параметры  
*_Dest*<br/>
Объект для копирования.  
  
*_Rank*<br/>
Ранг текстуры.  
  
*value_type*<br/>
Тип элементов в текстуре.  
  
##  <a name="data"></a> Данные 

 Возвращает указатель ЦП на необработанные данные этой текстуры.  
  
```  
void* data() restrict(cpu);

 
const void* data() const restrict(cpu);
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на необработанные данные текстуры.  
  
##  <a name="depth_pitch"></a> depth_pitch 

 Возвращает число байтов между каждым срезом глубины в трехмерной промежуточной текстуре ЦП.  
  
```  
__declspec(property(get= get_depth_pitch)) unsigned int depth_pitch;  
```  
  
##  <a name="get"></a> Получить 

 Возвращает значение элемента по указанному индексу.  
  
```  
const value_type get(const index<_Rank>& _Index) const restrict(amp);
```  
  
### <a name="parameters"></a>Параметры  
*_Index*<br/>
Индекс элемента.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение элемента по указанному индексу.  
  
##  <a name="get_associated_accelerator_view"></a> get_associated_accelerator_view 

 Возвращает accelerator_view, который является предпочтительным целевым объектом для копирования для этой текстуры.  
  
```  
Concurrency::accelerator_view get_associated_accelerator_view() const restrict(cpu);
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 [Accelerator_view](accelerator-view-class.md) то есть предпочтительным целевым объектом для копирования для этой текстуры.  
  
##  <a name="get_depth_pitch"></a> get_depth_pitch 

 Возвращает число байтов между каждым срезом глубины в трехмерной промежуточной текстуре ЦП.  
  
```  
unsigned int get_depth_pitch() const restrict(cpu);
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Число байтов между каждым срезом глубины в трехмерной промежуточной текстуре ЦП.  
  
##  <a name="get_row_pitch"></a> get_row_pitch 

 Возвращает число байтов между каждой строкой в 2-мерной промежуточной текстуре или между каждой строкой среза глубины в 3-мерной промежуточной текстуре.  
  
```  
unsigned int get_row_pitch() const restrict(cpu);
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Число байтов между каждой строкой в 2-мерной промежуточной текстуре или между каждой строкой среза глубины в 3-мерной промежуточной текстуре.  
  
##  <a name="operator_call"></a> Operator() 

 Возвращает значение элемента, который указан в параметрах.  
  
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
*_Index*<br/>
Индекс.  
  
*_I0*<br/>
Наиболее значимый компонент индекса.  
  
*_I1*<br/>
Далее к наиболее значимый компонент индекса.  
  
*_I2*<br/>
Наименее значимый компонент индекса.  
  
*_Rank*<br/>
Ранг индекса.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение элемента, задаваемый параметрами.  
  
##  <a name="operator_at"></a> оператор] 

 Возвращает элемент, находящийся по указанному индексу.  
  
```  
const value_type operator[] (const index<_Rank>& _Index) const restrict(amp);

 
const value_type operator[] (int _I0) const restrict(amp);
```  
  
### <a name="parameters"></a>Параметры  
*_Index*<br/>
Индекс.  
  
*_I0*<br/>
Индекс.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Элемент, находящийся по указанному индексу.  
  
##  <a name="operator_eq"></a> оператор = 

 Копирует указанный [текстуры](texture-class.md) в данный объект.  
  
```  
texture& operator= (
    const texture& _Other);

 
texture& operator= (
    texture<value_type, _Rank>&& _Other);
```  
  
### <a name="parameters"></a>Параметры  
*_Другое*<br/>
`texture` Для копирования.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ссылка на этот `texture` объекта.  
  
##  <a name="rank"></a> Ранг 

 Получает ранг объекта `texture` объекта.  
  
```  
static const int rank = _Rank;  
```  
  
##  <a name="row_pitch"></a> row_pitch 

 Возвращает число байтов между каждой строкой в двухмерной или трехмерной промежуточной текстуре ЦП.  
  
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
*_Index*<br/>
Индекс элемента.  
  
*_Rank*<br/>
Ранг индекса.  
  
*значение*<br/>
Новое значение элемента.  
  
##  <a name="ctor"></a> Текстуры 

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
*_Acc_view*<br/>
[Accelerator_view](accelerator-view-class.md) , указывающий расположение текстуры.  
  
*_Av*<br/>
[Accelerator_view](accelerator-view-class.md) , указывающий расположение текстуры.  
  
*_Associated_av*<br/>
Объект accelerator_view, который указывает предпочтительную цель для копий или из этой текстуры.  
  
*_Bits_per_scalar_element*<br/>
Количество битов на каждый скалярный элемент в базовом скалярном типе текстуры. Как правило поддерживаемые значения — 8, 16, 32 и 64. Если указано значение 0, количество битов, которое совпадает со значением базовым scalar_type. 64 допустимо только для текстур, основанных на double.  
  
*_Ext*<br/>
Область, в каждом измерении текстуры.  
  
*_E0*<br/>
Наиболее значимый компонент текстуры.  
  
*_E1*<br/>
Далее к наиболее значимый компонент текстуры.  
  
*_E2*<br/>
Наименее значимый компонент области памяти текстуры.  
  
*_Input_iterator*<br/>
Тип итератора ввода.  
  
*_Mipmap_levels*<br/>
Количество уровней MIP-карты в базовой текстуре. Если указано значение 0, текстура будет иметь полный диапазон уровней MIP-карты до наименьший возможный размер для заданного экстента.  
  
*_Rank*<br/>
Ранг области памяти.  
  
*_Source*<br/>
Указатель на буфер размещения.  
  
*_Src*<br/>
На текстуру для копирования.  
  
*_Src_byte_size*<br/>
Число байтов в буфере источника.  
  
*_Src_first*<br/>
Итератор с начала в исходном контейнере.  
  
*_Src_last*<br/>
Итератор конца в исходном контейнере.  
  
*_Другое*<br/>
Другой источник данных.  
  
*_Rank*<br/>
Ранг раздела.  
  
## <a name="see-also"></a>См. также  
 [Пространство имен Concurrency::graphics](concurrency-graphics-namespace.md)
