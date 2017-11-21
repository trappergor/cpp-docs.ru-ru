---
title: "Класс norm | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- norm
- AMP_SHORT_VECTORS/norm
- AMP_SHORT_VECTORS/Concurrency::graphics::norm Constructor
dev_langs: C++
ms.assetid: 73002f3d-c25e-4119-bcd3-4c46c9b6abf1
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 7d35bc7781b1a57fdc0b8b68c5d4f78046d19134
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="norm-class"></a>Класс norm
Представляет число нормы. Каждый элемент является типом с плавающей запятой в диапазоне [-1, 0f, 1, 0f].  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class norm;  
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[Норма конструктор](#ctor)|Перегружен. Конструктор по умолчанию. Инициализируйте 0, 0f.|  
  
### <a name="public-operators"></a>Открытые операторы  
  
|Имя|Описание|  
|----------|-----------------|  
|norm::operator-||  
|norm::operator--||  
|norm::operator число с плавающей запятой|Оператор преобразования. Преобразуйте нормы число с плавающей запятой.|  
|norm::operator * =||  
|norm::operator / =||  
|norm::operator ++||  
|norm::operator +=||  
|norm::operator =||  
|norm::operator-=||  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `norm`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** amp_short_vectors.h  
  
 **Пространство имен:** Concurrency::graphics  
  
##  <a name="ctor"></a>Норма 

 Конструктор по умолчанию. Инициализируйте 0, 0f.  
  
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
 [Пространство имен Concurrency::graphics](concurrency-graphics-namespace.md)
