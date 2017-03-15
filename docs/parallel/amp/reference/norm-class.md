---
title: "Класс norm | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- amp_short_vectors/Concurrency::graphics::norm
dev_langs:
- C++
ms.assetid: 73002f3d-c25e-4119-bcd3-4c46c9b6abf1
caps.latest.revision: 8
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: fc190feb08d9b221cd1cc21a9c91ad567c86c848
ms.openlocfilehash: 8ff5a99136a75d17d914783496205f1dd1eb4a06
ms.lasthandoff: 02/24/2017

---
# <a name="norm-class"></a>Класс norm
Представляет число нормы. Каждый элемент представляет число с плавающей запятой в диапазоне [-1.0f, 1.0f].  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class norm;  
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[Норма конструктор](#ctor)|Перегружен. Конструктор по умолчанию. Инициализируйте значение 0, 0f.|  
  
### <a name="public-operators"></a>Открытые операторы  
  
|Имя|Описание|  
|----------|-----------------|  
|norm::operator оператор||  
|norm::operator - оператор||  
|float norm::operator оператор|Оператор преобразования. Преобразуйте нормы число с плавающей запятой.|  
|norm::operator * =-оператор||  
|norm::operator / =-оператор||  
|norm::operator оператор ++||  
|Оператор += norm::operator||  
|norm::operator =-оператор||  
|norm::operator-= оператор||  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `norm`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** amp_short_vectors.h  
  
 **Пространство имен:** Concurrency::graphics  
  
##  <a name="a-namectora-norm"></a><a name="ctor"></a>Норма 

 Конструктор по умолчанию. Инициализируйте значение 0, 0f.  
  
```  
norm(
    void) restrict(amp,
    cpu);

 
explicit norm(
    float _V) restrict(amp,
    cpu);

 
explicit norm(
    unsigned int _V) restrict(amp,
    cpu);

 
explicit norm(
    int _V) restrict(amp,
    cpu);

 
explicit norm(
    double _V) restrict(amp,
    cpu);

 
norm(
    const norm& _Other) restrict(amp,
    cpu);

 
norm(
    const unorm& _Other) restrict(amp,
    cpu);
```  
  
### <a name="parameters"></a>Параметры  
 `_V`  
 Значение, используемое для инициализации.  
  
 `_Other`  
 Объект, используемый для инициализации.  
  
## <a name="see-also"></a>См. также  
 [Пространство имен Concurrency::Graphics](concurrency-graphics-namespace.md)

