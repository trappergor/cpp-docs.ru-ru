---
title: Класс CSimpleArrayEqualHelperFalse | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CSimpleArrayEqualHelperFalse
- ATLSIMPCOLL/ATL::CSimpleArrayEqualHelperFalse
- ATLSIMPCOLL/ATL::CSimpleArrayEqualHelperFalse::IsEqual
dev_langs:
- C++
helpviewer_keywords:
- CSimpleArrayEqualHelperFalse class
ms.assetid: 6918af6f-d23d-49eb-8482-c44272f5ffeb
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: a325da2edd4af8b8b0e6e965dc60df8c11bf8d30
ms.sourcegitcommit: 7d68f8303e021e27dc8f4d36e764ed836e93d24f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/06/2018
ms.locfileid: "37882862"
---
# <a name="csimplearrayequalhelperfalse-class"></a>Класс CSimpleArrayEqualHelperFalse
Этот класс представляет вспомогательный объект для [CSimpleArray](../../atl/reference/csimplearray-class.md) класса.  
  
## <a name="syntax"></a>Синтаксис  
  
```
template <class T>  
class CSimpleArrayEqualHelperFalse
```  
  
#### <a name="parameters"></a>Параметры  
 *T*  
 Производный класс.  
  
## <a name="members"></a>Участники  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CSimpleArrayEqualHelperFalse::IsEqual](#isequal)|(Статический) Возвращает значение false.|  
  
## <a name="remarks"></a>Примечания  
 Этот класс признаков — это дополнение к `CSimpleArray` класса. ИТ всегда возвращает false, а кроме того, будет вызывать `ATLASSERT` с аргументом значение false, если когда-либо ссылки на него. В ситуациях, где тест на равенство не определен достаточно, этот класс позволяет массив, содержащий элементы для правильной работы для большинства методов, но привести к сбою в виде четко определенных для методов, зависящие от сравнения, такие как [CSimpleArray:: Найти](../../atl/reference/csimplearray-class.md#find).  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atlsimpcoll.h  
  
##  <a name="isequal"></a>  CSimpleArrayEqualHelperFalse::IsEqual  
 Возвращает значение false.  
  
```
static bool IsEqual(const T&, const T&);
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение false.  
  
### <a name="remarks"></a>Примечания  
 Этот метод всегда возвращает значение false и будет вызывать `ATLASSERT` с аргументом значение false, если ссылка. Цель `CSimpleArrayEqualHelperFalse::IsEqual` — заставить методы использования сравнений к сбою в виде четко определенных проверок на равенство не определены должным образом.  
  
## <a name="see-also"></a>См. также  
 [Класс CSimpleArrayEqualHelper](../../atl/reference/csimplearrayequalhelper-class.md)   
 [Общие сведения о классе](../../atl/atl-class-overview.md)
