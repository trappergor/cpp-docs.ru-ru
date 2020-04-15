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
ms.openlocfilehash: 7a5f8e7e489c8e0d573569ac7c4a8fb63f652732
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81319013"
---
# <a name="catldllmodulet-class"></a>Класс CAtlDllModuleT

Этот класс представляет модуль для DLL.

## <a name="syntax"></a>Синтаксис

```
template <class T>
class ATL_NO_VTABLE CAtlDllModuleT : public CAtlModuleT<T>
```

#### <a name="parameters"></a>Параметры

*T*<br/>
Ваш класс происходит `CAtlDllModuleT`от .

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CAtlDllModuleT::CAtlDllModuleT](#catldllmodulet)|Конструктор.|
|[CAtlDllModuleT::](#dtor)|Деструктор|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CAtlDllModuleT::DllCanUnloadNow](#dllcanunloadnow)|Тесты, если DLL может быть выгружен.|
|[CAtlDllModuleT::DllgetClassObject](#dllgetclassobject)|Возвращает фабрику класса.|
|[CAtlDllModuleT::DllMain](#dllmain)|Дополнительная точка входа в библиотеку динамических ссылк (DLL).|
|[CAtlDllModuleT::DllRegisterServer](#dllregisterserver)|Добавляет записи в системный реестр объектов в DLL.|
|[CAtlDllModuleT::DllUnregisterServer](#dllunregisterserver)|Удаляет записи в системном реестре объектов в DLL.|
|[CAtlDllModuleT::GetClassObject](#getclassobject)|Возвращает фабрику класса. Вызывается [DllGetClassObject](#dllgetclassobject).|

## <a name="remarks"></a>Remarks

`CAtlDllModuleT`представляет модуль для библиотеки динамических ссылок (DLL) и предоставляет функции, используемые всеми проектами DLL. Эта специализация класса [CAtlModuleT](../../atl/reference/catlmodulet-class.md) включает в себя поддержку регистрации.

Для получения дополнительной информации о модулях в ATL, [см.](../../atl/atl-module-classes.md)

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[_ATL_MODULE](atl-typedefs.md#_atl_module)

[CAtlModule](../../atl/reference/catlmodule-class.md)

[CAtlModuleT](../../atl/reference/catlmodulet-class.md)

`CAtlDllModuleT`

## <a name="requirements"></a>Требования

**Заголовок:** atlbase.h

## <a name="catldllmoduletcatldllmodulet"></a><a name="catldllmodulet"></a>CAtlDllModuleT::CAtlDllModuleT

Конструктор.

```
CAtlDllModuleT() throw();
```

## <a name="catldllmoduletcatldllmodulet"></a><a name="dtor"></a>CAtlDllModuleT::

Деструктор

```
~CAtlDllModuleT() throw();
```

## <a name="catldllmoduletdllcanunloadnow"></a><a name="dllcanunloadnow"></a>CAtlDllModuleT::DllCanUnloadNow

Тесты, если DLL может быть выгружен.

```
HRESULT DllCanUnloadNow() throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK, если DLL может быть выгружен, или S_FALSE, если он не может.

## <a name="catldllmoduletdllgetclassobject"></a><a name="dllgetclassobject"></a>CAtlDllModuleT::DllgetClassObject

Возвращает фабрику класса.

```
HRESULT DllGetClassObject(
    REFCLSID rclsid,
    REFIID riid,
    LPVOID* ppv) throw();
```

### <a name="parameters"></a>Параметры

*rclsid*<br/>
CLSID объекта, который будет создан.

*riid*<br/>
IID запрашиваемого интерфейса.

*Ppv*<br/>
Указатель на указатель интерфейса, идентифицированный *riid*. Если объект не поддерживает этот интерфейс, *ppv* настроен на NULL.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK на успех, или ошибка HRESULT на отказ.

## <a name="catldllmoduletdllmain"></a><a name="dllmain"></a>CAtlDllModuleT::DllMain

Дополнительная точка входа в библиотеку динамических ссылк (DLL).

```
BOOL WINAPI DllMain(DWORD dwReason, LPVOID /* lpReserved*/) throw();
```

### <a name="parameters"></a>Параметры

*dwReason*<br/>
При установке на DLL_PROCESS_ATTACH вызовы DLL_THREAD_ATTACH и уведомления DLL_THREAD_DETACH отключены.

*lpReserved*<br/>
Зарезервировано.

### <a name="return-value"></a>Возвращаемое значение

Всегда возвращается TRUE.

### <a name="remarks"></a>Remarks

Отключение DLL_THREAD_ATTACH и DLL_THREAD_DETACH вызовов уведомлений может быть полезной оптимизацией для многопоточных приложений, которые имеют много DLL, которые часто создают и удаляют потоки, и чьи DLL не нуждаются в этих уведомлениях уровня потока о вложения/отслоении.

## <a name="catldllmoduletdllregisterserver"></a><a name="dllregisterserver"></a>CAtlDllModuleT::DllRegisterServer

Добавляет записи в системный реестр объектов в DLL.

```
HRESULT DllRegisterServer(BOOL bRegTypeLib = TRUE) throw();
```

### <a name="parameters"></a>Параметры

*bRegTypeLib*<br/>
TRUE, если библиотека типа должна быть зарегистрирована. Значение по умолчанию — TRUE.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK на успех, или ошибка HRESULT на отказ.

## <a name="catldllmoduletdllunregisterserver"></a><a name="dllunregisterserver"></a>CAtlDllModuleT::DllUnregisterServer

Удаляет записи в системном реестре объектов в DLL.

```
HRESULT DllUnregisterServer(BOOL bUnRegTypeLib = TRUE) throw();
```

### <a name="parameters"></a>Параметры

*bUnRegTypeLib*<br/>
ПРАВДА, если библиотека типа должна быть удалена из реестра. Значение по умолчанию — TRUE.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK на успех, или ошибка HRESULT на отказ.

## <a name="catldllmoduletgetclassobject"></a><a name="getclassobject"></a>CAtlDllModuleT::GetClassObject

Создает объект указанного CLSID.

```
HRESULT GetClassObject(
    REFCLSID rclsid,
    REFIID riid,
    LPVOID* ppv) throw();
```

### <a name="parameters"></a>Параметры

*rclsid*<br/>
CLSID объекта, который будет создан.

*riid*<br/>
IID запрашиваемого интерфейса.

*Ppv*<br/>
Указатель на указатель интерфейса, идентифицированный *riid*. Если объект не поддерживает этот интерфейс, *ppv* настроен на NULL.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK на успех, или ошибка HRESULT на отказ.

### <a name="remarks"></a>Remarks

Этот метод называется [CAtlDllModuleT: :DllGetClassObject](#dllgetclassobject) и включен для обратной совместимости.

## <a name="see-also"></a>См. также раздел

[Класс CAtlModuleT](../../atl/reference/catlmodulet-class.md)<br/>
[Класс CAtlExeModuleT](../../atl/reference/catlexemodulet-class.md)<br/>
[Общие сведения о классах](../../atl/atl-class-overview.md)<br/>
[Классы модулей](../../atl/atl-module-classes.md)
