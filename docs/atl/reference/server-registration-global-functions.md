---
title: Глобальные функции регистрации серверов | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- atlbase/ATL::AtlComModuleRegisterServer
- atlbase/ATL::AtlComModuleUnregisterServer
- atlbase/ATL::AtlComModuleRegisterClassObjects
- atlbase/ATL::AtlComModuleRevokeClassObjects
- atlbase/ATL::AtlComModuleGetClassObject
dev_langs:
- C++
ms.assetid: c2f0a35d-857c-4538-a44d-c4ea0db63b06
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c8a2935d5b1c32298215b0ebfcf7382dafd259b3
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/25/2018
ms.locfileid: "50052945"
---
# <a name="server-registration-global-functions"></a>Глобальные функции регистрации серверов

Эти функции обеспечивают поддержку для регистрации и отмены регистрации серверных объектов в карте объектов.

> [!IMPORTANT]
>  Функции, перечисленные в следующей таблице, не может использоваться в приложениях, выполняемых в среде выполнения Windows.

|||
|-|-|
|[AtlComModuleRegisterServer](#atlcommoduleregisterserver)|Эта функция вызывается для регистрации каждого из объектов в карте объектов.|
|[AtlComModuleUnregisterServer](#atlcommoduleunregisterserver)|Эта функция вызывается для отмены регистрации каждого из объектов в карте объектов.|
|[AtlComModuleRegisterClassObjects](#atlcommoduleregisterclassobjects)|Эта функция вызывается для регистрации объектов класса.|
|[AtlComModuleRevokeClassObjects](#atlcommodulerevokeclassobjects)|Эта функция вызывается для отмены объектов классов из COM-модуля.|
|[AtlComModuleGetClassObject](#atlcommodulegetclassobject)|Эта функция вызывается для получения объекта класса.|

## <a name="requirements"></a>Требования

**Заголовок:** atlbase.h

##  <a name="atlcommoduleregisterserver"></a>  AtlComModuleRegisterServer

Эта функция вызывается для регистрации каждого из объектов в карте объектов.

```
ATLINLINE ATLAPI AtlComModuleRegisterServer(
    _ATL_COM_MODULE* pComModule,
    BOOL bRegTypeLib,
    const CLSID* pCLSID);
```

### <a name="parameters"></a>Параметры

*pComModule*<br/>
Указатель на COM-модуля.

*bRegTypeLib*<br/>
Значение TRUE, если для регистрации библиотеки типов.

*pCLSID*<br/>
Указывает идентификатор CLSID объекта для регистрации. Если значение равно NULL, будет зарегистрировано всех объектов в карте объектов.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK в случае успеха или ошибки HRESULT в случае сбоя.

### <a name="remarks"></a>Примечания

`AtlComModuleRegisterServer` проверяет карте автоматически созданных объектов ATL и регистрирует каждый объект в сопоставлении. Если *pCLSID* не NULL, то только объект, на который ссылается *pCLSID* зарегистрирован; в противном случае все объекты зарегистрированы.

Эта функция вызывается [CAtlComModule::RegisterServer](catlcommodule-class.md#registerserver).

##  <a name="atlcommoduleunregisterserver"></a>  AtlComModuleUnregisterServer

Эта функция вызывается для отмены регистрации каждого из объектов в карте объектов.

```
ATLINLINE ATLAPI AtlComModuleUnregisterServer(
    _ATL_COM_MODULE* pComModule,
    BOOL bUnRegTypeLib,
    const CLSID* pCLSID);
```

### <a name="parameters"></a>Параметры

*pComModule*<br/>
Указатель на COM-модуля.

*bUnRegTypeLib*<br/>
Значение TRUE, если для регистрации библиотеки типов.

*pCLSID*<br/>
Указывает идентификатор CLSID объекта для отмены регистрации. Если значение равно NULL всех объектов в карте объектов будет отменена.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK в случае успеха или ошибки HRESULT в случае сбоя.

### <a name="remarks"></a>Примечания

`AtlComModuleUnregisterServer` проверяет карте объектов ATL и отменяет регистрацию каждого объекта в схеме. Если *pCLSID* не NULL, то только объект, на который ссылается *pCLSID* регистрация которой удалена; в противном случае все объекты, не зарегистрированы.

Эта функция вызывается [CAtlComModule::UnregisterServer](catlcommodule-class.md#unregisterserver).

##  <a name="atlcommoduleregisterclassobjects"></a>  AtlComModuleRegisterClassObjects

Эта функция вызывается для регистрации объектов класса.

```
ATLINLINE ATLAPI AtlComModuleRegisterClassObjects(
    _ATL_COM_MODULE* pComModule,
    DWORD dwClsContext,
    DWORD dwFlags);
```

### <a name="parameters"></a>Параметры

*pComModule*<br/>
Указатель на COM-модуля.

*dwClsContext*<br/>
Определяет контекст, в котором будет выполняться объект класса. Возможные значения: CLSCTX_INPROC_SERVER, CLSCTX_INPROC_HANDLER или CLSCTX_LOCAL_SERVER. См. в разделе [CLSCTX](/windows/desktop/api/wtypesbase/ne-wtypesbase-tagclsctx) для получения дополнительных сведений.

*dwFlags*<br/>
Определяет типы подключения к объекту класса. Возможные значения: REGCLS_SINGLEUSE, REGCLS_MULTIPLEUSE или REGCLS_MULTI_SEPARATE. См. в разделе [REGCLS](/windows/desktop/api/combaseapi/ne-combaseapi-tagregcls) для получения дополнительных сведений.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK в случае успеха или ошибки HRESULT в случае сбоя.

### <a name="remarks"></a>Примечания

Эта вспомогательная функция используемой [CComModule::RegisterClassObjects](ccommodule-class.md#registerclassobjects) (устаревший в ATL 7.0) и [CAtlExeModuleT::RegisterClassObjects](catlexemodulet-class.md#registerclassobjects).

##  <a name="atlcommodulerevokeclassobjects"></a>  AtlComModuleRevokeClassObjects

Эта функция вызывается для удаления фабрики или фабрик класса из таблицы запущенных объектов.

```
ATLINLINE ATLAPI AtlComModuleRevokeClassObjects(_ATL_COM_MODULE* pComModule);
```

### <a name="parameters"></a>Параметры

*pComModule*<br/>
Указатель на COM-модуля.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK в случае успеха или ошибки HRESULT в случае сбоя.

### <a name="remarks"></a>Примечания

Эта вспомогательная функция используемой [CComModule::RevokeClassObjects](ccommodule-class.md#revokeclassobjects) (устаревший в ATL 7.0) и [CAtlExeModuleT::RevokeClassObjects](catlexemodulet-class.md#revokeclassobjects).

##  <a name="atlcommodulegetclassobject"></a>  AtlComModuleGetClassObject

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
Указатель на COM-модуля.

*rclsid*<br/>
CLSID создаваемого объекта.

*riid*<br/>
Идентификатор IID запрошенного интерфейса.

*ppv*<br/>
Указатель на указатель интерфейса, идентифицируемый *riid*. Если объект не поддерживает этот интерфейс *ppv* имеет значение NULL.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK в случае успеха или ошибки HRESULT в случае сбоя.

### <a name="remarks"></a>Примечания

Эта вспомогательная функция используемой [CComModule::GetClassObject](ccommodule-class.md#getclassobject) (устаревший в ATL 7.0) и [CAtlDllModuleT::GetClassObject](catldllmodulet-class.md#getclassobject).

## <a name="see-also"></a>См. также

[Функции](../../atl/reference/atl-functions.md)
