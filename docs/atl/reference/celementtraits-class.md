---
title: Класс CElementTraits | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CElementTraits
- atlcoll/ATL::CElementTraits
dev_langs:
- C++
helpviewer_keywords:
- CElementTraits class
ms.assetid: 496528e5-7f80-4b45-be0c-6f646feb43c5
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 45139b16ebb923acd004d995cd9466ea9e39e163
ms.sourcegitcommit: 92dbc4b9bf82fda96da80846c9cfcdba524035af
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/05/2018
ms.locfileid: "43765740"
---
# <a name="celementtraits-class"></a>Класс CElementTraits

Этот класс используется классами коллекцию для предоставления методов и функций для перемещения, копирования, сравнения и операций хэширования.

## <a name="syntax"></a>Синтаксис

```
template<typename T>  
class CElementTraits : public CDefaultElementTraits<T>
```

#### <a name="parameters"></a>Параметры

`T`  
Тип данных, хранимых в коллекции.

## <a name="remarks"></a>Примечания

Этот класс предоставляет статические функции по умолчанию и методы для перемещения, копирования, сравнение и хэширования элементов, сохраненную в объекте класса коллекции. `CElementTraits` определяется как поставщик по умолчанию из этих операций в классах коллекций [CAtlArray](../../atl/reference/catlarray-class.md), [CAtlList](../../atl/reference/catllist-class.md), [CRBMap](../../atl/reference/crbmap-class.md), [CRBMultiMap](../../atl/reference/crbmultimap-class.md), и [CRBTree](../../atl/reference/crbtree-class.md).

Реализация по умолчанию будет достаточно для простых типов данных, но если в классах коллекций используются для хранения более сложных объектов, функций и методов должны быть переопределены пользовательские реализации.

Дополнительные сведения см. в разделе [классы коллекций ATL](../../atl/atl-collection-classes.md).

## <a name="requirements"></a>Требования

**Заголовок:** atlcoll.h

## <a name="see-also"></a>См. также

[Класс CDefaultElementTraits](../../atl/reference/cdefaultelementtraits-class.md)   
[Общие сведения о классе](../../atl/atl-class-overview.md)
