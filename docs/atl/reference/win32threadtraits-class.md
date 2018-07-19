---
title: Класс Win32ThreadTraits | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c61ba91fe29610f4b313cf31c65f514ef8e46f96
ms.sourcegitcommit: 7d68f8303e021e27dc8f4d36e764ed836e93d24f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/06/2018
ms.locfileid: "37883678"
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
|[Win32ThreadTraits::CreateThread](#createthread)|(Статический) Вызывайте эту функцию для создания потока, который не следует использовать функции CRT.|  
  
## <a name="remarks"></a>Примечания  
 Поток признаки являются классы, предоставляющие функции создания для определенного типа потока. Функция создания совпадает с той же сигнатуре и семантику Windows [CreateThread](http://msdn.microsoft.com/library/windows/desktop/ms682453) функции.  
  
 Поток признаки используются следующие классы:  
  
- [CThreadPool](../../atl/reference/cthreadpool-class.md)  
  
- [CWorkerThread](../../atl/reference/cworkerthread-class.md)  
  
 Если поток будет использовать функции CRT, используйте [CRTThreadTraits](../../atl/reference/crtthreadtraits-class.md) вместо этого.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atlbase.h  
  
##  <a name="createthread"></a>  Win32ThreadTraits::CreateThread  
 Вызывайте эту функцию для создания потока, который не следует использовать функции CRT.  
  
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
 *lpsa*  
 Атрибуты безопасности для нового потока.  
  
 *dwStackSize*  
 Размер стека для нового потока.  
  
 *pfnThreadProc*  
 Процедура потока нового потока.  
  
 *pvParam*  
 Параметр, передаваемый в процедуру потока.  
  
 *dwCreationFlags*  
 Создание флагов ("0" или "CREATE_SUSPENDED").  
  
 *pdwThreadId*  
 [out] Адрес переменной DWORD, который, в случае успешного выполнения получает идентификатор только что созданному потоку.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает дескриптор в только что созданному потоку или значение NULL в случае сбоя. Вызовите [GetLastError](http://msdn.microsoft.com/library/windows/desktop/ms679360) Чтобы получить расширенные сведения об ошибке.  
  
### <a name="remarks"></a>Примечания  
 См. в разделе [CreateThread](http://msdn.microsoft.com/library/windows/desktop/ms682453) для получения дополнительных сведений о параметрах для этой функции.  
  
 Эта функция вызывает `CreateThread` при создании потока.  
  
## <a name="see-also"></a>См. также  
 [Общие сведения о классе](../../atl/atl-class-overview.md)
