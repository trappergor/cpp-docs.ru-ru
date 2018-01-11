---
title: "Класс CComApartment | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CComApartment
- ATLBASE/ATL::CComApartment
- ATLBASE/ATL::CComApartment::CComApartment
- ATLBASE/ATL::CComApartment::Apartment
- ATLBASE/ATL::CComApartment::GetLockCount
- ATLBASE/ATL::CComApartment::Lock
- ATLBASE/ATL::CComApartment::Unlock
- ATLBASE/ATL::CComApartment::m_dwThreadID
- ATLBASE/ATL::CComApartment::m_hThread
- ATLBASE/ATL::CComApartment::m_nLockCnt
dev_langs: C++
helpviewer_keywords:
- apartments in ATL EXE modules
- CComApartment class
ms.assetid: dbc177d7-7ee4-45f2-b563-d578a467ca93
caps.latest.revision: "20"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: a3fecd77e93c0c51a37d7363e6ec1472d157d6d1
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="ccomapartment-class"></a>Класс CComApartment
Этот класс обеспечивает поддержку для помещения в модуле EXE пула потоков управления.  
  
> [!IMPORTANT]
>  Этот класс и его члены не может использоваться в приложениях, выполняемых в среде выполнения Windows.  
  
## <a name="syntax"></a>Синтаксис  
  
```
class CComApartment
```  
  
## <a name="members"></a>Участники  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CComApartment::CComApartment](#ccomapartment)|Конструктор.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CComApartment::Apartment](#apartment)|Отмечает начальный адрес потока.|  
|[CComApartment::GetLockCount](#getlockcount)|Возвращает число блокировок текущего потока.|  
|[CComApartment::Lock](#lock)|Увеличивает счетчик блокировки потока.|  
|[CComApartment::Unlock](#unlock)|Уменьшает счетчик блокировки потока.|  
  
### <a name="public-data-members"></a>Открытые члены данных  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CComApartment::m_dwThreadID](#m_dwthreadid)|Содержит идентификатор потока.|  
|[CComApartment::m_hThread](#m_hthread)|Содержит дескриптор потока.|  
|[CComApartment::m_nLockCnt](#m_nlockcnt)|Содержит число блокировок текущего потока.|  
  
## <a name="remarks"></a>Примечания  
 `CComApartment`используется [CComAutoThreadModule](../../atl/reference/ccomautothreadmodule-class.md) для управления как подразделение в модуле EXE пула потоков. `CComApartment`Предоставляет методы увеличивать и уменьшать блокировки подсчета в потоке.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atlbase.h  
  
##  <a name="apartment"></a>CComApartment::Apartment  
 Отмечает начальный адрес потока.  
  
```
DWORD Apartment();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Всегда равно 0.  
  
### <a name="remarks"></a>Примечания  
 Автоматически устанавливается во время [CComAutoThreadModule::Init](../../atl/reference/ccomautothreadmodule-class.md#init).  
  
##  <a name="ccomapartment"></a>CComApartment::CComApartment  
 Конструктор.  
  
```
CComApartment();
```  
  
### <a name="remarks"></a>Примечания  
 Инициализирует `CComApartment` данные-члены [m_nLockCnt](#m_nlockcnt) и [m_hThread](#m_hthread).  
  
##  <a name="getlockcount"></a>CComApartment::GetLockCount  
 Возвращает число блокировок текущего потока.  
  
```
LONG GetLockCount();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Число блокировок в потоке.  
  
##  <a name="lock"></a>CComApartment::Lock  
 Увеличивает счетчик блокировки потока.  
  
```
LONG Lock();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение, которое может быть полезно для диагностики и тестирования.  
  
### <a name="remarks"></a>Примечания  
 Вызывается методом [CComAutoThreadModule::Lock](../../atl/reference/ccomautothreadmodule-class.md#lock).  
  
 Число блокировок в потоке используется для статистической обработки.  
  
##  <a name="m_dwthreadid"></a>CComApartment::m_dwThreadID  
 Содержит идентификатор потока.  
  
```
DWORD m_dwThreadID;
```  
  
##  <a name="m_hthread"></a>CComApartment::m_hThread  
 Содержит дескриптор потока.  
  
```
HANDLE m_hThread;
```  
  
##  <a name="m_nlockcnt"></a>CComApartment::m_nLockCnt  
 Содержит число блокировок текущего потока.  
  
```
LONG m_nLockCnt;
```  
  
##  <a name="unlock"></a>CComApartment::Unlock  
 Уменьшает счетчик блокировки потока.  
  
```
LONG Unlock();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение, которое может быть полезно для диагностики и тестирования.  
  
### <a name="remarks"></a>Примечания  
 Вызывается методом [CComAutoThreadModule::Unlock](../../atl/reference/ccomautothreadmodule-class.md#lock).  
  
 Число блокировок в потоке используется для статистической обработки.  
  
## <a name="see-also"></a>См. также  
 [Общие сведения о классе](../../atl/atl-class-overview.md)
