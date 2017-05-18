---
title: "Класс CComAutoCriticalSection | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CComAutoCriticalSection
- ATLCORE/ATL::CComAutoCriticalSection
- ATLCORE/ATL::CComAutoCriticalSection::CComAutoCriticalSection
dev_langs:
- C++
helpviewer_keywords:
- CComAutoCriticalSection class
ms.assetid: 491a9d90-3398-4f90-88f5-fd2172a46b30
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
ms.sourcegitcommit: 050e7483670bd32f633660ba44491c8bb3fc462d
ms.openlocfilehash: 9f58a4cfd02af09a05b625a7e02b574b672adade
ms.contentlocale: ru-ru
ms.lasthandoff: 02/24/2017

---
# <a name="ccomautocriticalsection-class"></a>Класс CComAutoCriticalSection
`CComAutoCriticalSection`Предоставляет методы для получения и освобождения владельца объекта критической секции.  
  
## <a name="syntax"></a>Синтаксис  
  
```
class CComAutoCriticalSection : public CComCriticalSection
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CComAutoCriticalSection::CComAutoCriticalSection](#ccomautocriticalsection)|Конструктор.|  
|[CComAutoCriticalSection:: ~ CComAutoCriticalSection](#dtor)|Деструктор|  
  
## <a name="remarks"></a>Примечания  
 `CComAutoCriticalSection`похож на класс [CComCriticalSection](../../atl/reference/ccomcriticalsection-class.md), за исключением `CComAutoCriticalSection` автоматически инициализирует объект критической секции в конструкторе.  
  
 Как правило, используется `CComAutoCriticalSection` через `typedef` имя [AutoCriticalSection](ccommultithreadmodel-class.md#autocriticalsection). Это имя ссылается на `CComAutoCriticalSection` при [CComMultiThreadModel](../../atl/reference/ccommultithreadmodel-class.md) уже используется.  

  
 `Init` И `Term` методы из [CComCriticalSection](../../atl/reference/ccomcriticalsection-class.md) недоступны при использовании этого класса.  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CComCriticalSection](../../atl/reference/ccomcriticalsection-class.md)  
  
 `CComAutoCriticalSection`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** файле atlcore.h  
  
##  <a name="ccomautocriticalsection"></a>CComAutoCriticalSection::CComAutoCriticalSection  
 Конструктор.  
  
```
CComAutoCriticalSection();
```  
  
### <a name="remarks"></a>Примечания  
 Вызывает функцию Win32 [InitializeCriticalSection](http://msdn.microsoft.com/library/windows/desktop/ms683472), который инициализирует объект критической секции.  
  
##  <a name="dtor"></a>CComAutoCriticalSection:: ~ CComAutoCriticalSection  
 Деструктор  
  
```
~CComAutoCriticalSection() throw();
```  
  
### <a name="remarks"></a>Примечания  
 Вызывает деструктор [DeleteCriticalSection](http://msdn.microsoft.com/library/windows/desktop/ms682552), который освобождает все системные ресурсы, используемые объект критической секции.  
  
## <a name="see-also"></a>См. также  
 [Класс CComFakeCriticalSection](../../atl/reference/ccomfakecriticalsection-class.md)   
 [Общие сведения о классе](../../atl/atl-class-overview.md)   
 [Класс CComCriticalSection](../../atl/reference/ccomcriticalsection-class.md)

