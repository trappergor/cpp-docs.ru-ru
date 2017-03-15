---
title: "Класс float_3 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- amp_short_vectors/Concurrency::graphics::float_3::get_zyx
- amp_short_vectors/Concurrency::graphics::float_3::set_y
- amp_short_vectors/Concurrency::graphics::float_3::b
- amp_short_vectors/Concurrency::graphics::float_3::operator-=
- amp_short_vectors/Concurrency::graphics::float_3::get_y
- amp_short_vectors/Concurrency::graphics::float_3::set_zy
- amp_short_vectors/Concurrency::graphics::float_3::get_yzx
- amp_short_vectors/Concurrency::graphics::float_3::xz
- amp_short_vectors/Concurrency::graphics::float_3::xyz
- amp_short_vectors/Concurrency::graphics::float_3::operator+=
- amp_short_vectors/Concurrency::graphics::float_3::brg
- amp_short_vectors/Concurrency::graphics::float_3::get_x
- amp_short_vectors/Concurrency::graphics::float_3::get_zx
- amp_short_vectors/Concurrency::graphics::float_3::y
- amp_short_vectors/Concurrency::graphics::float_3::rbg
- amp_short_vectors/Concurrency::graphics::float_3::operator-
- amp_short_vectors/Concurrency::graphics::float_3::get_yz
- amp_short_vectors/Concurrency::graphics::float_3::set_xz
- amp_short_vectors/Concurrency::graphics::float_3::operator/=
- amp_short_vectors/Concurrency::graphics::float_3::zxy
- amp_short_vectors/Concurrency::graphics::float_3::yx
- amp_short_vectors/Concurrency::graphics::float_3::g
- amp_short_vectors/Concurrency::graphics::float_3::r
- amp_short_vectors/Concurrency::graphics::float_3::zy
- amp_short_vectors/Concurrency::graphics::float_3::set_zxy
- amp_short_vectors/Concurrency::graphics::float_3::set_zyx
- amp_short_vectors/Concurrency::graphics::float_3::get_yx
- amp_short_vectors/Concurrency::graphics::float_3
- amp_short_vectors/Concurrency::graphics::float_3::get_xz
- amp_short_vectors/Concurrency::graphics::float_3::get_yxz
- amp_short_vectors/Concurrency::graphics::float_3::set_xy
- amp_short_vectors/Concurrency::graphics::float_3::get_xzy
- amp_short_vectors/Concurrency::graphics::float_3::bgr
- amp_short_vectors/Concurrency::graphics::float_3::zx
- amp_short_vectors/Concurrency::graphics::float_3::gr
- amp_short_vectors/Concurrency::graphics::float_3::set_z
- amp_short_vectors/Concurrency::graphics::float_3::get_zy
- amp_short_vectors/Concurrency::graphics::float_3::gb
- amp_short_vectors/Concurrency::graphics::float_3::set_xzy
- amp_short_vectors/Concurrency::graphics::float_3::set_zx
- amp_short_vectors/Concurrency::graphics::float_3::set_yzx
- amp_short_vectors/Concurrency::graphics::float_3::operator=
- amp_short_vectors/Concurrency::graphics::float_3::x
- amp_short_vectors/Concurrency::graphics::float_3::grb
- amp_short_vectors/Concurrency::graphics::float_3::zyx
- amp_short_vectors/Concurrency::graphics::float_3::set_yxz
- amp_short_vectors/Concurrency::graphics::float_3::get_zxy
- amp_short_vectors/Concurrency::graphics::float_3::set_yz
- amp_short_vectors/Concurrency::graphics::float_3::operator--
- amp_short_vectors/Concurrency::graphics::float_3::set_xyz
- amp_short_vectors/Concurrency::graphics::float_3::operator++
- amp_short_vectors/Concurrency::graphics::float_3::z
- amp_short_vectors/Concurrency::graphics::float_3::xy
- amp_short_vectors/Concurrency::graphics::float_3::rgb
- amp_short_vectors/Concurrency::graphics::float_3::rg
- amp_short_vectors/Concurrency::graphics::float_3::yzx
- amp_short_vectors/Concurrency::graphics::float_3::set_yx
- amp_short_vectors/Concurrency::graphics::float_3::xzy
- amp_short_vectors/Concurrency::graphics::float_3::rb
- amp_short_vectors/Concurrency::graphics::float_3::get_z
- amp_short_vectors/Concurrency::graphics::float_3::br
- amp_short_vectors/Concurrency::graphics::float_3::bg
- amp_short_vectors/Concurrency::graphics::float_3::get_xyz
- amp_short_vectors/Concurrency::graphics::float_3::set_x
- amp_short_vectors/Concurrency::graphics::float_3::yxz
- amp_short_vectors/Concurrency::graphics::float_3::yz
- amp_short_vectors/Concurrency::graphics::float_3::gbr
- amp_short_vectors/Concurrency::graphics::float_3::operator*=
- amp_short_vectors/Concurrency::graphics::float_3::get_xy
dev_langs:
- C++
helpviewer_keywords:
- amp_short_vectors/Concurrency::graphics::float_3
ms.assetid: 209df7a5-08d7-48b4-8ba5-77603642cdd8
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
ms.openlocfilehash: 9e1225c724d2c89dd2a6c4158446b6a4df195f6c
ms.lasthandoff: 02/24/2017

