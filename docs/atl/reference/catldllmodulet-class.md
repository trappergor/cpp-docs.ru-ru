---
title: Класс CAtlDllModuleT
ms.date: 11/04/2016
f1_keywords:
- CAtlDllModuleT
- ATLBASE/ATL::CAtlDllModuleT
- ATLBASE/ATL::CAtlDllModuleT::CAtlDllModuleT
- ATLBASE/ATL::CAtlDllModuleT::DllCanUnloadNow
- ATLBASE/ATL::CAtlDllModuleT::DllGetClassObject
- ATLBASE/ATL::CAtlDllModuleT::DllMain
- ATLBASE/ATL::CAtlDllModuleT::DllRegisterServer
- ATLBASE/ATL::CAtlDllModuleT::DllUnregisterServer
- ATLBASE/ATL::CAtlDllModuleT::GetClassObject
helpviewer_keywords:
- CAtlDllModuleT class
ms.assetid: 351d5767-8257-4878-94be-45a85e31a72d
ms.openlocfilehash: 37f57240322c6f69fe25416866cb1b356f3c9909
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50515873"
---
# <a name="catldllmodulet-class"></a>Класс CAtlDllModuleT

Этот класс представляет модуль для библиотеки DLL.

## <a name="syntax"></a>Синтаксис

```
template <class T>
class ATL_NO_VTABLE CAtlDllModuleT : public CAtlModuleT<T>
```

#### <a name="parameters"></a>Параметры

