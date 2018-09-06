---
title: Класс IProvideClassInfo2Impl | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- IProvideClassInfo2Impl
- ATLCOM/ATL::IProvideClassInfo2Impl
- ATLCOM/ATL::IProvideClassInfo2Impl::IProvideClassInfo2Impl
- ATLCOM/ATL::IProvideClassInfo2Impl::GetClassInfo
- ATLCOM/ATL::IProvideClassInfo2Impl::GetGUID
- ATLCOM/ATL::IProvideClassInfo2Impl::_tih
dev_langs:
- C++
helpviewer_keywords:
- IProvideClassInfo2Impl class
- IProvideClassInfo2 ATL implementation
- class information, ATL
ms.assetid: d74956e8-9c69-4cba-b99d-ca1ac031bb9d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: a3e0ac7cf3a5448a2963aa92c2e275be796c895d
ms.sourcegitcommit: 92dbc4b9bf82fda96da80846c9cfcdba524035af
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/05/2018
ms.locfileid: "43758343"
---
# <a name="iprovideclassinfo2impl-class"></a>Класс IProvideClassInfo2Impl

Этот класс предоставляет реализацию по умолчанию [IProvideClassInfo](/windows/desktop/api/ocidl/nn-ocidl-iprovideclassinfo) и [IProvideClassInfo2](/windows/desktop/api/ocidl/nn-ocidl-iprovideclassinfo2) методы.

## <a name="syntax"></a>Синтаксис

```
template <const CLSID* pcoclsid,
    const IID* psrcid,
    const GUID* plibid = &CAtlModule::m_libid,
    WORD wMajor = 1,
    WORD wMinor = 0, class tihclass = CComTypeInfoHolder>  
class ATL_NO_VTABLE IProvideClassInfo2Impl : public IProvideClassInfo2
```

#### <a name="parameters"></a>Параметры

*pcoclsid*  
Указатель на идентификатор компонентного класса.

*psrcid*  
Указатель на идентификатор компонентного класса по умолчанию исходящие disp-интерфейса.

*plibid*  
Указатель на идентификатор LIBID библиотеки типов, содержащий сведения об интерфейсе. По умолчанию передается библиотеки типов на уровне сервера.

*wMajor*  
Основной номер версии для библиотеки типов. Значение по умолчанию — 1.

*wMinor*  
Дополнительный номер версии для библиотеки типов. Значение по умолчанию — 0.

*tihclass*  
Класс, используемый для управления coclass сведения о типе. Значение по умолчанию — `CComTypeInfoHolder`.

## <a name="members"></a>Участники

### <a name="constructors"></a>Конструкторы

|name|Описание|
|----------|-----------------|
|[IProvideClassInfo2Impl::IProvideClassInfo2Impl](#iprovideclassinfo2impl)|Конструктор.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[IProvideClassInfo2Impl::GetClassInfo](#getclassinfo)|Извлекает `ITypeInfo` указатель на сведения о типе компонентного класса.|
|[IProvideClassInfo2Impl::GetGUID](#getguid)|Извлекает идентификатор GUID исходящего объекта disp-интерфейса.|

### <a name="protected-data-members"></a>Защищенные члены данных

|name|Описание|
|----------|-----------------|
|[IProvideClassInfo2Impl::_tih](#_tih)|Управляет сведения о типе для компонентного класса.|

## <a name="remarks"></a>Примечания

[IProvideClassInfo2](/windows/desktop/api/ocidl/nn-ocidl-iprovideclassinfo2) интерфейс расширяет [IProvideClassInfo](/windows/desktop/api/ocidl/nn-ocidl-iprovideclassinfo) , добавив `GetGUID` метод. Этот метод позволяет клиенту получить объекта исходящего интерфейса IID для набора событий его по умолчанию. Класс `IProvideClassInfo2Impl` предоставляет реализацию по умолчанию `IProvideClassInfo` и `IProvideClassInfo2` методы.

`IProvideClassInfo2Impl` содержит статический член типа `CComTypeInfoHolder` , управляющий сведения о типе для компонентного класса.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`IProvideClassInfo2`

`IProvideClassInfo2Impl`

## <a name="requirements"></a>Требования

**Заголовок:** atlcom.h

##  <a name="getclassinfo"></a>  IProvideClassInfo2Impl::GetClassInfo

Извлекает `ITypeInfo` указатель на сведения о типе компонентного класса.

```
STDMETHOD(GetClassInfo)(ITypeInfo** pptinfo);
```

### <a name="remarks"></a>Примечания

См. в разделе [IProvideClassInfo::GetClassInfo](/windows/desktop/api/ocidl/nf-ocidl-iprovideclassinfo-getclassinfo) в Windows SDK.

##  <a name="getguid"></a>  IProvideClassInfo2Impl::GetGUID

Извлекает идентификатор GUID исходящего объекта disp-интерфейса.

```
STDMETHOD(GetGUID)(
    DWORD dwGuidKind,
    GUID* pGUID);
```

### <a name="remarks"></a>Примечания

См. в разделе [IProvideClassInfo2::GetGUID](/windows/desktop/api/ocidl/nf-ocidl-iprovideclassinfo2-getguid) в Windows SDK.

##  <a name="iprovideclassinfo2impl"></a>  IProvideClassInfo2Impl::IProvideClassInfo2Impl

Конструктор.

```
IProvideClassInfo2Impl();
```

### <a name="remarks"></a>Примечания

Вызовы `AddRef` на [_tih](#_tih) член. Деструктор вызывает `Release`.

##  <a name="_tih"></a>  IProvideClassInfo2Impl::_tih

Статические данные-член является экземпляром класса параметр шаблона, *tihclass*, по умолчанию — `CComTypeInfoHolder`.

```
static  tihclass
    _tih;
```

### <a name="remarks"></a>Примечания

`_tih` Управляет сведения о типе для компонентного класса.

## <a name="see-also"></a>См. также

[Общие сведения о классе](../../atl/atl-class-overview.md)
