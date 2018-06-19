---
title: Класс CComCritSecLock | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CComCritSecLock
- ATLBASE/ATL::CComCritSecLock
- ATLBASE/ATL::CComCritSecLock::CComCritSecLock
- ATLBASE/ATL::CComCritSecLock::Lock
- ATLBASE/ATL::CComCritSecLock::Unlock
dev_langs:
- C++
helpviewer_keywords:
- CComCritSecLock class
ms.assetid: 223152a1-86c3-4ef9-89a7-f455fe791b0e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 98b6eb7a8e6df16134573b55a7c9666befe4e4a1
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32358890"
---
# <a name="ccomcritseclock-class"></a>Класс CComCritSecLock
Этот класс предоставляет методы для блокировки и разблокировки объекта критической секции.  
  
## <a name="syntax"></a>Синтаксис  
  
```
template<class TLock> class CComCritSecLock
```  
  
#### <a name="parameters"></a>Параметры  
 *TLock*  
 Объект для блокировки и разблокировать.  
  
## <a name="members"></a>Участники  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CComCritSecLock::CComCritSecLock](#ctor)|Конструктор.|  
|[CComCritSecLock:: ~ CComCritSecLock](#dtor)|Деструктор|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CComCritSecLock::Lock](#lock)|Этот метод пытается заблокировать объект критической секции.|  
|[CComCritSecLock::Unlock](#unlock)|Вызовите этот метод, чтобы разблокировать объект критической секции.|  
  
## <a name="remarks"></a>Примечания  
 Этот класс используется для блокирования и разблокирования объектов более безопасным способом, чем с [класса CComCriticalSection](../../atl/reference/ccomcriticalsection-class.md) или [CComAutoCriticalSection класса](../../atl/reference/ccomautocriticalsection-class.md).  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atlbase.h  
  
##  <a name="ctor"></a>  CComCritSecLock::CComCritSecLock  
 Конструктор.  
  
```
CComCritSecLock(TLock& cs, bool bInitialLock = true);
```  
  
### <a name="parameters"></a>Параметры  
 *cs*  
 Объект критической секции.  
  
 `bInitialLock`  
 Состояние блокировки начальной: **true** означает заблокирован.  
  
### <a name="remarks"></a>Примечания  
 Инициализирует объект критической секции.  
  
##  <a name="dtor"></a>  CComCritSecLock:: ~ CComCritSecLock  
 Деструктор  
  
```
~CComCritSecLock() throw();
```  
  
### <a name="remarks"></a>Примечания  
 Разблокирует объект критической секции.  
  
##  <a name="lock"></a>  CComCritSecLock::Lock  
 Этот метод пытается заблокировать объект критической секции.  
  
```
HRESULT Lock() throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 В неудачи возвращает значение S_OK, если объект успешно заблокирована, иначе возникает ошибка HRESULT.  
  
### <a name="remarks"></a>Примечания  
 Если объект уже заблокирован, в отладочных построениях возникнет ошибка УТВЕРЖДЕНИЯ.  
  
##  <a name="unlock"></a>  CComCritSecLock::Unlock  
 Вызовите этот метод, чтобы разблокировать объект критической секции.  
  
```
void Unlock() throw();
```  
  
### <a name="remarks"></a>Примечания  
 Если объект уже разблокирован, произойдет ошибка ASSERT в отладочных построениях.  
  
## <a name="see-also"></a>См. также  
 [Класс CComCriticalSection](../../atl/reference/ccomcriticalsection-class.md)   
 [Класс CComAutoCriticalSection](../../atl/reference/ccomautocriticalsection-class.md)
