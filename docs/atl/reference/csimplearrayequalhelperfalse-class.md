---
title: Класс CSimpleArrayEqualHelperFalse | Документы Microsoft
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
ms.openlocfilehash: 7e22d67634f29b60bdc983c892c5fe266df61d08
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32358209"
---
# <a name="csimplearrayequalhelperfalse-class"></a>Класс CSimpleArrayEqualHelperFalse
Этот класс представляет вспомогательный класс для [CSimpleArray](../../atl/reference/csimplearray-class.md) класса.  
  
## <a name="syntax"></a>Синтаксис  
  
```
template <class T>  
class CSimpleArrayEqualHelperFalse
```  
  
#### <a name="parameters"></a>Параметры  
 `T`  
 Производный класс.  
  
## <a name="members"></a>Участники  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CSimpleArrayEqualHelperFalse::IsEqual](#isequal)|(Статический) Возвращает значение false.|  
  
## <a name="remarks"></a>Примечания  
 Этот класс характеристик является дополнением к `CSimpleArray` класса. ИТ всегда возвращает значение false, а кроме того, будет вызывать `ATLASSERT` с аргументом значение false, если когда-либо ссылки на него. В ситуациях, когда проверку равенства не определено недостаточно, этот класс позволяет массив, содержащий элементы для правильной работы для большинства методов, но в форме четко определенных для методов, зависящих от сравнения, такие как сбой [CSimpleArray:: Найти](../../atl/reference/csimplearray-class.md#find).  
  
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
 Этот метод всегда возвращает значение false и будет вызывать `ATLASSERT` с аргументом значение false, если ссылка. Назначение `CSimpleArrayEqualHelperFalse::IsEqual` можно принудительно методов с помощью сравнения возвращать ошибку четко определенным образом, если не были правильно определены проверок на равенство.  
  
## <a name="see-also"></a>См. также  
 [Класс CSimpleArrayEqualHelper](../../atl/reference/csimplearrayequalhelper-class.md)   
 [Общие сведения о классе](../../atl/atl-class-overview.md)
