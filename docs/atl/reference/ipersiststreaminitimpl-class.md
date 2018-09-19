---
title: Класс IPersistStreamInitImpl | Документация Майкрософт
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
ms.openlocfilehash: 85e772b9222f2066259042e551fa393758559ab2
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46115883"
---
# <a name="ipersiststreaminitimpl-class"></a>Класс IPersistStreamInitImpl

Этот класс реализует `IUnknown` и предоставляет реализацию по умолчанию [IPersistStreamInit](/windows/desktop/api/ocidl/nn-ocidl-ipersiststreaminit) интерфейс.

> [!IMPORTANT]
>  Этот класс и его члены не может использоваться в приложениях, выполняемых в среде выполнения Windows.

## <a name="syntax"></a>Синтаксис

```
template<class T>
class ATL_NO_VTABLE IPersistStreamInitImpl 
   : public IPersistStreamInit
```

#### <a name="parameters"></a>Параметры

*T*<br/>
Ваш класс, производный от `IPersistStreamInitImpl`.

## <a name="members"></a>Участники

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[IPersistStreamInitImpl::GetClassID](#getclassid)|Извлекает идентификатор CLSID объекта.|
|[IPersistStreamInitImpl::GetSizeMax](#getsizemax)|Возвращает размер потока, необходимого для сохранения данных объекта. Реализация ATL возвращает E_NOTIMPL.|
|[IPersistStreamInitImpl::InitNew](#initnew)|Инициализирует только что созданный объект.|
|[IPersistStreamInitImpl::IsDirty](#isdirty)|Проверяет, изменялся ли данные объекта с момента последнего сохранения.|
|[IPersistStreamInitImpl::Load](#load)|Загружает свойства объекта из указанного потока.|
|[IPersistStreamInitImpl::Save](#save)|Сохраняет свойства объекта в указанный поток.|

## <a name="remarks"></a>Примечания

[IPersistStreamInit](/windows/desktop/api/ocidl/nn-ocidl-ipersiststreaminit) интерфейс позволяет клиенту запросить, что объект загружает и сохраняет его постоянных данных в один поток. Класс `IPersistStreamInitImpl` предоставляет стандартную реализацию этого интерфейса и реализует `IUnknown` , отправляя данные в дамп сборок устройства в режиме отладки.

**Связанные статьи** [учебник по ATL](../../atl/active-template-library-atl-tutorial.md), [Создание проекта ATL](../../atl/reference/creating-an-atl-project.md)

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

См. в разделе [IPersist::GetClassID](/windows/desktop/api/objidl/nf-objidl-ipersist-getclassid) в Windows SDK.

##  <a name="getsizemax"></a>  IPersistStreamInitImpl::GetSizeMax

Возвращает размер потока, необходимого для сохранения данных объекта.

```
STDMETHOD(GetSizeMax)(ULARGE_INTEGER FAR* pcbSize);
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает E_NOTIMPL.

### <a name="remarks"></a>Примечания

См. в разделе [IPersistStreamInit::GetSizeMax](/windows/desktop/api/ocidl/nf-ocidl-ipersiststreaminit-getsizemax) в Windows SDK.

##  <a name="initnew"></a>  IPersistStreamInitImpl::InitNew

Инициализирует только что созданный объект.

```
STDMETHOD(InitNew)();
```

### <a name="remarks"></a>Примечания

См. в разделе [IPersistStreamInit::InitNew](/windows/desktop/api/ocidl/nf-ocidl-ipersiststreaminit-initnew) в Windows SDK.

##  <a name="isdirty"></a>  IPersistStreamInitImpl::IsDirty

Проверяет, изменялся ли данные объекта с момента последнего сохранения.

```
STDMETHOD(IsDirty)();
```

### <a name="remarks"></a>Примечания

См. в разделе [IPersistStreamInit::IsDirty](/windows/desktop/api/ocidl/nf-ocidl-ipersiststreaminit-isdirty) в Windows SDK.

##  <a name="load"></a>  IPersistStreamInitImpl::Load

Загружает свойства объекта из указанного потока.

```
STDMETHOD(Load)(LPSTREAM pStm);
```

### <a name="remarks"></a>Примечания

ATL использует сопоставление свойств объекта для извлечения этой информации.

См. в разделе [IPersistStreamInit::Load](/windows/desktop/api/ocidl/nf-ocidl-ipersiststreaminit-load) в Windows SDK.

##  <a name="save"></a>  IPersistStreamInitImpl::Save

Сохраняет свойства объекта в указанный поток.

```
STDMETHOD(Save)(LPSTREAM pStm, BOOL fClearDirty);
```

### <a name="remarks"></a>Примечания

ATL использует сопоставление свойств объекта для хранения подобной информации.

См. в разделе [IPersistStreamInit::Save](/windows/desktop/api/ocidl/nf-ocidl-ipersiststreaminit-save) в Windows SDK.

## <a name="see-also"></a>См. также

[Хранилищ и потоков](/windows/desktop/Stg/storages-and-streams)<br/>
[Общие сведения о классе](../../atl/atl-class-overview.md)
