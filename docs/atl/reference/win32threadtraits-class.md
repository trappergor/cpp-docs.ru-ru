---
title: "Класс Win32ThreadTraits | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- Win32ThreadTraits
- ATLBASE/ATL::Win32ThreadTraits
- ATLBASE/ATL::Win32ThreadTraits::CreateThread
dev_langs:
- C++
helpviewer_keywords:
- threading [ATL], Windows threads
- threading [ATL], creation functions
- Win32ThreadTraits class
ms.assetid: 50279c38-eae1-4301-9ea6-97ccea580f3e
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: bf4fd3ffaf2fc4a035fdecf679ab507ebb557f38
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="win32threadtraits-class"></a>Класс Win32ThreadTraits
Этот класс предоставляет функции создания для потока Windows. Этот класс используется в том случае, если поток не будет использовать функции CRT.  
  
> [!IMPORTANT]
>  Этот класс и его члены не может использоваться в приложениях, выполняемых в среде выполнения Windows.  
  
## <a name="syntax"></a>Синтаксис  
  
```
class Win32ThreadTraits
```  
  
## <a name="members"></a>Участники  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[Win32ThreadTraits::CreateThread](#createthread)|(Статический) Эта функция вызывается для создания потока, не следует использовать функции CRT.|  
  
## <a name="remarks"></a>Примечания  
 Признаки потока являются классы, обеспечивающие функции создания определенного типа потока. Функции создания теми же подписи и семантику, что Windows [CreateThread](http://msdn.microsoft.com/library/windows/desktop/ms682453) функции.  
  
 Признаки потока используются следующие классы:  
  
- [CThreadPool](../../atl/reference/cthreadpool-class.md)  
  
- [CWorkerThread](../../atl/reference/cworkerthread-class.md)  
  
 Если поток будет использовать функции CRT, используйте [CRTThreadTraits](../../atl/reference/crtthreadtraits-class.md) вместо него.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atlbase.h  
  
##  <a name="createthread"></a>Win32ThreadTraits::CreateThread  
 Эта функция вызывается для создания потока, не следует использовать функции CRT.  
  
```
static HANDLE CreateThread(
    LPSECURITY_ATTRIBUTES lpsa,
    DWORD dwStackSize,
    LPTHREAD_START_ROUTINE pfnThreadProc,
    void* pvParam,
    DWORD dwCreationFlags,
    DWORD* pdwThreadId) throw();
```  
  
### <a name="parameters"></a>Параметры  
 `lpsa`  
 Атрибуты безопасности для нового потока.  
  
 `dwStackSize`  
 Размер стека нового потока.  
  
 `pfnThreadProc`  
 Процедура потока нового потока.  
  
 `pvParam`  
 Параметр, передаваемый в процедуру потока.  
  
 `dwCreationFlags`  
 Создание флаги (0 или CREATE_SUSPENDED).  
  
 `pdwThreadId`  
 [out] Адрес переменной типа DWORD, в случае успеха, получающий идентификатор потока для только что созданного потока.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает дескриптор только что созданного потока или значение NULL в случае ошибки. Вызовите [GetLastError](http://msdn.microsoft.com/library/windows/desktop/ms679360) Чтобы получить расширенные сведения об ошибке.  
  
### <a name="remarks"></a>Примечания  
 В разделе [CreateThread](http://msdn.microsoft.com/library/windows/desktop/ms682453) Дополнительные сведения о параметрах этой функции.  
  
 Эта функция вызывает `CreateThread` при создании потока.  
  
## <a name="see-also"></a>См. также  
 [Общие сведения о классе](../../atl/atl-class-overview.md)
