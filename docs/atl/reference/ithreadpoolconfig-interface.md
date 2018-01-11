---
title: "Интерфейс IThreadPoolConfig | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- IThreadPoolConfig
- ATLUTIL/ATL::IThreadPoolConfig
- ATLUTIL/ATL::GetSize
- ATLUTIL/ATL::GetTimeout
- ATLUTIL/ATL::SetSize
- ATLUTIL/ATL::SetTimeout
dev_langs: C++
helpviewer_keywords: IThreadPoolConfig interface
ms.assetid: 69e642bf-6925-46e6-9a37-cce52231b1cc
caps.latest.revision: "24"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: d967720778305eace4eff9ad8b2163456fb4bb46
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
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
|[GetSize](#getsize)|Этот метод вызывается для получения количества потоков в пуле.|  
|[GetTimeout](#gettimeout)|Этот метод используется для получения максимальное время в миллисекундах, которое пула потоков будет ожидать завершения работы потока.|  
|[SetSize](#setsize)|Вызовите этот метод, чтобы задать количество потоков в пуле.|  
|[SetTimeout](#settimeout)|Вызовите этот метод, чтобы задать максимальное время в миллисекундах, которое пула потоков будет ожидать завершения работы потока.|  
  
## <a name="remarks"></a>Примечания  
 Этот интерфейс реализуется [CThreadPool](../../atl/reference/cthreadpool-class.md).  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** файлов atlutil.h  
  
##  <a name="getsize"></a>IThreadPoolConfig::GetSize  
 Этот метод вызывается для получения количества потоков в пуле.  
  
```
STDMETHOD(GetSize)(int* pnNumThreads);
```  
  
### <a name="parameters"></a>Параметры  
 `pnNumThreads`  
 [out] Адрес переменной, в случае успешного выполнения получает количество потоков в пуле.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение S_OK в случае успешного выполнения или ошибку HRESULT при сбое.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATL_Utilities#134](../../atl/codesnippet/cpp/ithreadpoolconfig-interface_1.cpp)]  
  
##  <a name="gettimeout"></a>IThreadPoolConfig::GetTimeout  
 Этот метод используется для получения максимальное время в миллисекундах, которое пула потоков будет ожидать завершения работы потока.  
  
```
STDMETHOD(GetTimeout)(DWORD* pdwMaxWait);
```  
  
### <a name="parameters"></a>Параметры  
 `pdwMaxWait`  
 [out] Адрес переменной, в случае успешного выполнения Получает максимальное время в миллисекундах, которое пула потоков будет ожидать завершения работы потока.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение S_OK в случае успешного выполнения или ошибку HRESULT при сбое.  
  
### <a name="example"></a>Пример  
 В разделе [IThreadPoolConfig::GetSize](#getsize).  
  
##  <a name="setsize"></a>IThreadPoolConfig::SetSize  
 Вызовите этот метод, чтобы задать количество потоков в пуле.  
  
```
STDMETHOD(SetSize)int nNumThreads);
```  
  
### <a name="parameters"></a>Параметры  
 `nNumThreads`  
 Запрошенное число потоков в пуле.  
  
 Если `nNumThreads` имеет отрицательное значение, его абсолютное значение будет умножено на количество процессоров в компьютере, чтобы получить общее количество потоков.  
  
 Если `nNumThreads` равен нулю, [ATLS_DEFAULT_THREADSPERPROC](http://msdn.microsoft.com/library/e0dcf107-72a9-4122-abb4-83c63aa7d571) будет умножено на количество процессоров в компьютере, чтобы получить общее количество потоков.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение S_OK в случае успешного выполнения или ошибку HRESULT при сбое.  
  
### <a name="example"></a>Пример  
 В разделе [IThreadPoolConfig::GetSize](#getsize).  
  
##  <a name="settimeout"></a>IThreadPoolConfig::SetTimeout  
 Вызовите этот метод, чтобы задать максимальное время в миллисекундах, которое пула потоков будет ожидать завершения работы потока.  
  
```
STDMETHOD(SetTimeout)(DWORD dwMaxWait);
```  
  
### <a name="parameters"></a>Параметры  
 `dwMaxWait`  
 Запрошенное максимальное время в миллисекундах, которое пула потоков будет ожидать завершения работы потока.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение S_OK в случае успешного выполнения или ошибку HRESULT при сбое.  
  
### <a name="example"></a>Пример  
 В разделе [IThreadPoolConfig::GetSize](#getsize).  
  
## <a name="see-also"></a>См. также  
 [Классы](../../atl/reference/atl-classes.md)   
 [Класс CThreadPool](../../atl/reference/cthreadpool-class.md)
