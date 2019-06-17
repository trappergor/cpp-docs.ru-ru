---
title: Класс ISupportErrorInfoImpl
ms.date: 06/13/2019
f1_keywords:
- ISupportErrorInfoImpl
- ATLCOM/ATL::ISupportErrorInfoImpl
- ATLCOM/ATL::ISupportErrorInfoImpl::InterfaceSupportsErrorInfo
helpviewer_keywords:
- ISupportErrorInfo ATL implementation
- ISupportErrorInfoImpl class
- error information, ATL
ms.assetid: e33a4b11-a123-41cf-bcea-7b19743902af
ms.openlocfilehash: 650d90c9ec98754e11586f63e0871b70ebbe34f3
ms.sourcegitcommit: e79188287189b76b34eb7e8fb1bfe646bdb586bc
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/14/2019
ms.locfileid: "67141706"
---
# <a name="isupporterrorinfoimpl-class"></a>Класс ISupportErrorInfoImpl

Этот класс предоставляет реализацию по умолчанию [ISupportErrorInfo интерфейс](/windows/desktop/api/oaidl/nn-oaidl-isupporterrorinfo) и может использоваться, когда только один интерфейс выдает ошибки для объекта.

> [!IMPORTANT]
> Этот класс и его члены не может использоваться в приложениях, выполняемых в среде выполнения Windows.

## <a name="syntax"></a>Синтаксис

```cpp
template<const IID* piid>
class ATL_NO_VTABLE ISupportErrorInfoImpl
   : public ISupportErrorInfo
```

### <a name="parameters"></a>Параметры

*piid*<br/>
Указатель на идентификатор IID интерфейса, поддерживающего [IErrorInfo](/windows/desktop/api/oaidl/nn-oaidl-ierrorinfo).

## <a name="members"></a>Участники

### <a name="public-methods"></a>Открытые методы

|name|Описание|
|----------|-----------------|
|[ISupportErrorInfoImpl::InterfaceSupportsErrorInfo](#interfacesupportserrorinfo)|Указывает, определяется ли интерфейс `riid` поддерживает [IErrorInfo](/windows/desktop/api/oaidl/nn-oaidl-ierrorinfo) интерфейс.|

## <a name="remarks"></a>Примечания

[ISupportErrorInfo интерфейс](/windows/desktop/api/oaidl/nn-oaidl-isupporterrorinfo) гарантирует, что сведения об ошибке могут быть возвращены клиенту. Объекты, использующие `IErrorInfo` должен реализовывать `ISupportErrorInfo`.

Класс `ISupportErrorInfoImpl` предоставляет реализацию по умолчанию `ISupportErrorInfo` и может использоваться, когда только один интерфейс выдает ошибки для объекта. Пример:

[!code-cpp[NVC_ATL_COM#48](../../atl/codesnippet/cpp/isupporterrorinfoimpl-class_1.h)]

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`ISupportErrorInfo`

`ISupportErrorInfoImpl`

## <a name="requirements"></a>Требования

**Заголовок:** atlcom.h

##  <a name="interfacesupportserrorinfo"></a>  ISupportErrorInfoImpl::InterfaceSupportsErrorInfo

Указывает, определяется ли интерфейс `riid` поддерживает [IErrorInfo](/windows/desktop/api/oaidl/nn-oaidl-ierrorinfo) интерфейс.

```cpp
STDMETHOD(InterfaceSupportsErrorInfo)(REFIID riid);
```

### <a name="remarks"></a>Примечания

См. в разделе [ISupportErrorInfo::InterfaceSupportsErrorInfo](/windows/desktop/api/oaidl/nf-oaidl-isupporterrorinfo-interfacesupportserrorinfo) в Windows SDK.

## <a name="see-also"></a>См. также

[Общие сведения о классе](../../atl/atl-class-overview.md)
