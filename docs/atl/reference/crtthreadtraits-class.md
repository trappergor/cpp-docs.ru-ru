---
title: Класс CRTThreadTraits | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CRTThreadTraits
- ATLBASE/ATL::CRTThreadTraits
- ATLBASE/ATL::CRTThreadTraits::CreateThread
dev_langs:
- C++
helpviewer_keywords:
- CRTThreadTraits class
- threading [ATL], creation functions
- threading [ATL], CRT threads
ms.assetid: eb6e20b0-c2aa-4170-8e34-aaeeacc86343
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: f08f0d6ea57aa5a153d190b357785911e64d6f09
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32358170"
---
# <a name="crtthreadtraits-class"></a>Класс CRTThreadTraits
Этот класс предоставляет функции создания потока CRT. Этот класс используется в том случае, если поток будет использовать функции CRT.  
  
> [!IMPORTANT]
>  Этот класс и его члены не может использоваться в приложениях, выполняемых в среде выполнения Windows.  
  
## <a name="syntax"></a>Синтаксис  
  
```
class CRTThreadTraits
```  
  
## <a name="members"></a>Участники  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CRTThreadTraits::CreateThread](#createthread)|(Статический) Эта функция вызывается для создания потока, можно использовать функции CRT.|  
  
## <a name="remarks"></a>Примечания  
 Признаки потока являются классы, обеспечивающие функции создания определенного типа потока. Функции создания теми же подписи и семантику, что Windows [CreateThread](http://msdn.microsoft.com/library/windows/desktop/ms682453) функции.  
  
 Признаки потока используются следующие классы:  
  
- [CThreadPool](../../atl/reference/cthreadpool-class.md)  
  
- [CWorkerThread](../../atl/reference/cworkerthread-class.md)  
  
 Если поток не будет использоваться функции CRT, используйте [Win32ThreadTraits](../../atl/reference/win32threadtraits-class.md) вместо него.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atlbase.h  
  
##  <a name="createthread"></a>  CRTThreadTraits::CreateThread  
 Эта функция вызывается для создания потока, можно использовать функции CRT.  
  
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
  
 Эта функция вызывает [_beginthreadex](../../c-runtime-library/reference/beginthread-beginthreadex.md) при создании потока.  
  
## <a name="see-also"></a>См. также  
 [Общие сведения о классе](../../atl/atl-class-overview.md)
