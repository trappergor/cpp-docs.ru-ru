---
title: "Класс CElementTraitsBase | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CElementTraitsBase
- ATL::CElementTraitsBase
- ATL.CElementTraitsBase<T>
- ATL::CElementTraitsBase<T>
- ATL.CElementTraitsBase
dev_langs:
- C++
helpviewer_keywords:
- CElementTraitsBase class
ms.assetid: 75284caf-347e-4355-a7d8-efc708dd514a
caps.latest.revision: 19
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
ms.sourcegitcommit: 5a0c6a1062330f952bb8fa52bc934f6754465513
ms.openlocfilehash: a06af7698afb24c1c2391b762673c7e3633018d4
ms.lasthandoff: 02/24/2017

---
# <a name="celementtraitsbase-class"></a>Класс CElementTraitsBase
Этот класс предоставляет копии по умолчанию и переместить методы для класса коллекции.  
  
## <a name="syntax"></a>Синтаксис  
  
```
template<typename T>  
class CElementTraitsBase
```  
  
#### <a name="parameters"></a>Параметры  
 `T`  
 Тип данных, хранящихся в коллекции.  
  
## <a name="members"></a>Члены  
  
### <a name="public-typedefs"></a>Общедоступные определения типов  
  
|Имя|Описание|  
|----------|-----------------|  
|[CElementTraitsBase::INARGTYPE](#inargtype)|Тип данных для добавления элементов в объекте класса коллекции.|  
|[CElementTraitsBase::OUTARGTYPE](#outargtype)|Тип данных, использовать для получения элементов из объекта класса коллекции.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CElementTraitsBase::CopyElements](#copyelements)|Этот метод служит для копирования элементов в объекте класса коллекции.|  
|[CElementTraitsBase::RelocateElements](#relocateelements)|Этот метод используется для перемещения элементов, хранящихся в объекте класса коллекции.|  
  
## <a name="remarks"></a>Примечания  
 Этот базовый класс определяет методы для копирование и перемещение элементов в класс коллекции. Оно используется классами [CDefaultElementTraits](../../atl/reference/cdefaultelementtraits-class.md), [CStringRefElementTraits](../../atl/reference/cstringrefelementtraits-class.md), и [CStringElementTraitsI](../../atl/reference/cstringelementtraitsi-class.md).  
  
 Дополнительные сведения см. в разделе [классы коллекций ATL](../../atl/atl-collection-classes.md).  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atlcoll.h  
  
##  <a name="a-namecopyelementsa--celementtraitsbasecopyelements"></a><a name="copyelements"></a>CElementTraitsBase::CopyElements  
 Этот метод служит для копирования элементов в объекте класса коллекции.  
  
```
static void CopyElements(
    T* pDest,
    const T* pSrc,
    size_t nElements);
```  
  
### <a name="parameters"></a>Параметры  
 `pDest`  
 Указатель на первый элемент, который получит скопированные данные.  
  
 `pSrc`  
 Указатель на первый элемент для копирования.  
  
 `nElements`  
 Число элементов для копирования.  
  
### <a name="remarks"></a>Примечания  
 Исходный и целевой элементы не должны перекрываться.  
  
##  <a name="a-nameinargtypea--celementtraitsbaseinargtype"></a><a name="inargtype"></a>CElementTraitsBase::INARGTYPE  
 Тип данных для добавления элементов в коллекцию.  
  
```
typedef const T& INARGTYPE;
```  
  
##  <a name="a-nameoutargtypea--celementtraitsbaseoutargtype"></a><a name="outargtype"></a>CElementTraitsBase::OUTARGTYPE  
 Тип данных, использовать для получения элементов из коллекции.  
  
```
typedef T& OUTARGTYPE;
```  
  
##  <a name="a-namerelocateelementsa--celementtraitsbaserelocateelements"></a><a name="relocateelements"></a>CElementTraitsBase::RelocateElements  
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
 Указатель на первый элемент для перемещения.  
  
 `nElements`  
 Число элементов для перемещения.  
  
### <a name="remarks"></a>Примечания  
 Этот метод вызывает метод [memmove](../../c-runtime-library/reference/memmove-wmemmove.md), которого достаточно для большинства типов данных. При перемещении объекты содержат указатели на свои собственные члены, этот метод необходимо переопределить.  
  
## <a name="see-also"></a>См. также  
 [Общие сведения о классе](../../atl/atl-class-overview.md)

