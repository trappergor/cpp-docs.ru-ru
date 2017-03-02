---
title: "Класс float_2 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- amp_short_vectors/Concurrency::graphics::float_2::yx
- amp_short_vectors/Concurrency::graphics::float_2::operator-=
- amp_short_vectors/Concurrency::graphics::float_2::operator++
- amp_short_vectors/Concurrency::graphics::float_2::operator-
- amp_short_vectors/Concurrency::graphics::float_2::r
- amp_short_vectors/Concurrency::graphics::float_2::get_yx
- amp_short_vectors/Concurrency::graphics::float_2::get_xy
- amp_short_vectors/Concurrency::graphics::float_2::operator/=
- amp_short_vectors/Concurrency::graphics::float_2::set_yx
- amp_short_vectors/Concurrency::graphics::float_2::x
- amp_short_vectors/Concurrency::graphics::float_2::get_y
- amp_short_vectors/Concurrency::graphics::float_2::operator+=
- amp_short_vectors/Concurrency::graphics::float_2::gr
- amp_short_vectors/Concurrency::graphics::float_2::operator=
- amp_short_vectors/Concurrency::graphics::float_2::set_x
- amp_short_vectors/Concurrency::graphics::float_2::operator--
- amp_short_vectors/Concurrency::graphics::float_2::get_x
- amp_short_vectors/Concurrency::graphics::float_2::operator*=
- amp_short_vectors/Concurrency::graphics::float_2::rg
- amp_short_vectors/Concurrency::graphics::float_2::set_xy
- amp_short_vectors/Concurrency::graphics::float_2::xy
- amp_short_vectors/Concurrency::graphics::float_2
- amp_short_vectors/Concurrency::graphics::float_2::set_y
- amp_short_vectors/Concurrency::graphics::float_2::y
- amp_short_vectors/Concurrency::graphics::float_2::g
dev_langs:
- C++
ms.assetid: b3ebd48e-f8c8-4f00-a640-357f702f0cae
caps.latest.revision: 11
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
ms.openlocfilehash: 05707bd43a8f9b89a93c0da0011c46d67361fc84
ms.lasthandoff: 02/24/2017

---
# <a name="float2-class"></a>Класс float_2
Представляет вектор короткий из двух значений с плавающей запятой.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class float_2;  
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-typedefs"></a>Общедоступные определения типов  
  
|Имя|Описание|  
|----------|-----------------|  
|`value_type`||  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[Конструктор float_2](#ctor)|Перегружен. По умолчанию конструктор инициализирует все элементы с 0.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|Метод float_2::get_X||  
|Метод float_2::get_xy||  
|Метод float_2::get_y||  
|Метод float_2::get_yx||  
|Метод float_2::ref_g||  
|Метод float_2::ref_r||  
|Метод float_2::ref_x||  
|Метод float_2::ref_y||  
|Метод float_2::set_X||  
|Метод float_2::set_xy||  
|Метод float_2::set_y||  
|Метод float_2::set_yx||  
  
### <a name="public-operators"></a>Открытые операторы  
  
|Имя|Описание|  
|----------|-----------------|  
|float_2::operator оператор||  
|float_2::operator - оператор||  
|float_2::operator * =-оператор||  
|float_2::operator / =-оператор||  
|float_2::operator оператор ++||  
|Оператор += float_2::operator||  
|float_2::operator =-оператор||  
|float_2::operator-= оператор||  
  
### <a name="public-constants"></a>Открытые константы  
  
|Имя|Описание|  
|----------|-----------------|  
|[Размер константы](#float_2__size)||  
  
### <a name="public-data-members"></a>Открытые члены данных  
  
|Имя|Описание|  
|----------|-----------------|  
|Элемент данных float_2::g||  
|Элемент данных float_2::GR||  
|Элемент данных float_2::r||  
|Элемент данных float_2::RG||  
|Элемент данных float_2::x||  
|Элемент данных float_2::XY||  
|Элемент данных float_2::y||  
|Элемент данных float_2::YX||  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `float_2`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** amp_short_vectors.h  
  
 **Пространство имен:** Concurrency::graphics  
  
##  <a name="a-namectora-float2"></a><a name="ctor"></a>float_2 

 По умолчанию конструктор инициализирует все элементы с 0.  
  
```  
float_2() restrict(amp,
    cpu);

 
float_2(
    float _V0,  
    float _V1) restrict(amp,
    cpu);

 
float_2(
    float _V) restrict(amp,
    cpu);

 
float_2(
    const float_2& _Other) restrict(amp,
    cpu);

 
explicit inline float_2(
    const uint_2& _Other) restrict(amp,
    cpu);

 
explicit inline float_2(
    const int_2& _Other) restrict(amp,
    cpu);

 
explicit inline float_2(
    const unorm_2& _Other) restrict(amp,
    cpu);

 
explicit inline float_2(
    const norm_2& _Other) restrict(amp,
    cpu);

 
explicit inline float_2(
    const double_2& _Other) restrict(amp,
    cpu);
```  
  
### <a name="parameters"></a>Параметры  
 `_V0`  
 Значение для инициализации элемента 0.  
  
 `_V1`  
 Значение для инициализации элемент 1.  
  
 `_V`  
 Значение для инициализации.  
  
 `_Other`  
 Объект, используемый для инициализации.  
  
##  <a name="a-namefloat2sizea-size"></a><a name="float_2__size"></a>размер 

```  
static const int size = 2;  
```  
  
## <a name="see-also"></a>См. также  
 [Пространство имен Concurrency::Graphics](concurrency-graphics-namespace.md)

