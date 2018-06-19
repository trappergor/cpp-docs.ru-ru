---
title: Класс IDataObjectImpl | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- IDataObjectImpl
- ATLCTL/ATL::IDataObjectImpl
- ATLCTL/ATL::IDataObjectImpl::DAdvise
- ATLCTL/ATL::IDataObjectImpl::DUnadvise
- ATLCTL/ATL::IDataObjectImpl::EnumDAdvise
- ATLCTL/ATL::IDataObjectImpl::EnumFormatEtc
- ATLCTL/ATL::IDataObjectImpl::FireDataChange
- ATLCTL/ATL::IDataObjectImpl::GetCanonicalFormatEtc
- ATLCTL/ATL::IDataObjectImpl::GetData
- ATLCTL/ATL::IDataObjectImpl::GetDataHere
- ATLCTL/ATL::IDataObjectImpl::QueryGetData
- ATLCTL/ATL::IDataObjectImpl::SetData
dev_langs:
- C++
helpviewer_keywords:
- data transfer [C++]
- data transfer [C++], Uniform Data Transfer
- IDataObjectImpl class
- IDataObject, ATL implementation
ms.assetid: b680f0f7-7795-40a1-a0f6-f48768201c89
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: a3ffcdd8cc8320b2534d928171fe75619062b300
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32365485"
---
# <a name="idataobjectimpl-class"></a>Класс IDataObjectImpl
Этот класс предоставляет методы для поддержки унифицированная передача данных и управления подключениями.  
  
> [!IMPORTANT]
>  Этот класс и его члены не может использоваться в приложениях, выполняемых в среде выполнения Windows.  
  
## <a name="syntax"></a>Синтаксис  
  
```
template<class T>  
class IDataObjectImpl
```  
  
#### <a name="parameters"></a>Параметры  
 `T`  
 Класс, производный от `IDataObjectImpl`.  
  
