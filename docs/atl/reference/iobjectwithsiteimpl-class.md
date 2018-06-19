---
title: Класс интерфейс IObjectWithSiteImpl | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- IObjectWithSiteImpl
- ATLCOM/ATL::IObjectWithSiteImpl
- ATLCOM/ATL::IObjectWithSiteImpl::GetSite
- ATLCOM/ATL::IObjectWithSiteImpl::SetChildSite
- ATLCOM/ATL::IObjectWithSiteImpl::SetSite
- ATLCOM/ATL::IObjectWithSiteImpl::m_spUnkSite
dev_langs:
- C++
helpviewer_keywords:
- IObjectWithSiteImpl class
ms.assetid: 4e1f774f-bc3d-45ee-9a1c-c3533a511588
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 6c626db62a02fba70f926776ea214e664d2f7f82
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32362043"
---
# <a name="iobjectwithsiteimpl-class"></a>Интерфейс IObjectWithSiteImpl класса
Этот класс предоставляет методы, что объект для взаимодействия со своим сайтом.  
  
## <a name="syntax"></a>Синтаксис  
  
```
template <class T>
    class ATL_NO_VTABLE IObjectWithSiteImpl :
    public IObjectWithSite
```  
  
#### <a name="parameters"></a>Параметры  
 `T`  
 Класс, производный от `IObjectWithSiteImpl`.  
  
## <a name="members"></a>Участники  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[IObjectWithSiteImpl::GetSite](#getsite)|Запросы на сайт для указателя на интерфейс.|  
|[IObjectWithSiteImpl::SetChildSite](#setchildsite)|Предоставляет объект, на сайте **IUnknown** указателя.|  
|[IObjectWithSiteImpl::SetSite](#setsite)|Предоставляет объект, на сайте **IUnknown** указателя.|  
  
### <a name="public-data-members"></a>Открытые члены данных  
  
|Имя|Описание|  
|----------|-----------------|  
|[IObjectWithSiteImpl::m_spUnkSite](#m_spunksite)|Управляет сайта **IUnknown** указателя.|  
  
## <a name="remarks"></a>Примечания  
 [IObjectWithSite](http://msdn.microsoft.com/library/windows/desktop/ms693765) интерфейс позволяет объекту обмениваться данными со своим сайтом. Класс `IObjectWithSiteImpl` предоставляет стандартную реализацию этого интерфейса и реализует **IUnknown** , отправляя сведения в дамп устройства в отладочных построений.  
  
 `IObjectWithSiteImpl` Определяет два метода. Первый клиент вызывает метод `SetSite`, передача на сайте **IUnknown** указателя. Этот указатель сохранен внутри объекта и более поздней версии можно получить путем вызова `GetSite`.  
  
 Как правило, являются производными от класса `IObjectWithSiteImpl` при создании объекта, не является элементом управления. Для элементов управления, производных от класса [IOleObjectImpl](../../atl/reference/ioleobjectimpl-class.md), предоставляющее указатель сайта. Не являющиеся производными класса как из `IObjectWithSiteImpl` и `IOleObjectImpl`.  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `IObjectWithSite`  
  
 `IObjectWithSiteImpl`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atlcom.h  
  
##  <a name="getsite"></a>  IObjectWithSiteImpl::GetSite  
 Запрашивает сайта для указателя на интерфейс, определенный `riid`.  
  
```
STDMETHOD(GetSite)(
    REFIID riid,
    void** ppvSite);
```  
  
### <a name="remarks"></a>Примечания  
 Если сайт поддерживает этот интерфейс, указатель, возвращенный через `ppvSite`. В противном случае `ppvSite` равно **NULL**.  
  
 В разделе [IObjectWithSite::GetSite](http://msdn.microsoft.com/library/windows/desktop/ms694452) в Windows SDK.  
  
##  <a name="m_spunksite"></a>  IObjectWithSiteImpl::m_spUnkSite  
 Управляет сайта **IUnknown** указателя.  
  
```
CComPtr<IUnknown> m_spUnkSite;
```  
  
### <a name="remarks"></a>Примечания  
 `m_spUnkSite` Сначала получит этот указатель посредством вызова [SetSite](#setsite).  
  
##  <a name="setchildsite"></a>  IObjectWithSiteImpl::SetChildSite  
 Предоставляет объект, на сайте **IUnknown** указателя.  
  
```
HRESULT SetChildSite(IUnknown* pUnkSite);
```  
  
### <a name="parameters"></a>Параметры  
 *pUnkSite*  
 [in] Указатель на **IUnknown** указатель интерфейса управления данного объекта сайта. Если значение равно NULL, объект должен вызывать `IUnknown::Release` на любой существующий сайт, на этом этапе объект больше не знает своего сайта.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает `S_OK`.  
  
##  <a name="setsite"></a>  IObjectWithSiteImpl::SetSite  
 Предоставляет объект, на сайте **IUnknown** указателя.  
  
```
STDMETHOD(SetSite)(IUnknown* pUnkSite);
```  
  
### <a name="remarks"></a>Примечания  
 В разделе [IObjectWithSite::SetSite](http://msdn.microsoft.com/library/windows/desktop/ms683869) в Windows SDK.  
  
## <a name="see-also"></a>См. также  
 [Общие сведения о классе](../../atl/atl-class-overview.md)