*T*<br/>
Ваш класс, производный от `CAtlDllModuleT`.

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CAtlDllModuleT::CAtlDllModuleT](#catldllmodulet)|Конструктор.|
|[CAtlDllModuleT:: ~ CAtlDllModuleT](#dtor)|Деструктор|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CAtlDllModuleT::DllCanUnloadNow](#dllcanunloadnow)|Проверяет, если библиотека DLL может быть выгружен.|
|[CAtlDllModuleT::DllGetClassObject](#dllgetclassobject)|Возвращает фабрику класса.|
|[CAtlDllModuleT::DllMain](#dllmain)|Точка входа необязательно в библиотеку динамической компоновки (DLL).|
|[CAtlDllModuleT::DllRegisterServer](#dllregisterserver)|Добавляет записи в системный реестр для объектов в библиотеке DLL.|
|[CAtlDllModuleT::DllUnregisterServer](#dllunregisterserver)|Удаляет записи системного реестра для объектов в библиотеке DLL.|
|[CAtlDllModuleT::GetClassObject](#getclassobject)|Возвращает фабрику класса. Вызывается [DllGetClassObject](#dllgetclassobject).|

## <a name="remarks"></a>Примечания

`CAtlDllModuleT` Представляет модуль для библиотеки динамической компоновки (DLL) и предоставляет функции, используемые все проекты библиотеки DLL. Такая специализация из [CAtlModuleT](../../atl/reference/catlmodulet-class.md) класс включает в себя поддержку регистрации.

Дополнительные сведения о модулях в ATL, см. в разделе [модульные классы ATL](../../atl/atl-module-classes.md).

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[_ATL_MODULE](atl-typedefs.md#_atl_module)

[CAtlModule](../../atl/reference/catlmodule-class.md)

[CAtlModuleT](../../atl/reference/catlmodulet-class.md)

`CAtlDllModuleT`

## <a name="requirements"></a>Требования

**Заголовок:** atlbase.h

##  <a name="catldllmodulet"></a>  CAtlDllModuleT::CAtlDllModuleT

Конструктор.

```
CAtlDllModuleT() throw();
```

##  <a name="dtor"></a>  CAtlDllModuleT:: ~ CAtlDllModuleT

Деструктор

```
~CAtlDllModuleT() throw();
```

##  <a name="dllcanunloadnow"></a>  CAtlDllModuleT::DllCanUnloadNow

Проверяет, если библиотека DLL может быть выгружен.

```
HRESULT DllCanUnloadNow() throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение S_OK, если библиотека DLL может быть выгружен или S_FALSE, если это невозможно.

##  <a name="dllgetclassobject"></a>  CAtlDllModuleT::DllGetClassObject

Возвращает фабрику класса.

```
HRESULT DllGetClassObject(
    REFCLSID rclsid,
    REFIID riid,
    LPVOID* ppv) throw();
```

### <a name="parameters"></a>Параметры

*rclsid*<br/>
CLSID создаваемого объекта.

*riid*<br/>
Идентификатор IID запрошенного интерфейса.

*ppv*<br/>
Указатель на указатель интерфейса, идентифицируемый *riid*. Если объект не поддерживает этот интерфейс *ppv* имеет значение NULL.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK в случае успеха или ошибки HRESULT в случае сбоя.

##  <a name="dllmain"></a>  CAtlDllModuleT::DllMain

Точка входа необязательно в библиотеку динамической компоновки (DLL).

```
BOOL WINAPI DllMain(DWORD dwReason, LPVOID /* lpReserved*/) throw();
```

### <a name="parameters"></a>Параметры

*параметр dwReason*<br/>
Если набор вызовам уведомления DLL_PROCESS_ATTACH, DLL_THREAD_ATTACH и DLL_THREAD_DETACH функции будут отключены.

*lpReserved*<br/>
Зарезервировано.

### <a name="return-value"></a>Возвращаемое значение

Всегда возвращает значение TRUE.

### <a name="remarks"></a>Примечания

Отключение DLL_THREAD_ATTACH и DLL_THREAD_DETACH уведомление, что вызовы могут быть полезная оптимизация для многопоточных приложений, имеющих множество библиотек DLL, часто, создание и удаление потоков и библиотек DLL которой не обязательно эти уведомления на уровне потока из отсоединение/вложения.

##  <a name="dllregisterserver"></a>  CAtlDllModuleT::DllRegisterServer

Добавляет записи в системный реестр для объектов в библиотеке DLL.

```
HRESULT DllRegisterServer(BOOL bRegTypeLib = TRUE) throw();
```

### <a name="parameters"></a>Параметры

*bRegTypeLib*<br/>
Значение TRUE, если для регистрации библиотеки типов. Значение по умолчанию — TRUE.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK в случае успеха или ошибки HRESULT в случае сбоя.

##  <a name="dllunregisterserver"></a>  CAtlDllModuleT::DllUnregisterServer

Удаляет записи системного реестра для объектов в библиотеке DLL.

```
HRESULT DllUnregisterServer(BOOL bUnRegTypeLib = TRUE) throw();
```

### <a name="parameters"></a>Параметры

*bUnRegTypeLib*<br/>
Значение TRUE, если библиотека типов удаляются из реестра. Значение по умолчанию — TRUE.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK в случае успеха или ошибки HRESULT в случае сбоя.

##  <a name="getclassobject"></a>  CAtlDllModuleT::GetClassObject

Создает объект для указанного идентификатора CLSID.

```
HRESULT GetClassObject(
    REFCLSID rclsid,
    REFIID riid,
    LPVOID* ppv) throw();
```

### <a name="parameters"></a>Параметры

*rclsid*<br/>
CLSID создаваемого объекта.

*riid*<br/>
Идентификатор IID запрошенного интерфейса.

*ppv*<br/>
Указатель на указатель интерфейса, идентифицируемый *riid*. Если объект не поддерживает этот интерфейс *ppv* имеет значение NULL.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK в случае успеха или ошибки HRESULT в случае сбоя.

### <a name="remarks"></a>Примечания

Этот метод вызывается [CAtlDllModuleT::DllGetClassObject](#dllgetclassobject) и включен для обеспечения обратной совместимости.

## <a name="see-also"></a>См. также

[Класс CAtlModuleT](../../atl/reference/catlmodulet-class.md)<br/>
[Класс CAtlExeModuleT](../../atl/reference/catlexemodulet-class.md)<br/>
[Общие сведения о классе](../../atl/atl-class-overview.md)<br/>
[Модульные классы](../../atl/atl-module-classes.md)
