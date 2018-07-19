---
title: Интерфейс IThreadPoolConfig | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- IThreadPoolConfig
- ATLUTIL/ATL::IThreadPoolConfig
- ATLUTIL/ATL::GetSize
- ATLUTIL/ATL::GetTimeout
- ATLUTIL/ATL::SetSize
- ATLUTIL/ATL::SetTimeout
dev_langs:
- C++
helpviewer_keywords:
- IThreadPoolConfig interface
ms.assetid: 69e642bf-6925-46e6-9a37-cce52231b1cc
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 935175f522dd0b41851763f7b76781228c1881c0
ms.sourcegitcommit: 7d68f8303e021e27dc8f4d36e764ed836e93d24f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/06/2018
ms.locfileid: "37880158"
---
# <a name="ithreadpoolconfig-interface"></a>Интерфейс IThreadPoolConfig
Этот интерфейс предоставляет методы для настройки пула потоков.  
  
> [!IMPORTANT]
>  Этот класс и его члены не может использоваться в приложениях, выполняемых в среде выполнения Windows.  
  
## <a name="syntax"></a>Синтаксис  
  
```
__interface
    __declspec(uuid("B1F64757-6E88-4fa2-8886-7848B0D7E660")) IThreadPoolConfig : public IUnknown
```  
  
## <a name="members"></a>Участники  
  
### <a name="methods"></a>Методы  
  
|||  
|-|-|  
|[GetSize](#getsize)|Вызовите этот метод, чтобы получить число потоков в пуле.|  
|[GetTimeout](#gettimeout)|Вызовите этот метод, чтобы получить максимальное время в миллисекундах, пул потоков будет ожидать поток для завершения работы.|  
|[SetSize](#setsize)|Вызовите этот метод, чтобы задать количество потоков в пуле.|  
|[SetTimeout](#settimeout)|Вызовите этот метод, чтобы задать максимальное время в миллисекундах, пул потоков будет ожидать поток для завершения работы.|  
  
## <a name="remarks"></a>Примечания  
 Этот интерфейс реализуется [CThreadPool](../../atl/reference/cthreadpool-class.md).  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** файлов atlutil.h  
  
##  <a name="getsize"></a>  IThreadPoolConfig::GetSize  
 Вызовите этот метод, чтобы получить число потоков в пуле.  
  
```
STDMETHOD(GetSize)(int* pnNumThreads);
```  
  
### <a name="parameters"></a>Параметры  
 *pnNumThreads*  
 [out] Адрес переменной, которая, в случае успешного выполнения получает количество потоков в пуле.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает S_OK в случае успеха или ошибки HRESULT в случае сбоя.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATL_Utilities#134](../../atl/codesnippet/cpp/ithreadpoolconfig-interface_1.cpp)]  
  
##  <a name="gettimeout"></a>  IThreadPoolConfig::GetTimeout  
 Вызовите этот метод, чтобы получить максимальное время в миллисекундах, пул потоков будет ожидать поток для завершения работы.  
  
```
STDMETHOD(GetTimeout)(DWORD* pdwMaxWait);
```  
  
### <a name="parameters"></a>Параметры  
 *pdwMaxWait*  
 [out] Адрес переменной, которая, в случае успешного выполнения Получает максимальное время в миллисекундах, пул потоков будет ожидать поток для завершения работы.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает S_OK в случае успеха или ошибки HRESULT в случае сбоя.  
  
### <a name="example"></a>Пример  
 См. в разделе [IThreadPoolConfig::GetSize](#getsize).  
  
##  <a name="setsize"></a>  IThreadPoolConfig::SetSize  
 Вызовите этот метод, чтобы задать количество потоков в пуле.  
  
```
STDMETHOD(SetSize)int nNumThreads);
```  
  
### <a name="parameters"></a>Параметры  
 *nNumThreads*  
 Запрашиваемое количество потоков в пуле.  
  
 Если *nNumThreads* является отрицательным, его абсолютное значение будет умножена на число процессоров в компьютере для получения общего числа потоков.  
  
 Если *nNumThreads* равен нулю, [ATLS_DEFAULT_THREADSPERPROC](http://msdn.microsoft.com/library/e0dcf107-72a9-4122-abb4-83c63aa7d571) будет умножена на число процессоров в компьютере для получения общего числа потоков.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает S_OK в случае успеха или ошибки HRESULT в случае сбоя.  
  
### <a name="example"></a>Пример  
 См. в разделе [IThreadPoolConfig::GetSize](#getsize).  
  
##  <a name="settimeout"></a>  IThreadPoolConfig::SetTimeout  
 Вызовите этот метод, чтобы задать максимальное время в миллисекундах, пул потоков будет ожидать поток для завершения работы.  
  
```
STDMETHOD(SetTimeout)(DWORD dwMaxWait);
```  
  
### <a name="parameters"></a>Параметры  
 *dwMaxWait*  
 Запрошенное максимальное время в миллисекундах, пул потоков будет ожидать поток для завершения работы.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает S_OK в случае успеха или ошибки HRESULT в случае сбоя.  
  
### <a name="example"></a>Пример  
 См. в разделе [IThreadPoolConfig::GetSize](#getsize).  
  
## <a name="see-also"></a>См. также  
 [Классы](../../atl/reference/atl-classes.md)   
 [Класс CThreadPool](../../atl/reference/cthreadpool-class.md)
