---
title: Класс CAtlComModule
ms.date: 11/04/2016
f1_keywords:
- CAtlComModule
- ATLBASE/ATL::CAtlComModule
- ATLBASE/ATL::CAtlComModule::CAtlComModule
- ATLBASE/ATL::CAtlComModule::RegisterServer
- ATLBASE/ATL::CAtlComModule::RegisterTypeLib
- ATLBASE/ATL::CAtlComModule::UnregisterServer
- ATLBASE/ATL::CAtlComModule::UnRegisterTypeLib
helpviewer_keywords:
- CAtlComModule class
ms.assetid: af5dd71a-a0d1-4a2e-9a24-154a03381c75
ms.openlocfilehash: 09adcb33ca9e6f8524063130d6aedca044d6ecb5
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/04/2019
ms.locfileid: "57275874"
---
# <a name="catlcommodule-class"></a>Класс CAtlComModule

Этот класс реализует COM-модуля сервера.

## <a name="syntax"></a>Синтаксис

```
class CAtlComModule : public _ATL_COM_MODULE
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание:|
|----------|-----------------|
|[CAtlComModule::CAtlComModule](#catlcommodule)|Конструктор.|
|[CAtlComModule::~CAtlComModule](#dtor)|Деструктор|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание:|
|----------|-----------------|
|[CAtlComModule::RegisterServer](#registerserver)|Вызовите этот метод, чтобы обновить реестр для каждого объекта в карте объектов.|
|[CAtlComModule::RegisterTypeLib](#registertypelib)|Вызовите этот метод для регистрации библиотеки типов.|
|[CAtlComModule::UnregisterServer](#unregisterserver)|Этот метод используется для отмены регистрации каждого объекта в карте объектов.|
|[CAtlComModule::UnRegisterTypeLib](#unregistertypelib)|Этот метод используется для отмены регистрации библиотеки типов.|

## <a name="remarks"></a>Примечания

`CAtlComModule` реализует COM-модуля сервера, что позволяет клиенту получить доступ к компонентам модуля.

Этот класс заменяет устаревшее [CComModule](../../atl/reference/ccommodule-class.md) класс, используемый в более ранних версиях ATL. См. в разделе [модульные классы ATL](../../atl/atl-module-classes.md) для получения дополнительных сведений.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[_ATL_COM_MODULE](atl-typedefs.md#_atl_com_module)

`CAtlComModule`

## <a name="requirements"></a>Требования

**Заголовок:** atlbase.h

##  <a name="catlcommodule"></a>  CAtlComModule::CAtlComModule

Конструктор.

```
CAtlComModule() throw();
```

### <a name="remarks"></a>Примечания

Инициализирует модуль.

##  <a name="dtor"></a>  CAtlComModule:: ~ CAtlComModule

Деструктор

```
~CAtlComModule();
```

### <a name="remarks"></a>Примечания

Освобождает все фабрики классов.

##  <a name="registerserver"></a>  CAtlComModule::RegisterServer

Вызовите этот метод, чтобы обновить реестр для каждого объекта в карте объектов.

```
HRESULT RegisterServer(BOOL bRegTypeLib = FALSE, const CLSID* pCLSID = NULL);
```

### <a name="parameters"></a>Параметры

*bRegTypeLib*<br/>
Значение TRUE, если для регистрации библиотеки типов. Значение по умолчанию — FALSE.

*pCLSID*<br/>
Указывает идентификатор CLSID объекта для регистрации. Если значение NULL (значение по умолчанию), все объекты в карте объектов будет зарегистрировано.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK в случае успеха или ошибки HRESULT в случае сбоя.

### <a name="remarks"></a>Примечания

Вызывает функцию глобального [AtlComModuleRegisterServer](server-registration-global-functions.md#atlcommoduleregisterserver).

##  <a name="registertypelib"></a>  CAtlComModule::RegisterTypeLib

Вызовите этот метод для регистрации библиотеки типов.

```
HRESULT RegisterTypeLib(LPCTSTR lpszIndex);
HRESULT RegisterTypeLib();
```

### <a name="parameters"></a>Параметры

*lpszIndex*<br/>
Строка в формате "\\\N», где N — это целочисленный индекс ресурса библиотеки ТИПОВ.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK в случае успеха или ошибки HRESULT в случае сбоя.

### <a name="remarks"></a>Примечания

Добавляет сведения о библиотеке типов в системный реестр. Если экземпляр модуля содержит несколько библиотек типов, позволяет указать, какие библиотеки типов должны использоваться первая версия этого метода.

##  <a name="unregisterserver"></a>  CAtlComModule::UnregisterServer

Этот метод используется для отмены регистрации каждого объекта в карте объектов.

```
HRESULT UnregisterServer(
    BOOL bRegTypeLib = FALSE,
    const CLSID* pCLSID = NULL);
```

### <a name="parameters"></a>Параметры

*bRegTypeLib*<br/>
Значение TRUE, если для отмены регистрации библиотеки типов. Значение по умолчанию — FALSE.

*pCLSID*<br/>
Указывает идентификатор CLSID объекта для отмены регистрации. Если значение NULL (значение по умолчанию), все объекты в карте объектов будет отменена.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK в случае успеха или ошибки HRESULT в случае сбоя.

### <a name="remarks"></a>Примечания

Вызывает функцию глобального [AtlComModuleUnregisterServer](server-registration-global-functions.md#atlcommoduleunregisterserver).

##  <a name="unregistertypelib"></a>  CAtlComModule::UnRegisterTypeLib

Этот метод используется для отмены регистрации библиотеки типов.

```
HRESULT UnRegisterTypeLib(LPCTSTR lpszIndex);
HRESULT UnRegisterTypeLib();
```

### <a name="parameters"></a>Параметры

*lpszIndex*<br/>
Строка в формате "\\\N», где N — это целочисленный индекс ресурса библиотеки ТИПОВ.

### <a name="remarks"></a>Примечания

Удаляет сведения о библиотеке типов, из системного реестра. Если экземпляр модуля содержит несколько библиотек типов, позволяет указать, какие библиотеки типов должны использоваться первая версия этого метода.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK в случае успеха или ошибки HRESULT в случае сбоя.

## <a name="see-also"></a>См. также

[_ATL_COM_MODULE](atl-typedefs.md#_atl_com_module)<br/>
[Общие сведения о классе](../../atl/atl-class-overview.md)
