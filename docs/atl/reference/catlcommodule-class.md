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
ms.openlocfilehash: 68fdb48edc9304d9d74df6f36bd208cfd35ff307
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81321482"
---
# <a name="catlcommodule-class"></a>Класс CAtlComModule

Этот класс реализует модуль сервера COM.

## <a name="syntax"></a>Синтаксис

```
class CAtlComModule : public _ATL_COM_MODULE
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CAtlComModule::CAtlComModule](#catlcommodule)|Конструктор.|
|[CAtlComModule::](#dtor)|Деструктор|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CAtlComModule::RegisterServer](#registerserver)|Вызовите этот метод для обновления системного реестра для каждого объекта на карте объекта.|
|[CAtlComModule::RegisterTypeLib](#registertypelib)|Вызовите этот метод для регистрации библиотеки типов.|
|[CAtlComModule::UnregisterServer](#unregisterserver)|Вызовите этот метод, чтобы отменить регистрацию каждого объекта на карте объекта.|
|[CAtlComModule::UnRegisterTypeLib](#unregistertypelib)|Вызовите этот метод, чтобы отменить регистрацию библиотеки типов.|

## <a name="remarks"></a>Remarks

`CAtlComModule`реализует модуль сервера COM, что позволяет клиенту получить доступ к компонентам модуля.

Этот класс заменяет устаревший класс [CComModule,](../../atl/reference/ccommodule-class.md) используемый в более ранних версиях ATL. Более подробную информацию можно узнать на [примере классов atL Module.](../../atl/atl-module-classes.md)

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[_ATL_COM_MODULE](atl-typedefs.md#_atl_com_module)

`CAtlComModule`

## <a name="requirements"></a>Требования

**Заголовок:** atlbase.h

## <a name="catlcommodulecatlcommodule"></a><a name="catlcommodule"></a>CAtlComModule::CAtlComModule

Конструктор.

```
CAtlComModule() throw();
```

### <a name="remarks"></a>Remarks

Инициализирует модуль.

## <a name="catlcommodulecatlcommodule"></a><a name="dtor"></a>CAtlComModule::

Деструктор

```
~CAtlComModule();
```

### <a name="remarks"></a>Remarks

Освобождает все заводы класса.

## <a name="catlcommoduleregisterserver"></a><a name="registerserver"></a>CAtlComModule::RegisterServer

Вызовите этот метод для обновления системного реестра для каждого объекта на карте объекта.

```
HRESULT RegisterServer(BOOL bRegTypeLib = FALSE, const CLSID* pCLSID = NULL);
```

### <a name="parameters"></a>Параметры

*bRegTypeLib*<br/>
TRUE, если библиотека типа должна быть зарегистрирована. Значение по умолчанию — FALSE.

*pCLSID*<br/>
Указывает на CLSID зарегистрированного объекта. Если NULL (значение по умолчанию) все объекты на карте объектов будут зарегистрированы.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK на успех, или ошибка HRESULT на отказ.

### <a name="remarks"></a>Remarks

Вызывает глобальную функцию [AtlComModuleRegisterServer](server-registration-global-functions.md#atlcommoduleregisterserver).

## <a name="catlcommoduleregistertypelib"></a><a name="registertypelib"></a>CAtlComModule::RegisterTypeLib

Вызовите этот метод для регистрации библиотеки типов.

```
HRESULT RegisterTypeLib(LPCTSTR lpszIndex);
HRESULT RegisterTypeLib();
```

### <a name="parameters"></a>Параметры

*lpszИндекс*<br/>
Строка в\\формате "N", где N является инкемгерным индексом ресурса TYPELIB.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK на успех, или ошибка HRESULT на отказ.

### <a name="remarks"></a>Remarks

Добавляет информацию о библиотеке типа в системный реестр. Если экземпляр модуля содержит несколько библиотек типов, используйте первую версию этого метода, чтобы указать, какой тип библиотеки следует использовать.

## <a name="catlcommoduleunregisterserver"></a><a name="unregisterserver"></a>CAtlComModule::UnregisterServer

Вызовите этот метод, чтобы отменить регистрацию каждого объекта на карте объекта.

```
HRESULT UnregisterServer(
    BOOL bRegTypeLib = FALSE,
    const CLSID* pCLSID = NULL);
```

### <a name="parameters"></a>Параметры

*bRegTypeLib*<br/>
ПРАВДА, если библиотека типа должна быть незарегистрированной. Значение по умолчанию — FALSE.

*pCLSID*<br/>
Указывает на CLSID объекта, который должен быть незарегистрированным. Если NULL (значение по умолчанию) все объекты на карте объектов будут незарегистрированы.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK на успех, или ошибка HRESULT на отказ.

### <a name="remarks"></a>Remarks

Вызывает глобальную функцию [AtlComModuleUnregisterServer](server-registration-global-functions.md#atlcommoduleunregisterserver).

## <a name="catlcommoduleunregistertypelib"></a><a name="unregistertypelib"></a>CAtlComModule::UnRegisterTypeLib

Вызовите этот метод, чтобы отменить регистрацию библиотеки типов.

```
HRESULT UnRegisterTypeLib(LPCTSTR lpszIndex);
HRESULT UnRegisterTypeLib();
```

### <a name="parameters"></a>Параметры

*lpszИндекс*<br/>
Строка в\\формате "N", где N является инкемгерным индексом ресурса TYPELIB.

### <a name="remarks"></a>Remarks

Удаляет информацию о библиотеке типа из системного реестра. Если экземпляр модуля содержит несколько библиотек типов, используйте первую версию этого метода, чтобы указать, какой тип библиотеки следует использовать.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK на успех, или ошибка HRESULT на отказ.

## <a name="see-also"></a>См. также раздел

[_ATL_COM_MODULE](atl-typedefs.md#_atl_com_module)<br/>
[Общие сведения о классах](../../atl/atl-class-overview.md)
