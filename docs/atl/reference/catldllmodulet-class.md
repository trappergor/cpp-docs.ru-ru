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
ms.openlocfilehash: be42915c6c2e941bc5fc1de78c5c7ac26ccca6e2
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2020
ms.locfileid: "78863222"
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
Класс, производный от `CAtlDllModuleT`.

## <a name="members"></a>Члены

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Description|
|----------|-----------------|
|[CAtlDllModuleT:: CAtlDllModuleT](#catldllmodulet)|Конструктор.|
|[CAtlDllModuleT:: ~ CAtlDllModuleT](#dtor)|Деструктор|

### <a name="public-methods"></a>Открытые методы

|Имя|Description|
|----------|-----------------|
|[CAtlDllModuleT::D Ллканунлоаднов](#dllcanunloadnow)|Проверяет, можно ли выгрузить библиотеку DLL.|
|[CAtlDllModuleT::D Ллжетклассобжект](#dllgetclassobject)|Возвращает фабрику класса.|
|[CAtlDllModuleT::D Ллмаин](#dllmain)|Необязательная точка входа в библиотеку динамической компоновки (DLL).|
|[CAtlDllModuleT::D Ллрегистерсервер](#dllregisterserver)|Добавляет записи в системный реестр для объектов в библиотеке DLL.|
|[CAtlDllModuleT::D Ллунрегистерсервер](#dllunregisterserver)|Удаляет записи в системном реестре для объектов в библиотеке DLL.|
|[CAtlDllModuleT:: Жетклассобжект](#getclassobject)|Возвращает фабрику класса. Вызывается методом [DllGetClassObject](#dllgetclassobject).|

## <a name="remarks"></a>Remarks

`CAtlDllModuleT` представляет модуль для библиотеки динамической компоновки (DLL) и предоставляет функции, используемые всеми проектами DLL. Эта специализация класса [катлмодулет](../../atl/reference/catlmodulet-class.md) включает поддержку регистрации.

Дополнительные сведения о модулях в ATL см. в разделе [Классы модулей ATL](../../atl/atl-module-classes.md).

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[_ATL_MODULE](atl-typedefs.md#_atl_module)

[катлмодуле](../../atl/reference/catlmodule-class.md)

[катлмодулет](../../atl/reference/catlmodulet-class.md)

`CAtlDllModuleT`

## <a name="requirements"></a>Требования

**Заголовок:** atlbase. h

##  <a name="catldllmodulet"></a>CAtlDllModuleT:: CAtlDllModuleT

Конструктор.

```
CAtlDllModuleT() throw();
```

##  <a name="dtor"></a>CAtlDllModuleT:: ~ CAtlDllModuleT

Деструктор

```
~CAtlDllModuleT() throw();
```

##  <a name="dllcanunloadnow"></a>CAtlDllModuleT::D Ллканунлоаднов

Проверяет, можно ли выгрузить библиотеку DLL.

```
HRESULT DllCanUnloadNow() throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK, если библиотека DLL может быть выгружена, или S_FALSE в случае невозможности.

##  <a name="dllgetclassobject"></a>CAtlDllModuleT::D Ллжетклассобжект

Возвращает фабрику класса.

```
HRESULT DllGetClassObject(
    REFCLSID rclsid,
    REFIID riid,
    LPVOID* ppv) throw();
```

### <a name="parameters"></a>Параметры

*рклсид*<br/>
Идентификатор CLSID создаваемого объекта.

*riid*<br/>
IID запрашиваемого интерфейса.

*ппв*<br/>
Указатель на указатель интерфейса, идентифицируемый *riid*. Если объект не поддерживает этот интерфейс, *ППВ* имеет значение null.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK при успешном выполнении или ошибку HRESULT при сбое.

##  <a name="dllmain"></a>CAtlDllModuleT::D Ллмаин

Необязательная точка входа в библиотеку динамической компоновки (DLL).

```
BOOL WINAPI DllMain(DWORD dwReason, LPVOID /* lpReserved*/) throw();
```

### <a name="parameters"></a>Параметры

*Параметр dwReason*<br/>
Если задано значение DLL_PROCESS_ATTACH, вызовы уведомлений DLL_THREAD_ATTACH и DLL_THREAD_DETACH отключаются.

*lpReserved*<br/>
Зарезервировано.

### <a name="return-value"></a>Возвращаемое значение

Всегда возвращает значение TRUE.

### <a name="remarks"></a>Remarks

Отключение вызовов уведомлений DLL_THREAD_ATTACH и DLL_THREAD_DETACH может быть полезной оптимизацией для многопоточных приложений, которые имеют много библиотек DLL, часто создают и удаляют потоки, а библиотеки DLL не нуждаются в таких уведомлениях на уровне потока, как вложение или отсоединение.

##  <a name="dllregisterserver"></a>CAtlDllModuleT::D Ллрегистерсервер

Добавляет записи в системный реестр для объектов в библиотеке DLL.

```
HRESULT DllRegisterServer(BOOL bRegTypeLib = TRUE) throw();
```

### <a name="parameters"></a>Параметры

*брегтипелиб*<br/>
Значение TRUE, если библиотека типов должна быть зарегистрирована. Значение по умолчанию — TRUE.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK при успешном выполнении или ошибку HRESULT при сбое.

##  <a name="dllunregisterserver"></a>CAtlDllModuleT::D Ллунрегистерсервер

Удаляет записи в системном реестре для объектов в библиотеке DLL.

```
HRESULT DllUnregisterServer(BOOL bUnRegTypeLib = TRUE) throw();
```

### <a name="parameters"></a>Параметры

*бунрегтипелиб*<br/>
Значение TRUE, если библиотека типов должна быть удалена из реестра. Значение по умолчанию — TRUE.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK при успешном выполнении или ошибку HRESULT при сбое.

##  <a name="getclassobject"></a>CAtlDllModuleT:: Жетклассобжект

Создает объект указанного идентификатора CLSID.

```
HRESULT GetClassObject(
    REFCLSID rclsid,
    REFIID riid,
    LPVOID* ppv) throw();
```

### <a name="parameters"></a>Параметры

*рклсид*<br/>
Идентификатор CLSID создаваемого объекта.

*riid*<br/>
IID запрашиваемого интерфейса.

*ппв*<br/>
Указатель на указатель интерфейса, идентифицируемый *riid*. Если объект не поддерживает этот интерфейс, *ППВ* имеет значение null.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK при успешном выполнении или ошибку HRESULT при сбое.

### <a name="remarks"></a>Remarks

Этот метод вызывается методом [CAtlDllModuleT::D ллжетклассобжект](#dllgetclassobject) и включен для обеспечения обратной совместимости.

## <a name="see-also"></a>См. также раздел

[Класс CAtlModuleT](../../atl/reference/catlmodulet-class.md)<br/>
[Класс CAtlExeModuleT](../../atl/reference/catlexemodulet-class.md)<br/>
[Обзор класса](../../atl/atl-class-overview.md)<br/>
[Классы модулей](../../atl/atl-module-classes.md)
