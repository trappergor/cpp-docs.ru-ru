---
title: "Класс unorm_3 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- amp_short_vectors/Concurrency::graphics::unorm_3::set_zy
- amp_short_vectors/Concurrency::graphics::unorm_3::zxy
- amp_short_vectors/Concurrency::graphics::unorm_3::set_zyx
- amp_short_vectors/Concurrency::graphics::unorm_3::operator-=
- amp_short_vectors/Concurrency::graphics::unorm_3::xzy
- amp_short_vectors/Concurrency::graphics::unorm_3::get_xzy
- amp_short_vectors/Concurrency::graphics::unorm_3::zyx
- amp_short_vectors/Concurrency::graphics::unorm_3::rgb
- amp_short_vectors/Concurrency::graphics::unorm_3::set_xz
- amp_short_vectors/Concurrency::graphics::unorm_3::set_yxz
- amp_short_vectors/Concurrency::graphics::unorm_3::set_yx
- amp_short_vectors/Concurrency::graphics::unorm_3::br
- amp_short_vectors/Concurrency::graphics::unorm_3::get_zy
- amp_short_vectors/Concurrency::graphics::unorm_3::set_zx
- amp_short_vectors/Concurrency::graphics::unorm_3::get_xyz
- amp_short_vectors/Concurrency::graphics::unorm_3::b
- amp_short_vectors/Concurrency::graphics::unorm_3::set_xyz
- amp_short_vectors/Concurrency::graphics::unorm_3
- amp_short_vectors/Concurrency::graphics::unorm_3::set_z
- amp_short_vectors/Concurrency::graphics::unorm_3::set_xy
- amp_short_vectors/Concurrency::graphics::unorm_3::get_zyx
- amp_short_vectors/Concurrency::graphics::unorm_3::get_xy
- amp_short_vectors/Concurrency::graphics::unorm_3::x
- amp_short_vectors/Concurrency::graphics::unorm_3::get_zxy
- amp_short_vectors/Concurrency::graphics::unorm_3::z
- amp_short_vectors/Concurrency::graphics::unorm_3::get_x
- amp_short_vectors/Concurrency::graphics::unorm_3::operator=
- amp_short_vectors/Concurrency::graphics::unorm_3::yxz
- amp_short_vectors/Concurrency::graphics::unorm_3::get_yx
- amp_short_vectors/Concurrency::graphics::unorm_3::gbr
- amp_short_vectors/Concurrency::graphics::unorm_3::get_yxz
- amp_short_vectors/Concurrency::graphics::unorm_3::operator--
- amp_short_vectors/Concurrency::graphics::unorm_3::operator/=
- amp_short_vectors/Concurrency::graphics::unorm_3::brg
- amp_short_vectors/Concurrency::graphics::unorm_3::gb
- amp_short_vectors/Concurrency::graphics::unorm_3::zy
- amp_short_vectors/Concurrency::graphics::unorm_3::set_xzy
- amp_short_vectors/Concurrency::graphics::unorm_3::get_yzx
- amp_short_vectors/Concurrency::graphics::unorm_3::rb
- amp_short_vectors/Concurrency::graphics::unorm_3::gr
- amp_short_vectors/Concurrency::graphics::unorm_3::zx
- amp_short_vectors/Concurrency::graphics::unorm_3::r
- amp_short_vectors/Concurrency::graphics::unorm_3::xyz
- amp_short_vectors/Concurrency::graphics::unorm_3::grb
- amp_short_vectors/Concurrency::graphics::unorm_3::bg
- amp_short_vectors/Concurrency::graphics::unorm_3::get_y
- amp_short_vectors/Concurrency::graphics::unorm_3::g
- amp_short_vectors/Concurrency::graphics::unorm_3::yz
- amp_short_vectors/Concurrency::graphics::unorm_3::yx
- amp_short_vectors/Concurrency::graphics::unorm_3::get_xz
- amp_short_vectors/Concurrency::graphics::unorm_3::set_zxy
- amp_short_vectors/Concurrency::graphics::unorm_3::get_z
- amp_short_vectors/Concurrency::graphics::unorm_3::bgr
- amp_short_vectors/Concurrency::graphics::unorm_3::set_x
- amp_short_vectors/Concurrency::graphics::unorm_3::operator-
- amp_short_vectors/Concurrency::graphics::unorm_3::y
- amp_short_vectors/Concurrency::graphics::unorm_3::set_yzx
- amp_short_vectors/Concurrency::graphics::unorm_3::get_zx
- amp_short_vectors/Concurrency::graphics::unorm_3::yzx
- amp_short_vectors/Concurrency::graphics::unorm_3::operator++
- amp_short_vectors/Concurrency::graphics::unorm_3::set_yz
- amp_short_vectors/Concurrency::graphics::unorm_3::operator+=
- amp_short_vectors/Concurrency::graphics::unorm_3::xz
- amp_short_vectors/Concurrency::graphics::unorm_3::rg
- amp_short_vectors/Concurrency::graphics::unorm_3::xy
- amp_short_vectors/Concurrency::graphics::unorm_3::operator*=
- amp_short_vectors/Concurrency::graphics::unorm_3::set_y
- amp_short_vectors/Concurrency::graphics::unorm_3::get_yz
- amp_short_vectors/Concurrency::graphics::unorm_3::rbg
dev_langs:
- C++
ms.assetid: ea4e7a17-5256-464c-af28-8b01962564c0
caps.latest.revision: 10
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
ms.openlocfilehash: ce64e15c062f04df6c9f7671bd820ee188af0111
ms.lasthandoff: 02/24/2017

