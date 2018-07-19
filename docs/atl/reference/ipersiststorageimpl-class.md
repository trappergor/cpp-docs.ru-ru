---
title: Класс IPersistStorageImpl | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- IPersistStorageImpl
- ATLCOM/ATL::IPersistStorageImpl
- ATLCOM/ATL::IPersistStorageImpl::GetClassID
- ATLCOM/ATL::IPersistStorageImpl::HandsOffStorage
- ATLCOM/ATL::IPersistStorageImpl::InitNew
- ATLCOM/ATL::IPersistStorageImpl::IsDirty
- ATLCOM/ATL::IPersistStorageImpl::Load
- ATLCOM/ATL::IPersistStorageImpl::Save
- ATLCOM/ATL::IPersistStorageImpl::SaveCompleted
dev_langs:
- C++
helpviewer_keywords:
- storage, ATL
- IPersistStorageImpl class
ms.assetid: d652f02c-239c-47c7-9a50-3e9fc3014fff
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 634a7a7373f6686ad36b645a73613a4ae350bbab
ms.sourcegitcommit: 7d68f8303e021e27dc8f4d36e764ed836e93d24f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/06/2018
ms.locfileid: "37884705"
---
# <a name="ipersiststorageimpl-class"></a>Класс IPersistStorageImpl
Этот класс реализует [IPersistStorage](http://msdn.microsoft.com/library/windows/desktop/ms679731) интерфейс.  
  
> [!IMPORTANT]
>  Этот класс и его члены не может использоваться в приложениях, выполняемых в среде выполнения Windows.  
  
## <a name="syntax"></a>Синтаксис  
  
```
template <class T>  
class ATL_NO_VTABLE IPersistStorageImpl : public IPersistStorage
```  
  
#### <a name="parameters"></a>Параметры  
 *T*  
 Ваш класс, производный от `IPersistStorageImpl`.  
  
## <a name="members"></a>Участники  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[IPersistStorageImpl::GetClassID](#getclassid)|Извлекает идентификатор CLSID объекта.|  
|[IPersistStorageImpl::HandsOffStorage](#handsoffstorage)|Указывает, что объект освободить все объекты хранилища и перейти в режим HandsOff. Реализация ATL, возвращается значение s_ок.|  
|[IPersistStorageImpl::InitNew](#initnew)|Инициализирует новое хранилище.|  
|[IPersistStorageImpl::IsDirty](#isdirty)|Проверяет, изменялся ли данные объекта с момента последнего сохранения.|  
|[IPersistStorageImpl::Load](#load)|Загружает свойства объекта из указанного хранилища.|  
|[IPersistStorageImpl::Save](#save)|Сохраняет свойства объекта в указанном хранилище.|  
|[IPersistStorageImpl::SaveCompleted](#savecompleted)|Уведомляет объект, который может возвращаться в обычном режиме для записи на свой объект хранения. Реализация ATL, возвращается значение s_ок.|  
  
## <a name="remarks"></a>Примечания  
 `IPersistStorageImpl` реализует [IPersistStorage](http://msdn.microsoft.com/library/windows/desktop/ms679731) интерфейс, который позволяет клиенту для запроса, нагрузки объекта и сохранить постоянные данные с помощью хранилища.  
  
 Реализации этого класса требуется класс `T` чтобы сделать реализацию `IPersistStreamInit` интерфейс, доступный через `QueryInterface`. Обычно это означает, что класс `T` должен быть производным от [IPersistStreamInitImpl](../../atl/reference/ipersiststreaminitimpl-class.md), предоставить запись для `IPersistStreamInit` в [COM карты](http://msdn.microsoft.com/library/ead2a1e3-334d-44ad-bb1f-b94bb14c2333)и использовать [сопоставление свойств](http://msdn.microsoft.com/library/bfe30be6-62c3-4dc2-bd49-21ef96f15427) для описания класса постоянных данных.  
  
 **Связанные статьи** [учебник по ATL](../../atl/active-template-library-atl-tutorial.md), [Создание проекта ATL](../../atl/reference/creating-an-atl-project.md)  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `IPersistStorage`  
  
 `IPersistStorageImpl`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atlcom.h  
  
##  <a name="getclassid"></a>  IPersistStorageImpl::GetClassID  
 Извлекает идентификатор CLSID объекта.  
  
```
STDMETHOD(GetClassID)(CLSID* pClassID);
```  
  
### <a name="remarks"></a>Примечания  
 См. в разделе [IPersist::GetClassID](http://msdn.microsoft.com/library/windows/desktop/ms688664) в Windows SDK.  
  
##  <a name="handsoffstorage"></a>  IPersistStorageImpl::HandsOffStorage  
 Указывает, что объект освободить все объекты хранилища и перейти в режим HandsOff.  
  
```
STDMETHOD(HandsOffStorage)(void);
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение S_OK.  
  
### <a name="remarks"></a>Примечания  
 См. в разделе [IPersistStorage::HandsOffStorage](http://msdn.microsoft.com/library/windows/desktop/ms679742) в Windows SDK.  
  
##  <a name="initnew"></a>  IPersistStorageImpl::InitNew  
 Инициализирует новое хранилище.  
  
```
STDMETHOD(InitNew)(IStorage*);
```  
  
### <a name="remarks"></a>Примечания  
 Делегирует реализацию ATL [IPersistStreamInit](http://msdn.microsoft.com/library/windows/desktop/ms682273) интерфейс.  
  
 См. в разделе [IPersistStorage:InitNew](http://msdn.microsoft.com/library/windows/desktop/ms687194) в Windows SDK.  
  
##  <a name="isdirty"></a>  IPersistStorageImpl::IsDirty  
 Проверяет, изменялся ли данные объекта с момента последнего сохранения.  
  
```
STDMETHOD(IsDirty)(void);
```  
  
### <a name="remarks"></a>Примечания  
 Делегирует реализацию ATL [IPersistStreamInit](http://msdn.microsoft.com/library/windows/desktop/ms682273) интерфейс.  
  
 См. в разделе [IPersistStorage:IsDirty](http://msdn.microsoft.com/library/windows/desktop/ms683910) в Windows SDK.  
  
##  <a name="load"></a>  IPersistStorageImpl::Load  
 Загружает свойства объекта из указанного хранилища.  
  
```
STDMETHOD(Load)(IStorage* pStorage);
```  
  
### <a name="remarks"></a>Примечания  
 Делегирует реализацию ATL [IPersistStreamInit](http://msdn.microsoft.com/library/windows/desktop/ms682273) интерфейс. `Load` поток с именем «Содержание» используется для извлечения данных объекта. [Сохранить](#save) метод изначально создает этот поток.  
  
 См. в разделе [IPersistStorage:Load](http://msdn.microsoft.com/library/windows/desktop/ms680557) в Windows SDK.  
  
##  <a name="save"></a>  IPersistStorageImpl::Save  
 Сохраняет свойства объекта в указанном хранилище.  
  
```
STDMETHOD(Save)(IStorage* pStorage, BOOL fSameAsLoad);
```  
  
### <a name="remarks"></a>Примечания  
 Делегирует реализацию ATL [IPersistStreamInit](http://msdn.microsoft.com/library/windows/desktop/ms682273) интерфейс. Когда `Save` является первым именем, он создает поток с именем «Содержание» в указанное хранилище. Этот поток используется в последующих вызовах `Save` и вызовы [нагрузки](#load).  
  
 См. в разделе [IPersistStorage:Save](http://msdn.microsoft.com/library/windows/desktop/ms680680) в Windows SDK.  
  
##  <a name="savecompleted"></a>  IPersistStorageImpl::SaveCompleted  
 Уведомляет объект, который может возвращаться в обычном режиме для записи на свой объект хранения.  
  
```
STDMETHOD(SaveCompleted)(IStorage*);
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение S_OK.  
  
### <a name="remarks"></a>Примечания  
 См. в разделе [IPersistStorage:SaveCompleted](http://msdn.microsoft.com/library/windows/desktop/ms679713) в Windows SDK.  
  
## <a name="see-also"></a>См. также  
 [Хранилищ и потоков](http://msdn.microsoft.com/library/windows/desktop/aa380352)   
 [Класс IPersistStreamInitImpl](../../atl/reference/ipersiststreaminitimpl-class.md)   
 [Класс IPersistPropertyBagImpl](../../atl/reference/ipersistpropertybagimpl-class.md)   
 [Общие сведения о классе](../../atl/atl-class-overview.md)
