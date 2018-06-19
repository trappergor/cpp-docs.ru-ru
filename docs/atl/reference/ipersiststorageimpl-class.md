---
title: Класс IPersistStorageImpl | Документы Microsoft
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
ms.openlocfilehash: 18f03ba235fdfc14dba22f1759240bd5fb72bafd
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32364666"
---
# <a name="ipersiststorageimpl-class"></a>Класс IPersistStorageImpl
Этот класс реализует [IPersistStorage](http://msdn.microsoft.com/library/windows/desktop/ms679731) интерфейса.  
  
> [!IMPORTANT]
>  Этот класс и его члены не может использоваться в приложениях, выполняемых в среде выполнения Windows.  
  
## <a name="syntax"></a>Синтаксис  
  
```
template <class T>  
class ATL_NO_VTABLE IPersistStorageImpl : public IPersistStorage
```  
  
#### <a name="parameters"></a>Параметры  
 `T`  
 Класс, производный от `IPersistStorageImpl`.  
  
## <a name="members"></a>Участники  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[IPersistStorageImpl::GetClassID](#getclassid)|Извлекает идентификатор CLSID объекта.|  
|[IPersistStorageImpl::HandsOffStorage](#handsoffstorage)|Указывает, что объект освободить все объекты хранилища и режим HandsOff. Возвращает реализацию ATL `S_OK`.|  
|[IPersistStorageImpl::InitNew](#initnew)|Инициализирует новое хранилище.|  
|[IPersistStorageImpl::IsDirty](#isdirty)|Проверяет, изменилась ли данные объекта со времени последнего сохранения.|  
|[IPersistStorageImpl::Load](#load)|Загружает свойства объекта из указанного хранилища.|  
|[IPersistStorageImpl::Save](#save)|Сохранение свойств объекта в указанном хранилище.|  
|[IPersistStorageImpl::SaveCompleted](#savecompleted)|Уведомляет объект, который может возвращаться в обычном режиме для записи в объект хранилища. Возвращает реализацию ATL `S_OK`.|  
  
## <a name="remarks"></a>Примечания  
 `IPersistStorageImpl` реализует [IPersistStorage](http://msdn.microsoft.com/library/windows/desktop/ms679731) интерфейс которого позволяет клиенту запросить объект нагрузки и сохранить постоянные данные с помощью хранилища.  
  
 Реализация этого класса требуется класс `T` вносить реализация `IPersistStreamInit` доступны через интерфейс `QueryInterface`. Обычно это означает, что класс `T` должен быть производным от [IPersistStreamInitImpl](../../atl/reference/ipersiststreaminitimpl-class.md), укажите запись для `IPersistStreamInit` в [сопоставления COM](http://msdn.microsoft.com/library/ead2a1e3-334d-44ad-bb1f-b94bb14c2333)и использовать [сопоставление свойств](http://msdn.microsoft.com/library/bfe30be6-62c3-4dc2-bd49-21ef96f15427) для описания класса постоянных данных.  
  
 **Связанные статьи** [учебник по ATL](../../atl/active-template-library-atl-tutorial.md), [создается проект ATL](../../atl/reference/creating-an-atl-project.md)  
  
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
 В разделе [IPersist::GetClassID](http://msdn.microsoft.com/library/windows/desktop/ms688664) в Windows SDK.  
  
##  <a name="handsoffstorage"></a>  IPersistStorageImpl::HandsOffStorage  
 Указывает, что объект освободить все объекты хранилища и режим HandsOff.  
  
```
STDMETHOD(HandsOffStorage)(void);
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает `S_OK`.  
  
### <a name="remarks"></a>Примечания  
 В разделе [IPersistStorage::HandsOffStorage](http://msdn.microsoft.com/library/windows/desktop/ms679742) в Windows SDK.  
  
##  <a name="initnew"></a>  IPersistStorageImpl::InitNew  
 Инициализирует новое хранилище.  
  
```
STDMETHOD(InitNew)(IStorage*);
```  
  
### <a name="remarks"></a>Примечания  
 Реализация ATL делегирует [программу](http://msdn.microsoft.com/library/windows/desktop/ms682273) интерфейса.  
  
 В разделе [IPersistStorage:InitNew](http://msdn.microsoft.com/library/windows/desktop/ms687194) в Windows SDK.  
  
##  <a name="isdirty"></a>  IPersistStorageImpl::IsDirty  
 Проверяет, изменилась ли данные объекта со времени последнего сохранения.  
  
```
STDMETHOD(IsDirty)(void);
```  
  
### <a name="remarks"></a>Примечания  
 Реализация ATL делегирует [программу](http://msdn.microsoft.com/library/windows/desktop/ms682273) интерфейса.  
  
 В разделе [IPersistStorage:IsDirty](http://msdn.microsoft.com/library/windows/desktop/ms683910) в Windows SDK.  
  
##  <a name="load"></a>  IPersistStorageImpl::Load  
 Загружает свойства объекта из указанного хранилища.  
  
```
STDMETHOD(Load)(IStorage* pStorage);
```  
  
### <a name="remarks"></a>Примечания  
 Реализация ATL делегирует [программу](http://msdn.microsoft.com/library/windows/desktop/ms682273) интерфейса. **Загрузка** использует поток под названием «Содержимое» для получения данных объекта. [Сохранить](#save) метод изначально создается данный поток.  
  
 В разделе [IPersistStorage:Load](http://msdn.microsoft.com/library/windows/desktop/ms680557) в Windows SDK.  
  
##  <a name="save"></a>  IPersistStorageImpl::Save  
 Сохранение свойств объекта в указанном хранилище.  
  
```
STDMETHOD(Save)(IStorage* pStorage, BOOL fSameAsLoad);
```  
  
### <a name="remarks"></a>Примечания  
 Реализация ATL делегирует [программу](http://msdn.microsoft.com/library/windows/desktop/ms682273) интерфейса. При **Сохранить** является первым именем, создает поток с именем «Содержимое» для указанного хранилища. Этот поток используется в последующих вызовах **Сохранить** и в вызовах [нагрузки](#load).  
  
 В разделе [IPersistStorage:Save](http://msdn.microsoft.com/library/windows/desktop/ms680680) в Windows SDK.  
  
##  <a name="savecompleted"></a>  IPersistStorageImpl::SaveCompleted  
 Уведомляет объект, который может возвращаться в обычном режиме для записи в объект хранилища.  
  
```
STDMETHOD(SaveCompleted)(IStorage*);
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает `S_OK`.  
  
### <a name="remarks"></a>Примечания  
 В разделе [IPersistStorage:SaveCompleted](http://msdn.microsoft.com/library/windows/desktop/ms679713) в Windows SDK.  
  
## <a name="see-also"></a>См. также  
 [Хранилищ и потоков](http://msdn.microsoft.com/library/windows/desktop/aa380352)   
 [Класс IPersistStreamInitImpl](../../atl/reference/ipersiststreaminitimpl-class.md)   
 [Класс IPersistPropertyBagImpl](../../atl/reference/ipersistpropertybagimpl-class.md)   
 [Общие сведения о классе](../../atl/atl-class-overview.md)
