---
title: Класс float_2 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-amp
ms.topic: reference
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 82197c785c8b27e2d4f2607cd677141b219c90ca
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2018
ms.locfileid: "33686650"
---
# <a name="float2-class"></a>Класс float_2
Представляет короткого вектора из двух значений с плавающей запятой.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class float_2;  
```  
  
## <a name="members"></a>Участники  
  
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
|float_2::get_x||  
|float_2::get_xy||  
|float_2::get_y||  
|float_2::get_yx||  
|float_2::ref_g||  
|float_2::ref_r||  
|float_2::ref_x||  
|float_2::ref_y||  
|float_2::set_x||  
|float_2::set_xy||  
|float_2::set_y||  
|float_2::set_yx||  
  
### <a name="public-operators"></a>Открытые операторы  
  
|Имя|Описание|  
|----------|-----------------|  
|float_2::operator-||  
|float_2::operator--||  
|float_2::operator * =||  
|float_2::operator / =||  
|float_2::operator ++||  
|float_2::operator +=||  
|float_2::operator =||  
|float_2::operator-=||  
  
### <a name="public-constants"></a>Открытые константы  
  
|name|Описание|  
|----------|-----------------|  
|[Размер константы](#float_2__size)||  
  
### <a name="public-data-members"></a>Открытые члены данных  
  
|Имя|Описание|  
|----------|-----------------|  
|float_2::g||  
|float_2::GR||  
|float_2::r||  
|float_2::rg||  
|float_2::x||  
|float_2::XY||  
|float_2::y||  
|float_2::YX||  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `float_2`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** amp_short_vectors.h  
  
 **Пространство имен:** Concurrency::graphics  
  
##  <a name="ctor"></a> float_2 

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
 Значение для инициализации элемента 1.  
  
 `_V`  
 Значение для инициализации.  
  
 `_Other`  
 Объект, используемый для инициализации.  
  
##  <a name="float_2__size"></a> Размер 

```  
static const int size = 2;  
```  
  
## <a name="see-also"></a>См. также  
 [Пространство имен Concurrency::graphics](concurrency-graphics-namespace.md)
