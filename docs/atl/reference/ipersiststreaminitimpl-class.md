---
title: Класс IPersistStreamInitImpl | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- IPersistStreamInitImpl
- ATLCOM/ATL::IPersistStreamInitImpl
- ATLCOM/ATL::IPersistStreamInitImpl::GetClassID
- ATLCOM/ATL::IPersistStreamInitImpl::GetSizeMax
- ATLCOM/ATL::IPersistStreamInitImpl::InitNew
- ATLCOM/ATL::IPersistStreamInitImpl::IsDirty
- ATLCOM/ATL::IPersistStreamInitImpl::Load
- ATLCOM/ATL::IPersistStreamInitImpl::Save
dev_langs:
- C++
helpviewer_keywords:
- IPersistStreamInit ATL implementation
- IPersistStreamInitImpl class
- streams, ATL
ms.assetid: ef217c3c-020f-4cf8-871e-ef68e57865b8
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: a51dd5e198a86b7bb17a6182c1edb098f23a8e47
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32360460"
---
# <a name="ipersiststreaminitimpl-class"></a>Класс IPersistStreamInitImpl
Этот класс реализует **IUnknown** и предоставляет реализацию по умолчанию [программу](http://msdn.microsoft.com/library/windows/desktop/ms682273) интерфейса.  
  
> [!IMPORTANT]
>  Этот класс и его члены не может использоваться в приложениях, выполняемых в среде выполнения Windows.  
  
## <a name="syntax"></a>Синтаксис  
  
```
template<class T>  
class ATL_NO_VTABLE IPersistStreamInitImpl 
   : public IPersistStreamInit
```  
  
#### <a name="parameters"></a>Параметры  
 `T`  
 Класс, производный от `IPersistStreamInitImpl`.  
  
## <a name="members"></a>Участники  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[IPersistStreamInitImpl::GetClassID](#getclassid)|Извлекает идентификатор CLSID объекта.|  
|[IPersistStreamInitImpl::GetSizeMax](#getsizemax)|Возвращает размер потока, необходимого для сохранения данных объекта. Возвращает реализацию ATL **E_NOTIMPL**.|  
|[IPersistStreamInitImpl::InitNew](#initnew)|Инициализирует только что созданный объект.|  
|[IPersistStreamInitImpl::IsDirty](#isdirty)|Проверяет, изменилась ли данные объекта со времени последнего сохранения.|  
|[IPersistStreamInitImpl::Load](#load)|Загружает свойства объекта из указанного потока.|  
|[IPersistStreamInitImpl::Save](#save)|Сохранение свойств объекта в указанный поток.|  
  
## <a name="remarks"></a>Примечания  
 [Программу](http://msdn.microsoft.com/library/windows/desktop/ms682273) интерфейс позволяет клиенту запрашивать, ваш объект загружает и сохраняет постоянные данные в отдельном потоке. Класс `IPersistStreamInitImpl` предоставляет стандартную реализацию этого интерфейса и реализует **IUnknown** , отправляя сведения в дамп устройства в отладочных построений.  
  
 **Связанные статьи** [учебник по ATL](../../atl/active-template-library-atl-tutorial.md), [создается проект ATL](../../atl/reference/creating-an-atl-project.md)  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `IPersistStreamInit`  
  
 `IPersistStreamInitImpl`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atlcom.h  
  
##  <a name="getclassid"></a>  IPersistStreamInitImpl::GetClassID  
 Извлекает идентификатор CLSID объекта.  
  
```
STDMETHOD(GetClassID)(CLSID* pClassID);
```  
  
### <a name="remarks"></a>Примечания  
 В разделе [IPersist::GetClassID](http://msdn.microsoft.com/library/windows/desktop/ms688664) в Windows SDK.  
  
##  <a name="getsizemax"></a>  IPersistStreamInitImpl::GetSizeMax  
 Возвращает размер потока, необходимого для сохранения данных объекта.  
  
```
STDMETHOD(GetSizeMax)(ULARGE_INTEGER FAR* pcbSize);
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает **E_NOTIMPL**.  
  
### <a name="remarks"></a>Примечания  
 В разделе [IPersistStreamInit::GetSizeMax](http://msdn.microsoft.com/library/windows/desktop/ms687287) в Windows SDK.  
  
##  <a name="initnew"></a>  IPersistStreamInitImpl::InitNew  
 Инициализирует только что созданный объект.  
  
```
STDMETHOD(InitNew)();
```  
  
### <a name="remarks"></a>Примечания  
 В разделе [IPersistStreamInit::InitNew](http://msdn.microsoft.com/library/windows/desktop/ms690234) в Windows SDK.  
  
##  <a name="isdirty"></a>  IPersistStreamInitImpl::IsDirty  
 Проверяет, изменилась ли данные объекта со времени последнего сохранения.  
  
```
STDMETHOD(IsDirty)();
```  
  
### <a name="remarks"></a>Примечания  
 В разделе [IPersistStreamInit::IsDirty](http://msdn.microsoft.com/library/windows/desktop/ms680092) в Windows SDK.  
  
##  <a name="load"></a>  IPersistStreamInitImpl::Load  
 Загружает свойства объекта из указанного потока.  
  
```
STDMETHOD(Load)(LPSTREAM pStm);
```  
  
### <a name="remarks"></a>Примечания  
 ATL использует сопоставление свойств объекта для получения этих сведений.  
  
 В разделе [IPersistStreamInit::Load](http://msdn.microsoft.com/library/windows/desktop/ms680730) в Windows SDK.  
  
##  <a name="save"></a>  IPersistStreamInitImpl::Save  
 Сохранение свойств объекта в указанный поток.  
  
```
STDMETHOD(Save)(LPSTREAM pStm, BOOL fClearDirty);
```  
  
### <a name="remarks"></a>Примечания  
 ATL использует сопоставление свойств объекта для хранения этой информации.  
  
 В разделе [IPersistStreamInit::Save](http://msdn.microsoft.com/library/windows/desktop/ms694439) в Windows SDK.  
  
## <a name="see-also"></a>См. также  
 [Хранилищ и потоков](http://msdn.microsoft.com/library/windows/desktop/aa380352)   
 [Общие сведения о классе](../../atl/atl-class-overview.md)
