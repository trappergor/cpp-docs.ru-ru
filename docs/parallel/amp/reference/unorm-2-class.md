---
title: "Класс unorm_2 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- amp_short_vectors/Concurrency::graphics::unnorm_2::operator+=
- amp_short_vectors/Concurrency::graphics::unnorm_2::y
- amp_short_vectors/Concurrency::graphics::unnorm_2::set_y
- amp_short_vectors/Concurrency::graphics::unnorm_2::x
- amp_short_vectors/Concurrency::graphics::unnorm_2::get_yx
- amp_short_vectors/Concurrency::graphics::unnorm_2::operator--
- amp_short_vectors/Concurrency::graphics::unnorm_2::set_xy
- amp_short_vectors/Concurrency::graphics::unnorm_2::operator*=
- amp_short_vectors/Concurrency::graphics::unnorm_2::xy
- amp_short_vectors/Concurrency::graphics::unnorm_2::get_y
- amp_short_vectors/Concurrency::graphics::unnorm_2::operator=
- amp_short_vectors/Concurrency::graphics::unnorm_2::set_x
- amp_short_vectors/Concurrency::graphics::unnorm_2::rg
- amp_short_vectors/Concurrency::graphics::unorm_2
- amp_short_vectors/Concurrency::graphics::unnorm_2::operator-=
- amp_short_vectors/Concurrency::graphics::unnorm_2::operator/=
- amp_short_vectors/Concurrency::graphics::unnorm_2::get_xy
- amp_short_vectors/Concurrency::graphics::unnorm_2::set_yx
- amp_short_vectors/Concurrency::graphics::unnorm_2::yx
- amp_short_vectors/Concurrency::graphics::unnorm_2::gr
- amp_short_vectors/Concurrency::graphics::unnorm_2::r
- amp_short_vectors/Concurrency::graphics::unnorm_2::operator-
- amp_short_vectors/Concurrency::graphics::unnorm_2::get_x
- amp_short_vectors/Concurrency::graphics::unnorm_2::g
- amp_short_vectors/Concurrency::graphics::unnorm_2::operator++
dev_langs: C++
ms.assetid: 62e88ea7-e29f-4f62-95ce-61a1f39f5e34
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: d050e819361175f1808a440671de684499ebfa3f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="unorm2-class"></a>Класс unorm_2
Представляет короткого вектора из двух чисел без знака обычного.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class unorm_2;  
```  
  
## <a name="members"></a>Участники  
  
### <a name="public-typedefs"></a>Общедоступные определения типов  
  
|Имя|Описание|  
|----------|-----------------|  
|`value_type`||  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[Конструктор unorm_2](#ctor)|Перегружен. По умолчанию конструктор инициализирует все элементы с 0.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание:|  
|----------|-----------------|  
|unorm_2::get_X||  
|unorm_2::get_xy||  
|unorm_2::get_y||  
|unorm_2::get_yx||  
|unorm_2::ref_g||  
|unorm_2::ref_r||  
|unorm_2::ref_x||  
|unorm_2::ref_y||  
|unorm_2::set_X||  
|unorm_2::set_xy||  
|unorm_2::set_y||  
|unorm_2::set_yx||  
  
### <a name="public-operators"></a>Открытые операторы  
  
|Имя|Описание:|  
|----------|-----------------|  
|unorm_2::operator--||  
|unorm_2::operator * =||  
|unorm_2::operator / =||  
|unorm_2::operator ++||  
|unorm_2::operator +=||  
|unorm_2::operator =||  
|unorm_2::operator-=||  
  
### <a name="public-constants"></a>Открытые константы  
  
|name|Описание:|  
|----------|-----------------|  
|Константа unorm_2::size||  
  
### <a name="public-data-members"></a>Открытые члены данных  
  
|Имя|Описание:|  
|----------|-----------------|  
|unorm_2::g||  
|unorm_2::GR||  
|unorm_2::r||  
|unorm_2::RG||  
|unorm_2::x||  
|unorm_2::XY||  
|unorm_2::y||  
|unorm_2::YX||  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `unorm_2`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** amp_short_vectors.h  
  
 **Пространство имен:** Concurrency::graphics  
  
##  <a name="ctor"></a>unorm_2 

 По умолчанию конструктор инициализирует все элементы с 0.  
  
```  
unorm_2() restrict(amp,
    cpu);

 
unorm_2(
    unorm _V0,  
    unorm _V1) restrict(amp,
    cpu);

 
unorm_2(
    float _V0,  
    float _V1) restrict(amp,
    cpu);

 
unorm_2(
    unorm _V) restrict(amp,
    cpu);

 
explicit unorm_2(
    float _V) restrict(amp,
    cpu);

 
unorm_2(
    const unorm_2& _Other) restrict(amp,
    cpu);

 
explicit inline unorm_2(
    const uint_2& _Other) restrict(amp,
    cpu);

 
explicit inline unorm_2(
    const int_2& _Other) restrict(amp,
    cpu);

 
explicit inline unorm_2(
    const float_2& _Other) restrict(amp,
    cpu);

 
explicit inline unorm_2(
    const norm_2& _Other) restrict(amp,
    cpu);

 
explicit inline unorm_2(
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
  
##  <a name="unorm_2__size"></a>размер 

```  
static const int size = 2;  
```  
  
## <a name="see-also"></a>См. также  
 [Пространство имен Concurrency::graphics](concurrency-graphics-namespace.md)
