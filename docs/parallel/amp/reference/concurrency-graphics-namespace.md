---
title: "Пространство имен Concurrency::Graphics | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- amp_graphics/Concurrency::graphics
- amp_short_vectors/Concurrency::graphics
dev_langs:
- C++
ms.assetid: 4529d3b1-d7da-4ffb-82bf-080915e0f23e
caps.latest.revision: 14
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
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: fd29b427307e336d560a2caf42e4fc5228e8071f
ms.lasthandoff: 02/24/2017

---
# <a name="concurrencygraphics-namespace"></a>Пространство имен Concurrency::graphics
Графики пространство имен предоставляет типы и функции, предназначенные для программирования графики.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
namespace graphics;  
```  
  
## <a name="members"></a>Члены  
  
### <a name="namespaces"></a>Пространства имен  
  
|Имя|Описание|  
|----------|-----------------|  
|[Пространство имен Concurrency::Graphics:: Direct3D](concurrency-graphics-direct3d-namespace.md)|Предоставляет функции для взаимодействия Direct3D.|  
  
### <a name="typedefs"></a>Определения типов  
  
|Имя|Описание|  
|----------|-----------------|  
|`uint`|Тип элемента для [класс uint_2](uint-2-class.md), [класс uint_3](uint-3-class.md), и [класс uint_4](uint-4-class.md). Определенная как `typedef unsigned int uint;`.|  
  
### <a name="enumerations"></a>Перечисления  
  
|Имя|Описание|  
|----------|-----------------|  
|[Перечисление address_mode](concurrency-graphics-namespace-enums.md#address_mode).|Указывает адрес режимы, поддерживаемые для выборки текстур.|  
|[Перечисление filter_mode](concurrency-graphics-namespace-enums.md#filter_mode)|Указывает режимы фильтрации, поддерживаемые для дискретизации текстур.|  
  
### <a name="classes"></a>Классы  
  
|Имя|Описание|  
|----------|-----------------|  
|[Класс Texture](texture-class.md)|Текстура является выражением на accelerator_view в домене область данных. Это коллекция переменных, по одной для каждого элемента в домене экстента. Каждая переменная содержит значение, соответствующее типа-примитива C++ (unsigned int, int, с плавающей запятой) или норма скалярный тип или unorm (определенных в concurrency::graphics) или короткого вектора подходящих типов, определенных в concurrency::graphics.|  
|[Класс writeonly_texture_view](writeonly-texture-view-class.md)|Writeonly_texture_view предоставляет writeonly доступ к текстуры.|  
|[Класс double_2](double-2-class.md)|Представляет короткий вектор 2 `double` значения.|  
|[Класс double_3](double-3-class.md)|Представляет короткий вектор 3 `double` значения.|  
|[Класс double_4](double-4-class.md)|Представляет короткого вектора 4 `double` значения.|  
|[Класс float_2](float-2-class.md)|Представляет короткий вектор 2 `float` значения.|  
|[Класс float_3](float-3-class.md)|Представляет короткий вектор 3 `float` значения.|  
|[Класс float_4](float-4-class.md)|Представляет короткого вектора 4 `float` значения.|  
|[Класс int_2](int-2-class.md)|Представляет короткий вектор 2 `int` значения.|  
|[Класс int_3](int-3-class.md)|Представляет короткий вектор 3 `int` значения.|  
|[Класс int_4](int-4-class.md)|Представляет короткого вектора 4 `int` значения.|  
|[Класс norm_2](norm-2-class.md)|Представляет короткий вектор 2 `norm` значения.|  
|[Класс norm_3](norm-3-class.md)|Представляет короткий вектор 3 `norm` значения.|  
|[Класс norm_4](norm-4-class.md)|Представляет короткого вектора 4 `norm` значения.|  
|[Класс uint_2](uint-2-class.md)|Представляет короткий вектор 2 `uint` значения.|  
|[Класс uint_3](uint-3-class.md)|Представляет короткий вектор 3 `uint` значения.|  
|[Класс uint_4](uint-4-class.md)|Представляет короткого вектора 4 `uint` значения.|  
|[Класс unorm_2](unorm-2-class.md)|Представляет короткий вектор 2 `unorm` значения.|  
|[Класс unorm_3](unorm-3-class.md)|Представляет короткий вектор 3 `unorm` значения.|  
|[Класс unorm_4](unorm-4-class.md)|Представляет короткого вектора 4 `unorm` значения.|  
|[Класс sampler](sampler-class.md)|Представляет конфигурацию пробы, используемый для дискретизации текстур.|  
|[Структура short_vector](short-vector-structure.md)|Предоставляет базовую реализацию короткого вектора значений.|  
|[Структура short_vector_traits](short-vector-traits-structure.md)|Предоставляет для получения длины и типа короткого вектора.|  
|[Класс texture_view](texture-view-class.md)|Предоставляет доступ на чтение и запись для текстуры.|  
  
### <a name="functions"></a>Функции  
  
|Имя|Описание|  
|----------|-----------------|  
|[Copy-функция](concurrency-graphics-namespace-functions.md#copy)|Перегружен. Копирует содержимое исходной текстуры в целевой буфер узла.|  
|[Функция copy_async](concurrency-graphics-namespace-functions.md#copy_async)|Перегружен. Асинхронно копирует содержимое исходной текстуры в целевой буфер узла.|  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** amp_graphics.h  
  
 **Пространство имен** : Concurrency  
  
## <a name="see-also"></a>См. также  
 [Пространство имен Concurrency (C++ AMP)](concurrency-namespace-cpp-amp.md)

