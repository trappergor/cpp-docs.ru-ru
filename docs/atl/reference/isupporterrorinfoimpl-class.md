---
title: "Класс ISupportErrorInfoImpl | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- ATL::ISupportErrorInfoImpl<piid>
- ATL::ISupportErrorInfoImpl
- ISupportErrorInfoImpl
- ATL.ISupportErrorInfoImpl<piid>
- ATL.ISupportErrorInfoImpl
dev_langs:
- C++
helpviewer_keywords:
- ISupportErrorInfo ATL implementation
- ISupportErrorInfoImpl class
- error information, ATL
ms.assetid: e33a4b11-a123-41cf-bcea-7b19743902af
caps.latest.revision: 23
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
ms.openlocfilehash: 320cb27d1d22a5e4240861c934e9bcfabd731bad
ms.lasthandoff: 02/24/2017

---
# <a name="isupporterrorinfoimpl-class"></a>Класс ISupportErrorInfoImpl
Этот класс предоставляет реализацию по умолчанию [ISupportErrorInfo интерфейс](http://msdn.microsoft.com/en-us/42d33066-36b4-4a5b-aa5d-46682e560f32) и может использоваться, когда только один интерфейс выдает сообщения об ошибках для объекта.  
  
> [!IMPORTANT]
>  Этот класс и его члены не может использоваться в приложениях, выполняемых в [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)].  
  
## <a name="syntax"></a>Синтаксис  
  
```
template<const IID* piid>  
class ATL_NO_VTABLE ISupportErrorInfoImpl 
   : public ISupportErrorInfo
```  
  
#### <a name="parameters"></a>Параметры  
 `piid`  
 Указатель на идентификатор IID интерфейса, который поддерживает [IErrorInfo](http://msdn.microsoft.com/en-us/4dda6909-2d9a-4727-ae0c-b5f90dcfa447).  
  
## <a name="members"></a>Члены  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[ISupportErrorInfoImpl::InterfaceSupportsErrorInfo](#interfacesupportserrorinfo)|Указывает, определяется ли интерфейс `riid` поддерживает [IErrorInfo](http://msdn.microsoft.com/en-us/4dda6909-2d9a-4727-ae0c-b5f90dcfa447) интерфейса.|  
  
## <a name="remarks"></a>Примечания  
 [ISupportErrorInfo интерфейс](http://msdn.microsoft.com/en-us/42d33066-36b4-4a5b-aa5d-46682e560f32) гарантирует, что сведения об ошибках могут быть возвращены клиенту. Объекты, использующие **IErrorInfo** необходимо реализовать **ISupportErrorInfo**.  
  
 Класс `ISupportErrorInfoImpl` предоставляет реализацию по умолчанию **ISupportErrorInfo** и может использоваться, когда только один интерфейс выдает сообщения об ошибках для объекта. Пример:  
  
 [!code-cpp[NVC_ATL_COM&#48;](../../atl/codesnippet/cpp/isupporterrorinfoimpl-class_1.h)]  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `ISupportErrorInfo`  
  
 `ISupportErrorInfoImpl`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** файле atlcom.h  
  
##  <a name="a-nameinterfacesupportserrorinfoa--isupporterrorinfoimplinterfacesupportserrorinfo"></a><a name="interfacesupportserrorinfo"></a>ISupportErrorInfoImpl::InterfaceSupportsErrorInfo  
 Указывает, определяется ли интерфейс `riid` поддерживает [IErrorInfo](http://msdn.microsoft.com/en-us/4dda6909-2d9a-4727-ae0c-b5f90dcfa447) интерфейса.  
  
```
STDMETHOD(InterfaceSupportsErrorInfo)(REFIID riid);
```  
  
### <a name="remarks"></a>Примечания  
 В разделе [ISupportErrorInfo::InterfaceSupportsErrorInfo](http://msdn.microsoft.com/en-us/a54ef18d-ee3f-4483-ac4a-99d758f0960a) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namegetsizea--ithreadpoolconfiggetsize"></a><a name="getsize"></a>IThreadPoolConfig::GetSize  
 Этот метод вызывается для получения количества потоков в пуле.  
  
```
STDMETHOD(GetSize)(int* pnNumThreads);
```  
  
### <a name="parameters"></a>Параметры  
 `pnNumThreads`  
 [out] Адрес переменной, в случае успешного выполнения получает количество потоков в пуле.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение S_OK в случае успешного выполнения или значение HRESULT ошибки в случае сбоя.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATL_Utilities&#134;](../../atl/codesnippet/cpp/isupporterrorinfoimpl-class_2.cpp)]  
  
##  <a name="a-namegettimeouta--ithreadpoolconfiggettimeout"></a><a name="gettimeout"></a>IThreadPoolConfig::GetTimeout  
 Этот метод, чтобы получить максимальное время в миллисекундах, пул потоков будет ожидать завершения работы потока.  
  
```
STDMETHOD(GetTimeout)(DWORD* pdwMaxWait);
```  
  
### <a name="parameters"></a>Параметры  
 `pdwMaxWait`  
 [out] Адрес переменной, в случае успешного выполнения Получает максимальное время в миллисекундах, пул потоков будет ожидать завершения работы потока.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение S_OK в случае успешного выполнения или значение HRESULT ошибки в случае сбоя.  
  
### <a name="example"></a>Пример  
 В разделе [IThreadPoolConfig::GetSize](#getsize).  
  
##  <a name="a-namesetsizea--ithreadpoolconfigsetsize"></a><a name="setsize"></a>IThreadPoolConfig::SetSize  
 Вызовите этот метод, чтобы задать количество потоков в пуле.  
  
```
STDMETHOD(SetSize)int nNumThreads);
```  
  
### <a name="parameters"></a>Параметры  
 `nNumThreads`  
 Запрошенное число потоков в пуле.  
  
 Если `nNumThreads` является отрицательным, абсолютное значение будет умножено на количество процессоров в компьютере, чтобы получить общее количество потоков.  
  
 Если `nNumThreads` равен нулю, [ATLS_DEFAULT_THREADSPERPROC](http://msdn.microsoft.com/library/e0dcf107-72a9-4122-abb4-83c63aa7d571) будет умножено на количество процессоров в компьютере, чтобы получить общее количество потоков.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение S_OK в случае успешного выполнения или значение HRESULT ошибки в случае сбоя.  
  
### <a name="example"></a>Пример  
 В разделе [IThreadPoolConfig::GetSize](#getsize).  
  
##  <a name="a-namesettimeouta--ithreadpoolconfigsettimeout"></a><a name="settimeout"></a>IThreadPoolConfig::SetTimeout  
 Вызовите этот метод, чтобы задать максимальное время в миллисекундах, пул потоков будет ожидать завершения работы потока.  
  
```
STDMETHOD(SetTimeout)(DWORD dwMaxWait);
```  
  
### <a name="parameters"></a>Параметры  
 `dwMaxWait`  
 Запрошенное максимальное время в миллисекундах, пул потоков будет ожидать завершения работы потока.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение S_OK в случае успешного выполнения или значение HRESULT ошибки в случае сбоя.  
  
### <a name="example"></a>Пример  
 В разделе [IThreadPoolConfig::GetSize](#getsize).  
  
## <a name="see-also"></a>См. также  
 [Общие сведения о классе](../../atl/atl-class-overview.md)

