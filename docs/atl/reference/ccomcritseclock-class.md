---
title: "Класс CComCritSecLock | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
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
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 71b9ab8b11adc946656c2192c2f0f06555ef1254
ms.contentlocale: ru-ru
ms.lasthandoff: 02/24/2017

---
# <a name="ccomcritseclock-class"></a>Класс CComCritSecLock
Этот класс предоставляет методы для блокировки и разблокировки объекта критической секции.  
  
## <a name="syntax"></a>Синтаксис  
  
```
template<class TLock> class CComCritSecLock
```  
  
#### <a name="parameters"></a>Параметры  
 *TLock*  
 Объект для блокировки и разблокирован.  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CComCritSecLock::CComCritSecLock](#ctor)|Конструктор.|  
|[CComCritSecLock:: ~ CComCritSecLock](#dtor)|Деструктор|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CComCritSecLock::Lock](#lock)|Этот метод используется для блокировки объекта критической секции.|  
|[CComCritSecLock::Unlock](#unlock)|Этот метод вызывается для разблокировки объекта критической секции.|  
  
## <a name="remarks"></a>Примечания  
 Этот класс используется для блокирования и разблокирования объектов более безопасным способом, чем с [класса CComCriticalSection](../../atl/reference/ccomcriticalsection-class.md) или [CComAutoCriticalSection класса](../../atl/reference/ccomautocriticalsection-class.md).  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atlbase.h  
  
##  <a name="ctor"></a>CComCritSecLock::CComCritSecLock  
 Конструктор.  
  
```
CComCritSecLock(TLock& cs, bool bInitialLock = true);
```  
  
### <a name="parameters"></a>Параметры  
 *CS*  
 Объект критической секции.  
  
 `bInitialLock`  
 Состояние блокировки начальной: **true** означает заблокирован.  
  
### <a name="remarks"></a>Примечания  
 Инициализирует объект критической секции.  
  
##  <a name="dtor"></a>CComCritSecLock:: ~ CComCritSecLock  
 Деструктор  
  
```
~CComCritSecLock() throw();
```  
  
### <a name="remarks"></a>Примечания  
 Разблокирует объект критической секции.  
  
##  <a name="lock"></a>CComCritSecLock::Lock  
 Этот метод используется для блокировки объекта критической секции.  
  
```
HRESULT Lock() throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение S_OK, если объект успешно заблокирован или ошибку HRESULT при сбое.  
  
### <a name="remarks"></a>Примечания  
 Если объект уже заблокирован, ASSERT приводит к ошибке в отладочных сборках.  
  
##  <a name="unlock"></a>CComCritSecLock::Unlock  
 Этот метод вызывается для разблокировки объекта критической секции.  
  
```
void Unlock() throw();
```  
  
### <a name="remarks"></a>Примечания  
 Если объект уже разблокирован, произойдет ошибка ASSERT в отладочных сборках.  
  
## <a name="see-also"></a>См. также  
 [Класс CComCriticalSection](../../atl/reference/ccomcriticalsection-class.md)   
 [Класс CComAutoCriticalSection](../../atl/reference/ccomautocriticalsection-class.md)

