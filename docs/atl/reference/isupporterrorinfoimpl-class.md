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
ms.openlocfilehash: d5e7f087f6646940777ae8b2d2a4ea888fdd3593
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/15/2019
ms.locfileid: "69495365"
---
# <a name="isupporterrorinfoimpl-class"></a>Класс ISupportErrorInfoImpl

Этот класс предоставляет реализацию [интерфейса ISupportErrorInfo](/windows/win32/api/oaidl/nn-oaidl-isupporterrorinfo) по умолчанию и может использоваться, когда только один интерфейс создает ошибки для объекта.

> [!IMPORTANT]
> Этот класс и его члены не могут использоваться в приложениях, выполняемых в среда выполнения Windows.

## <a name="syntax"></a>Синтаксис

```cpp
template<const IID* piid>
class ATL_NO_VTABLE ISupportErrorInfoImpl
   : public ISupportErrorInfo
```

### <a name="parameters"></a>Параметры

*пиид*<br/>
Указатель на идентификатор IID интерфейса, который поддерживает [IErrorInfo](/windows/win32/api/oaidl/nn-oaidl-ierrorinfo).

## <a name="members"></a>Участники

### <a name="public-methods"></a>Открытые методы

|name|Описание|
|----------|-----------------|
|[ISupportErrorInfoImpl:: Интерфацесуппортсерроринфо](#interfacesupportserrorinfo)|Указывает, поддерживает ли интерфейс, `riid` определенный с помощью, интерфейс [IErrorInfo](/windows/win32/api/oaidl/nn-oaidl-ierrorinfo) .|

## <a name="remarks"></a>Примечания

[Интерфейс ISupportErrorInfo](/windows/win32/api/oaidl/nn-oaidl-isupporterrorinfo) гарантирует, что сведения об ошибке могут быть возвращены клиенту. Объекты, использующие `IErrorInfo` , должны `ISupportErrorInfo`реализовывать.

Класс `ISupportErrorInfoImpl` предоставляет`ISupportErrorInfo` реализацию по умолчанию и может использоваться, когда только один интерфейс создает ошибки для объекта. Например:

[!code-cpp[NVC_ATL_COM#48](../../atl/codesnippet/cpp/isupporterrorinfoimpl-class_1.h)]

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`ISupportErrorInfo`

`ISupportErrorInfoImpl`

## <a name="requirements"></a>Требования

**Заголовок:** атлком. h

##  <a name="interfacesupportserrorinfo"></a>ISupportErrorInfoImpl:: Интерфацесуппортсерроринфо

Указывает, поддерживает ли интерфейс, `riid` определенный с помощью, интерфейс [IErrorInfo](/windows/win32/api/oaidl/nn-oaidl-ierrorinfo) .

```cpp
STDMETHOD(InterfaceSupportsErrorInfo)(REFIID riid);
```

### <a name="remarks"></a>Примечания

См. раздел [ISupportErrorInfo:: интерфацесуппортсерроринфо](/windows/win32/api/oaidl/nf-oaidl-isupporterrorinfo-interfacesupportserrorinfo) в Windows SDK.

## <a name="see-also"></a>См. также

[Обзор класса](../../atl/atl-class-overview.md)
