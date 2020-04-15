---
title: Класс CAtlModuleT
ms.date: 11/04/2016
f1_keywords:
- CAtlModuleT
- ATLBASE/ATL::CAtlModuleT
- ATLBASE/ATL::CAtlModuleT::CAtlModuleT
- ATLBASE/ATL::CAtlModuleT::InitLibId
- ATLBASE/ATL::CAtlModuleT::RegisterAppId
- ATLBASE/ATL::CAtlModuleT::RegisterServer
- ATLBASE/ATL::CAtlModuleT::UnregisterAppId
- ATLBASE/ATL::CAtlModuleT::UnregisterServer
- ATLBASE/ATL::CAtlModuleT::UpdateRegistryAppId
helpviewer_keywords:
- CAtlModuleT class
ms.assetid: 9b74d02f-9117-47b1-a05e-c5945f83dd2b
ms.openlocfilehash: bf64c073249b7426fafb430a708573d9d06d11fd
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81321412"
---
# <a name="catlmodulet-class"></a>Класс CAtlModuleT

Этот класс реализует модуль ATL.

## <a name="syntax"></a>Синтаксис

```
template <class T>
class ATL_NO_VTABLE CAtlModuleT : public CAtlModule
```

#### <a name="parameters"></a>Параметры

*T*<br/>
Ваш класс происходит `CAtlModuleT`от .

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CAtlModuleT::CAtlModuleT](#catlmodulet)|Конструктор.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CAtlModuleT::InitLibId](#initlibid)|Инициализирует член данных, содержащий GUID текущего модуля.|
|[CAtlModuleT::RegisterAppId](#registerappid)|Добавляет EXE в реестр.|
|[CAtlModuleT::RegisterServer](#registerserver)|Добавляет услугу в реестр.|
|[CAtlModuleT::UnregisterAppId](#unregisterappid)|Удаляет EXE из реестра.|
|[CAtlModuleT::UnregisterServer](#unregisterserver)|Удаляет службу из реестра.|
|[CAtlModuleT::UpdateRegistryAppId](#updateregistryappid)|Обновление информации EXE в реестре.|

## <a name="remarks"></a>Remarks

`CAtlModuleT`, полученные из [CAtlModule](../../atl/reference/catlmodule-class.md), реализует Исполняемый (EXE) или сервис (EXE) ATL модуль. Исполняемый модуль — это локальный сервер, не отменяемый, в то время как модуль службы — это приложение Windows, которое работает в фоновом режиме при запуске Windows.

`CAtlModuleT`обеспечивает поддержку инициализации, регистрации и нерегистрации модуля.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[_ATL_MODULE](atl-typedefs.md#_atl_module)

[CAtlModule](../../atl/reference/catlmodule-class.md)

`CAtlModuleT`

## <a name="requirements"></a>Требования

**Заголовок:** atlbase.h

## <a name="catlmoduletcatlmodulet"></a><a name="catlmodulet"></a>CAtlModuleT::CAtlModuleT

Конструктор.

```
CAtlModuleT() throw();
```

### <a name="remarks"></a>Remarks

Вызовы [CAtlModuleT::InitLibId](#initlibid).

## <a name="catlmoduletinitlibid"></a><a name="initlibid"></a>CAtlModuleT::InitLibId

Инициализирует член данных, содержащий GUID текущего модуля.

```
static void InitLibId() throw();
```

### <a name="remarks"></a>Remarks

Вызывается [конструктором CAtlModuleT::CAtlModuleT](#catlmodulet).

## <a name="catlmoduletregisterappid"></a><a name="registerappid"></a>CAtlModuleT::RegisterAppId

Добавляет EXE в реестр.

```
HRESULT RegisterAppId() throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK на успех, или ошибка HRESULT на отказ.

## <a name="catlmoduletregisterserver"></a><a name="registerserver"></a>CAtlModuleT::RegisterServer

Добавляет услугу в реестр.

```
HRESULT RegisterServer(
    BOOL bRegTypeLib = FALSE,
    const CLSID* pCLSID = NULL) throw();
```

### <a name="parameters"></a>Параметры

*bRegTypeLib*<br/>
TRUE, если библиотека типа должна быть зарегистрирована. Значение по умолчанию — FALSE.

*pCLSID*<br/>
Указывает на CLSID зарегистрированного объекта. Если NULL (значение по умолчанию) все объекты на карте объектов будут зарегистрированы.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK на успех, или ошибка HRESULT на отказ.

## <a name="catlmoduletunregisterappid"></a><a name="unregisterappid"></a>CAtlModuleT::UnregisterAppId

Удаляет EXE из реестра.

```
HRESULT UnregisterAppId() throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK на успех, или ошибка HRESULT на отказ.

## <a name="catlmoduletunregisterserver"></a><a name="unregisterserver"></a>CAtlModuleT::UnregisterServer

Удаляет службу из реестра.

```
HRESULT UnregisterServer(
    BOOL bUnRegTypeLib,
    const CLSID* pCLSID = NULL) throw();
```

### <a name="parameters"></a>Параметры

*bUnRegTypeLib*<br/>
ПРАВДА, если библиотека типа также должна быть незарегистрированной.

*pCLSID*<br/>
Указывает на CLSID объекта, который должен быть незарегистрированным. Если NULL (значение по умолчанию) все объекты на карте объектов будут незарегистрированы.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK на успех, или ошибка HRESULT на отказ.

## <a name="catlmoduletupdateregistryappid"></a><a name="updateregistryappid"></a>CAtlModuleT::UpdateRegistryAppId

Обновление информации EXE в реестре.

```
static HRESULT WINAPI UpdateRegistryAppId(BOOL /* bRegister*/) throw();
```

### <a name="parameters"></a>Параметры

*bРегистрация*<br/>
Зарезервировано.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK на успех, или ошибка HRESULT на отказ.

## <a name="see-also"></a>См. также раздел

[Класс CAtlModule](../../atl/reference/catlmodule-class.md)<br/>
[Общие сведения о классах](../../atl/atl-class-overview.md)<br/>
[Классы модулей](../../atl/atl-module-classes.md)
