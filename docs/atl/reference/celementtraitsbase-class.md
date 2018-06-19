---
title: Класс CElementTraitsBase | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CElementTraitsBase
- ATLCOLL/ATL::CElementTraitsBase
- ATLCOLL/ATL::CElementTraitsBase::INARGTYPE
- ATLCOLL/ATL::CElementTraitsBase::OUTARGTYPE
- ATLCOLL/ATL::CElementTraitsBase::CopyElements
- ATLCOLL/ATL::CElementTraitsBase::RelocateElements
dev_langs:
- C++
helpviewer_keywords:
- CElementTraitsBase class
ms.assetid: 75284caf-347e-4355-a7d8-efc708dd514a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 7a0b9f3945d9bcfa0c77855c94ec7247cb9804cb
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32359598"
---
# <a name="celementtraitsbase-class"></a>Класс CElementTraitsBase
Этот класс предоставляет копирования по умолчанию и переместить методы для класса коллекции.  
  
## <a name="syntax"></a>Синтаксис  
  
```
template<typename T>  
class CElementTraitsBase
```  
  
#### <a name="parameters"></a>Параметры  
 `T`  
 Тип данных, хранимых в коллекции.  
  
## <a name="members"></a>Участники  
  
### <a name="public-typedefs"></a>Общедоступные определения типов  
  
|Имя|Описание|  
|----------|-----------------|  
|[CElementTraitsBase::INARGTYPE](#inargtype)|Тип данных, используемый для добавления элементов к такому объекту класса коллекции.|  
|[CElementTraitsBase::OUTARGTYPE](#outargtype)|Тип данных для использования для получения элементов из объекта класса коллекции.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CElementTraitsBase::CopyElements](#copyelements)|Этот метод используется для копирования элементов в объекте класса коллекции.|  
|[CElementTraitsBase::RelocateElements](#relocateelements)|Этот метод используется для перемещения элементов, хранящихся в объекте класса коллекции.|  
  
## <a name="remarks"></a>Примечания  
 Этот базовый класс определяет методы для копирования и перемещение элементов в классе коллекции. Он сейчас используется классами [CDefaultElementTraits](../../atl/reference/cdefaultelementtraits-class.md), [CStringRefElementTraits](../../atl/reference/cstringrefelementtraits-class.md), и [CStringElementTraitsI](../../atl/reference/cstringelementtraitsi-class.md).  
  
 Дополнительные сведения см. в разделе [классы коллекций ATL](../../atl/atl-collection-classes.md).  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atlcoll.h  
  
##  <a name="copyelements"></a>  CElementTraitsBase::CopyElements  
 Этот метод используется для копирования элементов в объекте класса коллекции.  
  
```
static void CopyElements(
    T* pDest,
    const T* pSrc,
    size_t nElements);
```  
  
### <a name="parameters"></a>Параметры  
 `pDest`  
 Указатель на первый элемент, который получит копируемых данных.  
  
 `pSrc`  
 Указатель на первый элемент для копирования.  
  
 `nElements`  
 Число элементов для копирования.  
  
### <a name="remarks"></a>Примечания  
 Исходный и целевой элементы не должны перекрываться.  
  
##  <a name="inargtype"></a>  CElementTraitsBase::INARGTYPE  
 Тип данных, используемый для добавления элементов в коллекцию.  
  
```
typedef const T& INARGTYPE;
```  
  
##  <a name="outargtype"></a>  CElementTraitsBase::OUTARGTYPE  
 Тип данных для использования для получения элементов из коллекции.  
  
```
typedef T& OUTARGTYPE;
```  
  
##  <a name="relocateelements"></a>  CElementTraitsBase::RelocateElements  
 Этот метод используется для перемещения элементов, хранящихся в объекте класса коллекции.  
  
```
static void RelocateElements(
    T* pDest,
    T* pSrc,
    size_t nElements);
```  
  
### <a name="parameters"></a>Параметры  
 `pDest`  
 Указатель на первый элемент, который получит перемещенный данные.  
  
 `pSrc`  
 Указатель на первый элемент в другое место.  
  
 `nElements`  
 Количество элементов в другое место.  
  
### <a name="remarks"></a>Примечания  
 Этот метод вызывает метод [memmove](../../c-runtime-library/reference/memmove-wmemmove.md), что вполне достаточно для большинства типов данных. Перемещение объекты содержат указатели на свои собственные члены, этот метод необходимо переопределить.  
  
## <a name="see-also"></a>См. также  
 [Общие сведения о классе](../../atl/atl-class-overview.md)