---
# <a name="unorm3-class"></a>Класс unorm_3
Представляет короткий вектор из трех чисел без знака normal.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class unorm_3;  
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-typedefs"></a>Общедоступные определения типов  
  
|Имя|Описание|  
|----------|-----------------|  
|`value_type`||  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[Конструктор unorm_3](#ctor)|Перегружен. По умолчанию конструктор инициализирует все элементы с 0.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|Метод unorm_3::get_X||  
|Метод unorm_3::get_xy||  
|Метод unorm_3::get_xyz||  
|Метод unorm_3::get_xz||  
|Метод unorm_3::get_xzy||  
|Метод unorm_3::get_y||  
|Метод unorm_3::get_yx||  
|Метод unorm_3::get_yxz||  
|Метод unorm_3::get_yz||  
|Метод unorm_3::get_yzx||  
|Метод unorm_3::get_z||  
|Метод unorm_3::get_zx||  
|Метод unorm_3::get_zxy||  
|Метод unorm_3::get_zy||  
|Метод unorm_3::get_zyx||  
|Метод Unorm_3::ref_b||  
|Метод Unorm_3::ref_g||  
|Метод Unorm_3::ref_r||  
|Метод Unorm_3::ref_x||  
|Метод Unorm_3::ref_y||  
|Метод Unorm_3::ref_z||  
|Метод unorm_3::set_X||  
|Метод unorm_3::set_xy||  
|Метод unorm_3::set_xyz||  
|Метод unorm_3::set_xz||  
|Метод unorm_3::set_xzy||  
|Метод unorm_3::set_y||  
|Метод unorm_3::set_yx||  
|Метод unorm_3::set_yxz||  
|Метод unorm_3::set_yz||  
|Метод unorm_3::set_yzx||  
|Метод unorm_3::set_z||  
|Метод unorm_3::set_zx||  
|Метод unorm_3::set_zxy||  
|Метод unorm_3::set_zy||  
|Метод unorm_3::set_zyx||  
  
### <a name="public-operators"></a>Открытые операторы  
  
|Имя|Описание|  
|----------|-----------------|  
|unorm_3::operator - оператор||  
|unorm_3::operator * =-оператор||  
|unorm_3::operator / =-оператор||  
|unorm_3::operator оператор ++||  
|Оператор += unorm_3::operator||  
|unorm_3::operator =-оператор||  
|unorm_3::operator-= оператор||  
  
### <a name="public-constants"></a>Открытые константы  
  
|Имя|Описание|  
|----------|-----------------|  
|[Размер константы](#unorm_3__size)||  
  
### <a name="public-data-members"></a>Открытые члены данных  
  
|Имя|Описание|  
|----------|-----------------|  
|Элемент данных unorm_3::b||  
|Элемент данных unorm_3::BG||  
|Элемент данных unorm_3::bgr||  
|Элемент данных unorm_3::br||  
|Элемент данных unorm_3::brg||  
|Элемент данных unorm_3::g||  
|Элемент данных unorm_3::GB||  
|Элемент данных unorm_3::GBR||  
|Элемент данных unorm_3::GR||  
|Элемент данных unorm_3::grb||  
|Элемент данных unorm_3::r||  
|Элемент данных unorm_3::RB||  
|Элемент данных unorm_3::rbg||  
|Элемент данных unorm_3::RG||  
|Элемент данных unorm_3::RGB||  
|Элемент данных unorm_3::x||  
|Элемент данных unorm_3::XY||  
|Элемент данных unorm_3::xyz||  
|Элемент данных unorm_3::xz||  
|Элемент данных unorm_3::xzy||  
|Элемент данных unorm_3::y||  
|Элемент данных unorm_3::YX||  
|Элемент данных unorm_3::yxz||  
|Элемент данных unorm_3::yz||  
|Элемент данных unorm_3::yzx||  
|Элемент данных unorm_3::z||  
|Элемент данных unorm_3::zx||  
|Элемент данных unorm_3::zxy||  
|Элемент данных unorm_3::zy||  
|Элемент данных unorm_3::zyx||  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `unorm_3`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** amp_short_vectors.h  
  
 **Пространство имен:** Concurrency::graphics  
  
##  <a name="a-namectora-unorm3"></a><a name="ctor"></a>unorm_3 

 По умолчанию конструктор инициализирует все элементы с 0.  
  
```  
unorm_3() restrict(amp,
    cpu);

 
unorm_3(
    unorm _V0,  
    unorm _V1,  
    unorm _V2) restrict(amp,
    cpu);

 
unorm_3(
    float _V0,  
    float _V1,  
    float _V2) restrict(amp,
    cpu);

 
unorm_3(
    unorm _V) restrict(amp,
    cpu);

 
explicit unorm_3(
    float _V) restrict(amp,
    cpu);

 
unorm_3(
    const unorm_3& _Other) restrict(amp,
    cpu);

 
explicit inline unorm_3(
    const uint_3& _Other) restrict(amp,
    cpu);

 
explicit inline unorm_3(
    const int_3& _Other) restrict(amp,
    cpu);

 
explicit inline unorm_3(
    const float_3& _Other) restrict(amp,
    cpu);

 
explicit inline unorm_3(
    const norm_3& _Other) restrict(amp,
    cpu);

 
explicit inline unorm_3(
    const double_3& _Other) restrict(amp,
    cpu);
```  
  
### <a name="parameters"></a>Параметры  
 `_V0`  
 Значение для инициализации элемента 0.  
  
 `_V1`  
 Значение для инициализации элемент 1.  
  
 `_V2`  
 Значение для инициализации элемента 2.  
  
 `_V`  
 Значение для инициализации.  
  
 `_Other`  
 Объект, используемый для инициализации.  
  
##  <a name="a-nameunorm3sizea-size"></a><a name="unorm_3__size"></a>размер 

```  
static const int size = 3;  
```  
  
## <a name="see-also"></a>См. также  
 [Пространство имен Concurrency::Graphics](concurrency-graphics-namespace.md)

