---
title: Класс writeonly_texture_view | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-amp
ms.topic: reference
f1_keywords:
- writeonly_texture_view
- AMP_GRAPHICS/writeonly_texture_view
- AMP_GRAPHICS/Concurrency::graphics::writeonly_texture_view
- AMP_GRAPHICS/Concurrency::graphics::writeonly_texture_view::set
- AMP_GRAPHICS/Concurrency::graphics::rank Constant
dev_langs:
- C++
ms.assetid: 8d117ad3-0a1c-41ae-b29c-7c95fdd4d04d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: a6b1bc5c90fd837f56dbd98eddb37f624e78080b
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2018
---
# <a name="writeonlytextureview-class"></a>Класс writeonly_texture_view
Предоставляет доступ writeonly до текстуры.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
template <
    typename value_type,  
    int _Rank  
>  
class writeonly_texture_view;  
 
template <
    typename value_type,  
    int _Rank  
>  
class writeonly_texture_view<value_type, _Rank> : public details::_Texture_base<value_type, _Rank>;  
```  
  
#### <a name="parameters"></a>Параметры  
 `value_type`  
 Тип элементов в текстуре.  
  
 `_Rank`  
 Ранг текстуры.  
  
## <a name="members"></a>Участники  
  
### <a name="public-typedefs"></a>Общедоступные определения типов  
  
|Имя|Описание|  
|----------|-----------------|  
|`scalar_type`||  
|`value_type`|Тип элементов в текстуре.|  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[Конструктор writeonly_texture_view](#ctor)|Инициализирует новый экземпляр класса `writeonly_texture_view`.|  
|[~ writeonly_texture_view деструктор](#ctor)|Уничтожает `writeonly_texture_view` объекта.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[set](#set)|Задает значение элемента по указанному индексу.|  
  
### <a name="public-operators"></a>Открытые операторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[оператор=](#operator_eq)|Копирует указанный `writeonly_texture_view` этого объекта.|  
  
### <a name="public-constants"></a>Открытые константы  
  
|name|Описание|  
|----------|-----------------|  
|[Ранг константа](#rank)|Возвращает ранг `writeonly_texture_view` объекта.|  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `_Texture_base`  
  
 `writeonly_texture_view`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** amp_graphics.h  
  
 **Пространство имен:** Concurrency::graphics  
  
##  <a name="dtor"></a> ~ writeonly_texture_view 

 Уничтожает `writeonly_texture_view` объекта.  
  
```  
~writeonly_texture_view() restrict(amp,cpu);
```  
  
##  <a name="operator_eq"></a> оператор = 

 Копирует указанный `writeonly_texture_view` этого объекта.  
  
```  
writeonly_texture_view<value_type, _Rank>& operator= (
    const writeonly_texture_view<value_type, _Rank>& _Other) restrict(amp,cpu);
```  
  
### <a name="parameters"></a>Параметры  
 `_Other`  
 `writeonly_texture_view` объект для копирования из.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ссылку на это `writeonly_texture_view` объекта.  
  
##  <a name="rank"></a> Ранг 

 Возвращает ранг `writeonly_texture_view` объекта.  
  
```  
static const int rank = _Rank;  
```  
  
##  <a name="set"></a> Набор 

 Задает значение элемента по указанному индексу.  
  
```  
void set(
    const index<_Rank>& _Index,  
    const value_type& value) const restrict(amp);
```  
  
### <a name="parameters"></a>Параметры  
 `_Index`  
 Индекс элемента.  
  
 `value`  
 Новое значение элемента.  
  
##  <a name="ctor"></a> writeonly_texture_view 

 Инициализирует новый экземпляр класса `writeonly_texture_view`.  
  
```  
writeonly_texture_view(
    texture<value_type, 
    _Rank>& _Src) restrict(amp);

 
writeonly_texture_view(
    const writeonly_texture_view<value_type,  
    _Rank>& _Src) restrict(amp,cpu);
```  
  
### <a name="parameters"></a>Параметры  
 `_Rank`  
 Ранг текстуры.  
  
 `value_type`  
 Тип элементов в текстуре.  
  
 `_Src`  
 Текстуры, которая используется для создания `writeonly_texture_view`.  
  
## <a name="see-also"></a>См. также  
 [Пространство имен Concurrency::graphics](concurrency-graphics-namespace.md)
