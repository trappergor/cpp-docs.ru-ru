---
title: "Класс IPersistStorageImpl | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
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
caps.latest.revision: 20
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: a5a855f81072316510efb47c3f9650a5feafa39b
ms.contentlocale: ru-ru
ms.lasthandoff: 02/24/2017

---
# <a name="ipersiststorageimpl-class"></a>Класс IPersistStorageImpl
Этот класс реализует [IPersistStorage](http://msdn.microsoft.com/library/windows/desktop/ms679731) интерфейса.  
  
> [!IMPORTANT]
>  Этот класс и его члены не может использоваться в приложениях, выполняемых в [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)].  
  
## <a name="syntax"></a>Синтаксис  
  
```
template <class T>  
class ATL_NO_VTABLE IPersistStorageImpl : public IPersistStorage
```  
  
#### <a name="parameters"></a>Параметры  
 `T`  
 Класс, производный от `IPersistStorageImpl`.  
  
## <a name="members"></a>Члены  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[IPersistStorageImpl::GetClassID](#getclassid)|Извлекает идентификатор CLSID объекта.|  
|[IPersistStorageImpl::HandsOffStorage](#handsoffstorage)|Указывает, что объект освободить все объекты хранилища и режим HandsOff. Возвращает реализацию ATL `S_OK`.|  
|[IPersistStorageImpl::InitNew](#initnew)|Инициализирует новое хранилище.|  
|[IPersistStorageImpl::IsDirty](#isdirty)|Проверяет, изменялся ли данные объекта с момента последнего сохранения.|  
|[IPersistStorageImpl::Load](#load)|Загружает свойства объекта из указанного хранилища.|  
|[IPersistStorageImpl::Save](#save)|Сохраняет свойства объекта в указанном хранилище.|  
|[IPersistStorageImpl::SaveCompleted](#savecompleted)|Уведомляет объект, который может возвращаться в нормальный режим для записи в объект хранилища. Возвращает реализацию ATL `S_OK`.|  
  
## <a name="remarks"></a>Примечания  
 `IPersistStorageImpl`реализует [IPersistStorage](http://msdn.microsoft.com/library/windows/desktop/ms679731) интерфейс, который позволяет клиенту запрос, объект нагрузочных и сохранить постоянные данные с помощью хранилища.  
  
 Реализация этого класса требуется класс `T` вносить в реализацию `IPersistStreamInit` доступно через интерфейс `QueryInterface`. Обычно это означает, что класс `T` должен быть производным от [IPersistStreamInitImpl](../../atl/reference/ipersiststreaminitimpl-class.md), предоставить запись для `IPersistStreamInit` в [сопоставления COM](http://msdn.microsoft.com/library/ead2a1e3-334d-44ad-bb1f-b94bb14c2333)и использовать [сопоставление свойств](http://msdn.microsoft.com/library/bfe30be6-62c3-4dc2-bd49-21ef96f15427) для описания класса постоянных данных.  
  
 **Связанные статьи** [учебник по ATL](../../atl/active-template-library-atl-tutorial.md), [создается проект ATL](../../atl/reference/creating-an-atl-project.md)  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `IPersistStorage`  
  
 `IPersistStorageImpl`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** файле atlcom.h  
  
##  <a name="getclassid"></a>IPersistStorageImpl::GetClassID  
 Извлекает идентификатор CLSID объекта.  
  
```
STDMETHOD(GetClassID)(CLSID* pClassID);
```  
  
### <a name="remarks"></a>Примечания  
 В разделе [IPersist::GetClassID](http://msdn.microsoft.com/library/windows/desktop/ms688664) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="handsoffstorage"></a>IPersistStorageImpl::HandsOffStorage  
 Указывает, что объект освободить все объекты хранилища и режим HandsOff.  
  
```
STDMETHOD(HandsOffStorage)(void);
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает `S_OK`.  
  
### <a name="remarks"></a>Примечания  
 В разделе [IPersistStorage::HandsOffStorage](http://msdn.microsoft.com/library/windows/desktop/ms679742) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="initnew"></a>IPersistStorageImpl::InitNew  
 Инициализирует новое хранилище.  
  
```
STDMETHOD(InitNew)(IStorage*);
```  
  
### <a name="remarks"></a>Примечания  
 Делегирует реализацию ATL [программу](http://msdn.microsoft.com/library/windows/desktop/ms682273) интерфейса.  
  
 В разделе [IPersistStorage:InitNew](http://msdn.microsoft.com/library/windows/desktop/ms687194) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="isdirty"></a>IPersistStorageImpl::IsDirty  
 Проверяет, изменялся ли данные объекта с момента последнего сохранения.  
  
```
STDMETHOD(IsDirty)(void);
```  
  
### <a name="remarks"></a>Примечания  
 Делегирует реализацию ATL [программу](http://msdn.microsoft.com/library/windows/desktop/ms682273) интерфейса.  
  
 В разделе [IPersistStorage:IsDirty](http://msdn.microsoft.com/library/windows/desktop/ms683910) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="load"></a>IPersistStorageImpl::Load  
 Загружает свойства объекта из указанного хранилища.  
  
```
STDMETHOD(Load)(IStorage* pStorage);
```  
  
### <a name="remarks"></a>Примечания  
 Делегирует реализацию ATL [программу](http://msdn.microsoft.com/library/windows/desktop/ms682273) интерфейса. **Загрузка** используется для получения данных объекта в поток с именем «Содержимое». [Сохранить](#save) метод изначально создается данный поток.  
  
 В разделе [IPersistStorage:Load](http://msdn.microsoft.com/library/windows/desktop/ms680557) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="save"></a>IPersistStorageImpl::Save  
 Сохраняет свойства объекта в указанном хранилище.  
  
```
STDMETHOD(Save)(IStorage* pStorage, BOOL fSameAsLoad);
```  
  
### <a name="remarks"></a>Примечания  
 Делегирует реализацию ATL [программу](http://msdn.microsoft.com/library/windows/desktop/ms682273) интерфейса. При **Сохранить** является первым именем, он создает поток под названием «Содержимое» для указанного хранилища. Этот поток используется в последующих вызовов **Сохранить** и вызовов [нагрузки](#load).  
  
 В разделе [IPersistStorage:Save](http://msdn.microsoft.com/library/windows/desktop/ms680680) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="savecompleted"></a>IPersistStorageImpl::SaveCompleted  
 Уведомляет объект, который может возвращаться в нормальный режим для записи в объект хранилища.  
  
```
STDMETHOD(SaveCompleted)(IStorage*);
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает `S_OK`.  
  
### <a name="remarks"></a>Примечания  
 В разделе [IPersistStorage:SaveCompleted](http://msdn.microsoft.com/library/windows/desktop/ms679713) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
## <a name="see-also"></a>См. также  
 [Хранилищ и потоков](http://msdn.microsoft.com/library/windows/desktop/aa380352)   
 [Класс IPersistStreamInitImpl](../../atl/reference/ipersiststreaminitimpl-class.md)   
 [Класс IPersistPropertyBagImpl](../../atl/reference/ipersistpropertybagimpl-class.md)   
 [Общие сведения о классе](../../atl/atl-class-overview.md)