## <a name="members"></a>Участники  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[IDataObjectImpl::DAdvise](#dadvise)|Устанавливает соединение между объектом данных и приемника уведомлений. Это позволяет приемник уведомлений для получения уведомлений об изменениях в объекте.|  
|[IDataObjectImpl::DUnadvise](#dunadvise)|Завершает соединение, установленное ранее при помощи `DAdvise`.|  
|[IDataObjectImpl::EnumDAdvise](#enumdadvise)|Создает перечислитель для перебора текущих соединений для рекомендаций.|  
|[IDataObjectImpl::EnumFormatEtc](#enumformatetc)|Создает перечислитель для перебора **FORMATETC** структуры, поддерживаемые объектом данных. Возвращает реализацию ATL **E_NOTIMPL**.|  
|[IDataObjectImpl::FireDataChange](#firedatachange)|Отправляет уведомление об изменении каждый приемник уведомлений.|  
|[IDataObjectImpl::GetCanonicalFormatEtc](#getcanonicalformatetc)|Извлекает логически эквивалентных **FORMATETC** структуры на ту, которая является более сложным. Возвращает реализацию ATL **E_NOTIMPL**.|  
|[IDataObjectImpl::GetData](#getdata)|Передает данные из объекта данных клиенту. Данные, которые описываются в **FORMATETC** структуры и передается через **STGMEDIUM** структуры.|  
|[IDataObjectImpl::GetDataHere](#getdatahere)|Аналогично `GetData`, за исключением того, клиент должен выделить **STGMEDIUM** структуры. Возвращает реализацию ATL **E_NOTIMPL**.|  
|[IDataObjectImpl::QueryGetData](#querygetdata)|Определяет, поддерживает ли объект данных конкретного **FORMATETC** структуры для передачи данных. Возвращает реализацию ATL **E_NOTIMPL**.|  
|[IDataObjectImpl::SetData](#setdata)|Данные передаются от клиента объект данных. Возвращает реализацию ATL **E_NOTIMPL**.|  
  
## <a name="remarks"></a>Примечания  
 [IDataObject](http://msdn.microsoft.com/library/windows/desktop/ms688421) интерфейс предоставляет методы для поддержки унифицированная передача данных. `IDataObject` использует стандартный формат структуры [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) и [STGMEDIUM](http://msdn.microsoft.com/library/windows/desktop/ms683812) для получения и сохранения данных.  
  
 `IDataObject` также управляет соединениями с приемников для обработки уведомления об изменении данных уведомлений. Чтобы клиента для получения уведомлений об изменении данных из объекта данных, необходимо реализовать клиент [IAdviseSink](http://msdn.microsoft.com/library/windows/desktop/ms692513) интерфейса на объект с именем приемника уведомлений. Если затем клиент вызывает **IDataObject::DAdvise**, установить соединение между объектом данных и приемник уведомлений.  
  
 Класс `IDataObjectImpl` предоставляет реализацию по умолчанию `IDataObject` и реализует **IUnknown** , отправляя сведения в дамп устройства в отладочных построений.  
  
 **Связанные статьи** [учебник по ATL](../../atl/active-template-library-atl-tutorial.md), [создается проект ATL](../../atl/reference/creating-an-atl-project.md)  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `IDataObject`  
  
 `IDataObjectImpl`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atlctl.h  
  
##  <a name="dadvise"></a>  IDataObjectImpl::DAdvise  
 Устанавливает соединение между объектом данных и приемника уведомлений.  
  
```
HRESULT DAdvise(
    FORMATETC* pformatetc,
    DWORD advf,
    IAdviseSink* pAdvSink,
    DWORD* pdwConnection);
```  
  
### <a name="remarks"></a>Примечания  
 Это позволяет приемник уведомлений для получения уведомлений об изменениях в объекте.  
  
 Разорвать соединение, вызовите [DUnadvise](#dunadvise).  
  
 В разделе [IDataObject::DAdvise](http://msdn.microsoft.com/library/windows/desktop/ms692579) в Windows SDK.  
  
##  <a name="dunadvise"></a>  IDataObjectImpl::DUnadvise  
 Завершает соединение, установленное ранее при помощи [DAdvise](#dadvise).  
  
```
HRESULT DUnadvise(DWORD dwConnection);
```  
  
### <a name="remarks"></a>Примечания  
 В разделе [IDataObject::DUnadvise](http://msdn.microsoft.com/library/windows/desktop/ms692448) в Windows SDK.  
  
##  <a name="enumdadvise"></a>  IDataObjectImpl::EnumDAdvise  
 Создает перечислитель для перебора текущих соединений для рекомендаций.  
  
```
HRESULT DAdvise(
    FORMATETC* pformatetc,
    DWORD advf,
    IAdviseSink* pAdvSink,
    DWORD* pdwConnection);
```  
  
### <a name="remarks"></a>Примечания  
 В разделе [IDataObject::EnumDAdvise](http://msdn.microsoft.com/library/windows/desktop/ms680127) в Windows SDK.  
  
##  <a name="enumformatetc"></a>  IDataObjectImpl::EnumFormatEtc  
 Создает перечислитель для перебора **FORMATETC** структуры, поддерживаемые объектом данных.  
  
```
HRESULT EnumFormatEtc(  
    DWORD dwDirection,
    IEnumFORMATETC** ppenumFormatEtc);
```  
  
### <a name="remarks"></a>Примечания  
 В разделе [IDataObject::EnumFormatEtc](http://msdn.microsoft.com/library/windows/desktop/ms683979) в Windows SDK.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает **E_NOTIMPL**.  
  
##  <a name="firedatachange"></a>  IDataObjectImpl::FireDataChange  
 Отправляет уведомление об изменении каждый приемник уведомлений, управляемого.  
  
```
HRESULT FireDataChange();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Стандартное значение `HRESULT` .  
  
##  <a name="getcanonicalformatetc"></a>  IDataObjectImpl::GetCanonicalFormatEtc  
 Извлекает логически эквивалентных **FORMATETC** структуры на ту, которая является более сложным.  
  
```
HRESULT GetCanonicalFormatEtc(FORMATETC* pformatetcIn, FORMATETC* pformatetcOut);
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает **E_NOTIMPL**.  
  
### <a name="remarks"></a>Примечания  
 В разделе [IDataObject::GetCanonicalFormatEtc](http://msdn.microsoft.com/library/windows/desktop/ms680685) в Windows SDK.  
  
##  <a name="getdata"></a>  IDataObjectImpl::GetData  
 Передает данные из объекта данных клиенту.  
  
```
HRESULT GetData(
    FORMATETC* pformatetcIn,
    STGMEDIUM* pmedium);
```  
  
### <a name="remarks"></a>Примечания  
 *PformatetcIn* параметра необходимо указать тип среды хранения, из **TYMED_MFPICT**.  
  
 В разделе [IDataObject::GetData](http://msdn.microsoft.com/library/windows/desktop/ms678431) в Windows SDK.  
  
##  <a name="getdatahere"></a>  IDataObjectImpl::GetDataHere  
 Аналогично `GetData`, за исключением того, клиент должен выделить **STGMEDIUM** структуры.  
  
```
HRESULT GetDataHere(
    FORMATETC* pformatetc,
    STGMEDIUM* pmedium);
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает **E_NOTIMPL**.  
  
### <a name="remarks"></a>Примечания  
 В разделе [IDataObject::GetDataHere](http://msdn.microsoft.com/library/windows/desktop/ms687266) в Windows SDK.  
  
##  <a name="querygetdata"></a>  IDataObjectImpl::QueryGetData  
 Определяет, поддерживает ли объект данных конкретного **FORMATETC** структуры для передачи данных.  
  
```
HRESULT QueryGetData(FORMATETC* pformatetc);
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает **E_NOTIMPL**.  
  
### <a name="remarks"></a>Примечания  
 В разделе [IDataObject::QueryGetData](http://msdn.microsoft.com/library/windows/desktop/ms680637) в Windows SDK.  
  
##  <a name="setdata"></a>  IDataObjectImpl::SetData  
 Данные передаются от клиента объект данных.  
  
```
HRESULT SetData(
    FORMATETC* pformatetc,
    STGMEDIUM* pmedium,
    BOOL fRelease);
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает **E_NOTIMPL**.  
  
### <a name="remarks"></a>Примечания  
 В разделе [IDataObject::SetData](http://msdn.microsoft.com/library/windows/desktop/ms686626) в Windows SDK.  
  
## <a name="see-also"></a>См. также  
 [Общие сведения о классе](../../atl/atl-class-overview.md)
