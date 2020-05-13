---
title: Глобальные функции регистрации серверов
ms.date: 11/04/2016
f1_keywords:
- atlbase/ATL::AtlComModuleRegisterServer
- atlbase/ATL::AtlComModuleUnregisterServer
- atlbase/ATL::AtlComModuleRegisterClassObjects
- atlbase/ATL::AtlComModuleRevokeClassObjects
- atlbase/ATL::AtlComModuleGetClassObject
ms.assetid: c2f0a35d-857c-4538-a44d-c4ea0db63b06
ms.openlocfilehash: fb6353b52f487d0511c54223fe9e31dab88704b2
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81325928"
---
# <a name="server-registration-global-functions"></a>Глобальные функции регистрации серверов

Эти функции обеспечивают поддержку регистрации и нерегистрации объектов сервера на карте объектов.

> [!IMPORTANT]
> Функции, перечисленные в следующей таблице, не могут использоваться в приложениях, выполняемых в Windows Runtime.

|||
|-|-|
|[AtlComModuleRegisterServer](#atlcommoduleregisterserver)|Эта функция вызывается для регистрации каждого из объектов в карте объектов.|
|[AtlComModuleUnregisterServer](#atlcommoduleunregisterserver)|Эта функция вызывается для отмены регистрации каждого из объектов в карте объектов.|
|[AtlComModuleRegisterClassObjects](#atlcommoduleregisterclassobjects)|Эта функция вызывается для регистрации объектов класса.|
|[AtlComModuleRevokeClassObjects](#atlcommodulerevokeclassobjects)|Эта функция призвана отменить объекты класса из модуля COM.|
|[AtlComModuleGetClassObject](#atlcommodulegetclassobject)|Эта функция называется для получения объекта класса.|

## <a name="requirements"></a>Требования

**Заголовок:** atlbase.h

## <a name="atlcommoduleregisterserver"></a><a name="atlcommoduleregisterserver"></a>AtlComModuleRegisterServer

Эта функция вызывается для регистрации каждого из объектов в карте объектов.

```
ATLINLINE ATLAPI AtlComModuleRegisterServer(
    _ATL_COM_MODULE* pComModule,
    BOOL bRegTypeLib,
    const CLSID* pCLSID);
```

### <a name="parameters"></a>Параметры

*pComModule*<br/>
Указатель на модуль COM.

*bRegTypeLib*<br/>
TRUE, если библиотека типа должна быть зарегистрирована.

*pCLSID*<br/>
Указывает на CLSID зарегистрированного объекта. Если NULL, все объекты на карте объектов будут зарегистрированы.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK на успех, или ошибка HRESULT на отказ.

### <a name="remarks"></a>Remarks

`AtlComModuleRegisterServer`ходит по карте объектов ATL и регистрирует каждый объект на карте. Если *pCLSID* не является NULL, то регистрируется только объект, на который ссылается *pCLSID;* в противном случае все объекты зарегистрированы.

Эта функция называется [CAtlComModule::RegisterServer](catlcommodule-class.md#registerserver).

## <a name="atlcommoduleunregisterserver"></a><a name="atlcommoduleunregisterserver"></a>AtlComModuleUnregisterServer

Эта функция вызывается для отмены регистрации каждого из объектов в карте объектов.

```
ATLINLINE ATLAPI AtlComModuleUnregisterServer(
    _ATL_COM_MODULE* pComModule,
    BOOL bUnRegTypeLib,
    const CLSID* pCLSID);
```

### <a name="parameters"></a>Параметры

*pComModule*<br/>
Указатель на модуль COM.

*bUnRegTypeLib*<br/>
TRUE, если библиотека типа должна быть зарегистрирована.

*pCLSID*<br/>
Указывает на CLSID объекта, который должен быть незарегистрированным. Если NULL все объекты на карте объектов будут незарегистрированы.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK на успех, или ошибка HRESULT на отказ.

### <a name="remarks"></a>Remarks

`AtlComModuleUnregisterServer`ходит по карте объектов ATL и отменяет регистрацию каждого объекта на карте. Если *pCLSID* не является NULL, то только объект, на который ссылается *pCLSID,* не зарегистрирован; в противном случае все объекты не зарегистрированы.

Эта функция называется [CAtlComModule::UnregisterServer](catlcommodule-class.md#unregisterserver).

## <a name="atlcommoduleregisterclassobjects"></a><a name="atlcommoduleregisterclassobjects"></a>AtlComModuleRegisterClassObjects

Эта функция вызывается для регистрации объектов класса.

```
ATLINLINE ATLAPI AtlComModuleRegisterClassObjects(
    _ATL_COM_MODULE* pComModule,
    DWORD dwClsContext,
    DWORD dwFlags);
```

### <a name="parameters"></a>Параметры

*pComModule*<br/>
Указатель на модуль COM.

*dwClsКонтекст*<br/>
Определяет контекст, в котором должен быть запущен объект класса. Возможные значения : CLSCTX_INPROC_SERVER, CLSCTX_INPROC_HANDLER или CLSCTX_LOCAL_SERVER. Более подробную информацию можно узнать из [CLSCTX.](/windows/win32/api/wtypesbase/ne-wtypesbase-clsctx)

*dwFlags*<br/>
Определяет типы соединения с объектом класса. Возможные значения — REGCLS_SINGLEUSE, REGCLS_MULTIPLEUSE или REGCLS_MULTI_SEPARATE. Более подробную информацию можно узнать на [примере REGCLS.](/windows/win32/api/combaseapi/ne-combaseapi-regcls)

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK на успех, или ошибка HRESULT на отказ.

### <a name="remarks"></a>Remarks

Эта функция помощника используется [CComModule::RegisterClassObjects](ccommodule-class.md#registerclassobjects) (устаревшие в ATL 7.0) и [CAtlExeModuleT::RegisterClassObjects](catlexemodulet-class.md#registerclassobjects).

## <a name="atlcommodulerevokeclassobjects"></a><a name="atlcommodulerevokeclassobjects"></a>AtlComModuleRevokeClassObjects

Эта функция вызывается для удаления фабрики или фабрик класса из таблицы запущенных объектов.

```
ATLINLINE ATLAPI AtlComModuleRevokeClassObjects(_ATL_COM_MODULE* pComModule);
```

### <a name="parameters"></a>Параметры

*pComModule*<br/>
Указатель на модуль COM.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK на успех, или ошибка HRESULT на отказ.

### <a name="remarks"></a>Remarks

Эта функция помощника используется [CComModule::RevokeClassObjects](ccommodule-class.md#revokeclassobjects) (устаревшие в ATL 7.0) и [CAtlExeModuleT::RevokeClassObjects](catlexemodulet-class.md#revokeclassobjects).

## <a name="atlcommodulegetclassobject"></a><a name="atlcommodulegetclassobject"></a>AtlComModuleGetClassObject

Эта функция вызывается для получения фабрики класса.

```
ATLINLINE ATLAPI AtlComModuleGetClassObject(
    _ATL_COM_MODULE* pComModule,
    REFCLSID rclsid,
    REFIID riid,
    LPVOID* ppv);
```

### <a name="parameters"></a>Параметры

*pComModule*<br/>
Указатель на модуль COM.

*rclsid*<br/>
CLSID объекта, который будет создан.

*riid*<br/>
IID запрашиваемого интерфейса.

*Ppv*<br/>
Указатель на указатель интерфейса, идентифицированный *riid*. Если объект не поддерживает этот интерфейс, *ppv* настроен на NULL.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK на успех, или ошибка HRESULT на отказ.

### <a name="remarks"></a>Remarks

Эта функция помощника используется [CComModule::GetClassObject](ccommodule-class.md#getclassobject) (устаревший в ATL 7.0) и [CAtlDllModuleT::GetClassObject](catldllmodulet-class.md#getclassobject).

## <a name="see-also"></a>См. также раздел

[Функции](../../atl/reference/atl-functions.md)
