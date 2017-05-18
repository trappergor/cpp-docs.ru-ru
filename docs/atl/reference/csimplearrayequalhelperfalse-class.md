---
title: "Класс CSimpleArrayEqualHelperFalse | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 604a4bf49490ad2599c857eb3afd527d67e1e25b
ms.openlocfilehash: cd5ed7058194880ef1ceaebe788e3deb60d4ac8e
ms.contentlocale: ru-ru
ms.lasthandoff: 02/24/2017

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
  
## <a name="members"></a>Члены  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CSimpleArrayEqualHelperFalse::IsEqual](#isequal)|(Статический) Возвращает значение false.|  
  
## <a name="remarks"></a>Примечания  
 Этот класс характеристик является дополнением к `CSimpleArray` класса. ИТ всегда возвращает значение false, а кроме того, будет вызывать `ATLASSERT` с аргументом значение false, если когда-либо ссылки на него. В ситуациях, где проверку равенства не определен достаточно, этот класс позволяет массив, содержащий элементы, для правильной работы в большинстве методов, но не в форме четко определенные методы, зависящие от сравнения, таких как [CSimpleArray::Find](../../atl/reference/csimplearray-class.md#find).  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atlsimpcoll.h  
  
##  <a name="isequal"></a>CSimpleArrayEqualHelperFalse::IsEqual  
 Возвращает значение false.  
  
```
static bool IsEqual(const T&, const T&);
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение false.  
  
### <a name="remarks"></a>Примечания  
 Этот метод всегда возвращает значение false и будет вызывать `ATLASSERT` с аргументом значение false, если ссылка. Назначение `CSimpleArrayEqualHelperFalse::IsEqual` — заставить методы с помощью сравнения сбой в форме четко определенные тесты на равенство не заданы правильно.  
  
## <a name="see-also"></a>См. также  
 [Класс CSimpleArrayEqualHelper](../../atl/reference/csimplearrayequalhelper-class.md)   
 [Общие сведения о классе](../../atl/atl-class-overview.md)