---
# <a name="float3-class"></a>Класс float_3
Представляет короткий вектор из трех значений с плавающей запятой.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class float_3;  
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-typedefs"></a>Общедоступные определения типов  
  
|Имя|Описание|  
|----------|-----------------|  
|`value_type`||  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[Конструктор float_3](#ctor)|Перегружен. По умолчанию конструктор инициализирует все элементы с 0.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|Метод float_3::get_X||  
|Метод float_3::get_xy||  
|Метод float_3::get_xyz||  
|Метод float_3::get_xz||  
|Метод float_3::get_xzy||  
|Метод float_3::get_y||  
|Метод float_3::get_yx||  
|Метод float_3::get_yxz||  
|Метод float_3::get_yz||  
|Метод float_3::get_yzx||  
|Метод float_3::get_z||  
|Метод float_3::get_zx||  
|Метод float_3::get_zxy||  
|Метод float_3::get_zy||  
|Метод float_3::get_zyx||  
|Метод float_3::ref_b||  
|Метод float_3::ref_g||  
|Метод float_3::ref_r||  
|Метод float_3::ref_x||  
|Метод float_3::ref_y||  
|Метод float_3::ref_z||  
|Метод float_3::set_X||  
|Метод float_3::set_xy||  
|Метод float_3::set_xyz||  
|Метод float_3::set_xz||  
|Метод float_3::set_xzy||  
|Метод float_3::set_y||  
|Метод float_3::set_yx||  
|Метод float_3::set_yxz||  
|Метод float_3::set_yz||  
|Метод float_3::set_yzx||  
|Метод float_3::set_z||  
|Метод float_3::set_zx||  
|Метод float_3::set_zxy||  
|Метод float_3::set_zy||  
|Метод float_3::set_zyx||  
  
### <a name="public-operators"></a>Открытые операторы  
  
|Имя|Описание|  
|----------|-----------------|  
|float_3::operator оператор||  
|float_3::operator - оператор||  
|float_3::operator * =-оператор||  
|float_3::operator / =-оператор||  
|float_3::operator оператор ++||  
|Оператор += float_3::operator||  
|float_3::operator =-оператор||  
|float_3::operator-= оператор||  
  
### <a name="public-constants"></a>Открытые константы  
  
|Имя|Описание|  
|----------|-----------------|  
|[Размер константы](#float_3__size)||  
  
### <a name="public-data-members"></a>Открытые члены данных  
  
|Имя|Описание|  
|----------|-----------------|  
|Элемент данных float_3::b||  
|Элемент данных float_3::BG||  
|Элемент данных float_3::bgr||  
|Элемент данных float_3::br||  
|Элемент данных float_3::brg||  
|Элемент данных float_3::g||  
|Элемент данных float_3::GB||  
|Элемент данных float_3::GBR||  
|Элемент данных float_3::GR||  
|Элемент данных float_3::grb||  
|Элемент данных float_3::r||  
|Элемент данных float_3::RB||  
|Элемент данных float_3::rbg||  
|Элемент данных float_3::RG||  
|Элемент данных float_3::RGB||  
|Элемент данных float_3::x||  
|Элемент данных float_3::XY||  
|Элемент данных float_3::xyz||  
|Элемент данных float_3::xz||  
|Элемент данных float_3::xzy||  
|Элемент данных float_3::y||  
|Элемент данных float_3::YX||  
|Элемент данных float_3::yxz||  
|Элемент данных float_3::yz||  
|Элемент данных float_3::yzx||  
|Элемент данных float_3::z||  
|Элемент данных float_3::zx||  
|Элемент данных float_3::zxy||  
|Элемент данных float_3::zy||  
|Элемент данных float_3::zyx||  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `float_3`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** amp_short_vectors.h  
  
 **Пространство имен:** Concurrency::graphics  
  
##  <a name="a-namectora-float3"></a><a name="ctor"></a>float_3 

 По умолчанию конструктор инициализирует все элементы с 0.  
  
```  
float_3() restrict(amp,
    cpu);

 
float_3(
    float _V0,  
    float _V1,  
    float _V2) restrict(amp,
    cpu);

 
float_3(
    float _V) restrict(amp,
    cpu);

 
float_3(
    const float_3& _Other) restrict(amp,
    cpu);

 
explicit inline float_3(
    const uint_3& _Other) restrict(amp,
    cpu);

 
explicit inline float_3(
    const int_3& _Other) restrict(amp,
    cpu);

 
explicit inline float_3(
    const unorm_3& _Other) restrict(amp,
    cpu);

 
explicit inline float_3(
    const norm_3& _Other) restrict(amp,
    cpu);

 
explicit inline float_3(
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
  
##  <a name="a-namefloat3sizea-size"></a><a name="float_3__size"></a>размер 

```  
static const int size = 3;  
```  
  
## <a name="see-also"></a>См. также  
 [Пространство имен Concurrency::Graphics](concurrency-graphics-namespace.md)

