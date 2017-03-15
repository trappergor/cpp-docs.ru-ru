---
title: "Класс CComSimpleThreadAllocator | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CComSimpleThreadAllocator
- ATL::CComSimpleThreadAllocator
- ATL.CComSimpleThreadAllocator
dev_langs:
- C++
helpviewer_keywords:
- threading [ATL], selecting threads
- ATL threads
- CComSimpleThreadAllocator class
- ATL threads, allocating
ms.assetid: 66b2166a-8c50-49fd-b8e4-7f293470327d
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
ms.sourcegitcommit: 604a4bf49490ad2599c857eb3afd527d67e1e25b
ms.openlocfilehash: 377e7f2fa6d8377d46e98b52e9c8f075b10956a8
ms.lasthandoff: 02/24/2017

---
# <a name="ccomsimplethreadallocator-class"></a>Класс CComSimpleThreadAllocator
Этот класс управляет Выбор потоков для класса `CComAutoThreadModule`.  
  
## <a name="syntax"></a>Синтаксис  
  
```
class CComSimpleThreadAllocator
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CComSimpleThreadAllocator::GetThread](#getthread)|Выбирает поток.|  
  
## <a name="remarks"></a>Примечания  
 `CComSimpleThreadAllocator`Управляет Выбор потоков для [CComAutoThreadModule](../../atl/reference/ccomautothreadmodule-class.md). `CComSimpleThreadAllocator::GetThread`просто перебирает каждый поток и возвращает является следующим в последовательности.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atlbase.h  
  
##  <a name="a-namegetthreada--ccomsimplethreadallocatorgetthread"></a><a name="getthread"></a>CComSimpleThreadAllocator::GetThread  
 Выбирает поток, указав следующий поток в последовательности.  
  
```
int GetThread(CComApartment* /* pApt */, int nThreads);
```  
  
### <a name="parameters"></a>Параметры  
 `pApt`  
 В реализации библиотеки ATL по умолчанию не используется.  
  
 `nThreads`  
 Максимальное число потоков в модуле exe-файла.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Целое число от нуля и ( `nThreads` – 1). Определяет один из потоков в модуле exe-файла.  
  
### <a name="remarks"></a>Примечания  
 Можно переопределить `GetThread` для предоставления другой метод выделения или использовать `pApt` параметр.  
  
 `GetThread`вызывается методом [CComAutoThreadModule::CreateInstance](../../atl/reference/ccomautothreadmodule-class.md#createinstance).  
  
## <a name="see-also"></a>См. также  
 [Класс CComApartment](../../atl/reference/ccomapartment-class.md)   
 [Общие сведения о классе](../../atl/atl-class-overview.md)

