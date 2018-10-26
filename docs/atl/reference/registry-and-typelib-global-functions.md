---
title: Глобальные функции реестра и библиотеки типов | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- atlbase/ATL::AtlGetPerUserRegistration
- afxpriv/ATL::AfxRegCreateKey
- afxpriv/ATL::AfxRegDeleteKey
- atlbase/ATL::AtlRegisterTypeLib
- afxpriv/ATL::AfxRegOpenKey
- afxpriv/ATL::AfxRegOpenKeyEx
- afxdisp/ATL::AfxUnregisterPreviewHandler
- atlbase/ATL::AtlSetPerUserRegistration
- atlbase/ATL::AtlUnRegisterTypeLib
- atlbase/ATL::AtlLoadTypeLib
- atlbase/ATL::AtlUpdateRegistryFromResourceD
- atlbase/ATL::RegistryDataExchange
dev_langs:
- C++
helpviewer_keywords:
- RegistryDataExchange function, global functions
ms.assetid: d58b8a4e-975c-4417-8b34-d3c847f679b3
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: af2780c8b7fb332cd739416e5051a57a8bc7f765
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/25/2018
ms.locfileid: "50073543"
---
# <a name="registry-and-typelib-global-functions"></a>Глобальные функции реестра и библиотеки типов

Эти функции обеспечивают поддержку для загрузки и регистрации библиотеки типов.

> [!IMPORTANT]
>  Функции, перечисленные в следующих таблицах не может использоваться в приложениях, выполняемых в среде выполнения Windows.

|||
|-|-|
|[AfxRegCreateKey](#afxrefcreatekey)|Создает указанный раздел реестра.|
|[AfxRegDeleteKey](#afxrefdeletekey)|Удаляет указанный раздел реестра.|
|[AfxRegisterPreviewHandler](#afxregisterpreviewhandler)|Вспомогательный класс для регистрации обработчика просмотра.|
|[AfxUnregisterPreviewHandler](#afxunregisterpreviewhandler)| Вспомогательный класс для отмены регистрации обработчика просмотра. |
|[AtlRegisterTypeLib](#atlregistertypelib)|Эта функция вызывается для регистрации библиотеки типов.|
|[AtlUnRegisterTypeLib](#atlunregistertypelib)|Эта функция вызывается для отмены регистрации библиотеки типов|
|[AfxRegOpenKey](#afxregopenkey)|Открывает указанный раздел реестра.|
|[AfxRegOpenKeyEx](#afxregopenkeyex)|Открывает указанный раздел реестра.|
|[AtlLoadTypeLib](#atlloadtypelib)|Эта функция вызывается для загрузки библиотеки типов.|
|[AtlUpdateRegistryFromResourceD](#atlupdateregistryfromresourced)|Эта функция вызывается для обновления реестра из предоставленного ресурса.|
|[RegistryDataExchange](#registrydataexchange)|Эта функция вызывается для чтения из системного реестра или записи в него. Вызывается средой [макросы обмена данными реестра](../../atl/reference/registry-data-exchange-macros.md).|

Эти функции управления, какой из узлов в реестре, программа использует для хранения информации.

|||
|-|-|
|[AtlGetPerUserRegistration](#atlgetperuserregistration)|Извлекает, перенаправляет ли приложение доступ к реестру **HKEY_CURRENT_USER** ( **HKCU**) узла.|
|[AtlSetPerUserRegistration](#atlsetperuserregistration)|Задает, перенаправляет ли приложение доступ к реестру **HKEY_CURRENT_USER** ( **HKCU**) узла.|

### <a name="requirements"></a>Требования

**Заголовок:** atlbase.h

## <a name="atlgetperuserregistration"></a> AtlGetPerUserRegistration

Эта функция используется для определения, перенаправляет ли приложение доступ к реестру **HKEY_CURRENT_USER** (**HKCU**) узла.

### <a name="syntax"></a>Синтаксис

```
ATLINLINE ATLAPI AtlGetPerUserRegistration(bool* pEnabled);
```

### <a name="parameters"></a>Параметры

*pEnabled*<br/>
[out] Значение TRUE указывает, что данные реестра направляется **HKCU** узла; Значение FALSE указывает, что приложение записывает данные реестра в узел по умолчанию. Узел по умолчанию является **HKEY_CLASSES_ROOT** (**HKCR**).

### <a name="return-value"></a>Возвращаемое значение

Значение S_OK, если метод выполнен успешно, в противном случае — значение HRESULT ошибки кода при возникновении ошибки.

### <a name="remarks"></a>Примечания

Перенаправление системного реестра не включена по умолчанию. Если этот параметр включен, доступ к реестру перенаправляется на **HKEY_CURRENT_USER\Software\Classes**.

Перенаправление не является общим. Только платформы MFC и ATL затрагивает это перенаправление системного реестра.

### <a name="requirements"></a>Требования

**Заголовок:** atlbase.h

## <a name="afxregcreatekey"></a> AfxRegCreateKey

Создает указанный раздел реестра.

### <a name="syntax"></a>Синтаксис

```
LONG AFXAPI AfxRegCreateKey(HKEY hKey, LPCTSTR lpSubKey, PHKEY phkResult, CAtlTransactionManager* pTM = NULL);
```

### <a name="parameters"></a>Параметры

*открываемый раздел hKey*<br/>
Дескриптор, чтобы открыть раздел реестра.

*lpSubKey*<br/>
Имя ключа, который открывает эту функцию, или создает.

*phkResult*<br/>
Указатель на переменную, которая получает дескриптор открыт или созданный ключ.

*pTM*<br/>
Указатель на `CAtlTransactionManager` объект.

### <a name="return-value"></a>Возвращаемое значение

Если функция выполняется успешно, возвращаемое значение равно ERROR_SUCCESS. Если функция завершается с ошибкой, возвращается код ненулевого значения ошибки, определенный в Winerror.h.

### <a name="requirements"></a>Требования

**Заголовок:** afxpriv.h

## <a name="afxregdeletekey"></a> AfxRegDeleteKey

Удаляет указанный раздел реестра.

### <a name="syntax"></a>Синтаксис

```
LONG AFXAPI AfxRegDeleteKey(HKEY hKey, LPCTSTR lpSubKey, CAtlTransactionManager* pTM = NULL);
```

### <a name="parameters"></a>Параметры

*открываемый раздел hKey*<br/>
Дескриптор, чтобы открыть раздел реестра.

*lpSubKey*<br/>
Имя ключа для удаления.

*pTM*<br/>
Указатель на `CAtlTransactionManager` объект.

### <a name="return-value"></a>Возвращаемое значение

Если функция выполняется успешно, возвращаемое значение равно ERROR_SUCCESS. Если функция завершается с ошибкой, возвращается код ненулевого значения ошибки, определенный в Winerror.h.

### <a name="requirements"></a>Требования

**Заголовок:** afxpriv.h

## <a name="afxregisterpreviewhandler"></a>

Вспомогательный класс для регистрации обработчика просмотра.

### <a name="syntax"></a>Синтаксис

```
BOOL AFXAPI AfxRegisterPreviewHandler(LPCTSTR lpszCLSID, LPCTSTR lpszShortTypeName, LPCTSTR lpszFilterExt);
```

### <a name="parameters"></a>Параметры

*lpszCLSID*<br/>
Указывает CLSID обработчика.

*lpszShortTypeName*<br/>
Указывает идентификатор ProgID для обработчика.

*lpszFilterExt*<br/>
Указывает расширение файла, зарегистрированные с данным обработчиком.

### <a name="requirements"></a>Требования

**Заголовок:** afxdisp.h

##  <a name="atlregistertypelib"></a>  AtlRegisterTypeLib

Эта функция вызывается для регистрации библиотеки типов.

```
ATLAPI AtlRegisterTypeLib(HINSTANCE hInstTypeLib, LPCOLESTR lpszIndex);
```

### <a name="parameters"></a>Параметры

*hInstTypeLib*<br/>
Дескриптор экземпляра модуля.

*lpszIndex*<br/>
Строка в формате "\\\N», где N — это целочисленный индекс ресурса библиотеки типов. Может иметь значение NULL, если индекс не является обязательным.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK в случае успеха или ошибки HRESULT в случае сбоя.

### <a name="remarks"></a>Примечания

Эта вспомогательная функция используемой [AtlComModuleUnregisterServer](server-registration-global-functions.md#atlcommoduleunregisterserver) и [CAtlComModule::RegisterTypeLib](../../atl/reference/catlcommodule-class.md#registertypelib).

### <a name="requirements"></a>Требования

**Заголовок:** atlbase.h

## <a name="afxregopenkey"></a> AfxRegOpenKey

Открывает указанный раздел реестра.

### <a name="syntax"></a>Синтаксис

```
LONG AFXAPI AfxRegOpenKey(HKEY hKey, LPCTSTR lpSubKey, PHKEY phkResult, CAtlTransactionManager* pTM = NULL);
```

### <a name="parameters"></a>Параметры

*открываемый раздел hKey*<br/>
Дескриптор, чтобы открыть раздел реестра.

*lpSubKey*<br/>
Имя ключа, который открывает эту функцию, или создает.

*phkResult*<br/>
Указатель на переменную, которая получает дескриптор созданный ключ.

*pTM*<br/>
Указатель на `CAtlTransactionManager` объект.

### <a name="return-value"></a>Возвращаемое значение

Если функция выполняется успешно, возвращаемое значение равно ERROR_SUCCESS. Если функция завершается с ошибкой, возвращается код ненулевого значения ошибки, определенный в Winerror.h.

### <a name="requirements"></a>Требования

**Заголовок:** afxpriv.h

## <a name="afxregopenkeyex"></a>  AfxRegOpenKeyEx

Открывает указанный раздел реестра.

### <a name="syntax"></a>Синтаксис

```
LONG AFXAPI AfxRegOpenKeyEx(HKEY hKey, LPCTSTR lpSubKey, DWORD ulOptions, REGSAM samDesired, PHKEY phkResult, CAtlTransactionManager* pTM = NULL);
```

### <a name="parameters"></a>Параметры

*открываемый раздел hKey*<br/>
Дескриптор, чтобы открыть раздел реестра.

*lpSubKey*<br/>
Имя ключа, который открывает эту функцию, или создает.

*ulOptions*<br/>
Этот параметр зарезервирован и должен быть равен нулю.

*samDesired*<br/>
Маска, которая определяет требуемые права доступа к ключу.

*phkResult*<br/>
Указатель на переменную, которая получает дескриптор открытого ключа.

*pTM*<br/>
Указатель на `CAtlTransactionManager` объект.

### <a name="return-value"></a>Возвращаемое значение

Если функция выполняется успешно, возвращаемое значение равно ERROR_SUCCESS. Если функция завершается с ошибкой, возвращается код ненулевого значения ошибки, определенный в Winerror.h.

### <a name="requirements"></a>Требования

**Заголовок:** afxpriv.h

## <a name="afxunregisterpreviewhandler"></a> AfxUnregisterPreviewHandler

Вспомогательный класс для отмены регистрации обработчика просмотра.

### <a name="syntax"></a>Синтаксис

```
BOOL AFXAPI AfxUnRegisterPreviewHandler(LPCTSTR lpszCLSID);
```

### <a name="parameters"></a>Параметры

*lpszCLSID*<br/>
Указывает CLSID обработчика для отмены регистрации.

### <a name="requirements"></a>Требования

**Заголовок:** afxdisp.h

## <a name="atlsetperuserregistration"></a> AtlSetPerUserRegistration

Задает, перенаправляет ли приложение доступ к реестру **HKEY_CURRENT_USER** (**HKCU**) узла.

### <a name="syntax"></a>Синтаксис

```
ATLINLINE ATLAPI AtlSetPerUserRegistration(bool bEnable);
```

### <a name="parameters"></a>Параметры

*bEnable*<br/>
[in] Значение TRUE указывает, что данные реестра направляется **HKCU** узла; Значение FALSE указывает, что приложение записывает данные реестра в узел по умолчанию. Узел по умолчанию является **HKEY_CLASSES_ROOT** (**HKCR**).

### <a name="return-value"></a>Возвращаемое значение

Значение S_OK, если метод выполнен успешно, в противном случае — значение HRESULT ошибки кода при возникновении ошибки.

### <a name="remarks"></a>Примечания

Перенаправление системного реестра не включена по умолчанию. Если этот параметр включен, доступ к реестру перенаправляется на **HKEY_CURRENT_USER\Software\Classes**.

Перенаправление не является общим. Только платформы MFC и ATL затрагивает это перенаправление системного реестра.

### <a name="requirements"></a>Требования

**Заголовок:** atlbase.h

##  <a name="atlunregistertypelib"></a>  AtlUnRegisterTypeLib

Эта функция вызывается для отмены регистрации библиотеки типов.

### <a name="syntax"></a>Синтаксис

```
ATLAPI AtlUnRegisterTypeLib(
    HINSTANCE hInstTypeLib,
    LPCOLESTR lpszIndex);
```

### <a name="parameters"></a>Параметры

*hInstTypeLib*<br/>
Дескриптор экземпляра модуля.

*lpszIndex*<br/>
Строка в формате "\\\N», где N — это целочисленный индекс ресурса библиотеки типов. Может иметь значение NULL, если индекс не является обязательным.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK в случае успеха или ошибки HRESULT в случае сбоя.

### <a name="remarks"></a>Примечания

Эта вспомогательная функция используемой [CAtlComModule::UnRegisterTypeLib](../../atl/reference/catlcommodule-class.md#unregistertypelib) и [AtlComModuleUnregisterServer](#atlcommoduleunregisterserver).

### <a name="requirements"></a>Требования

**Заголовок:** atlbase.h

##  <a name="atlloadtypelib"></a>  AtlLoadTypeLib

Эта функция вызывается для загрузки библиотеки типов.

### <a name="syntax"></a>Синтаксис

```
ATLINLINE ATLAPI AtlLoadTypeLib(
    HINSTANCE hInstTypeLib,
    LPCOLESTR lpszIndex,
    BSTR* pbstrPath,
    ITypeLib** ppTypeLib);
```

### <a name="parameters"></a>Параметры

*hInstTypeLib*<br/>
Дескриптор модуля, связанных с библиотекой типов.

*lpszIndex*<br/>
Строка в формате "\\\N», где N — это целочисленный индекс ресурса библиотеки типов. Может иметь значение NULL, если индекс не является обязательным.

*pbstrPath*<br/>
При успешном возвращении содержит полный путь модуля, связанных с библиотекой типов.

*ppTypeLib*<br/>
При успешном возвращении содержит указатель на указатель на библиотеку типов для загрузки.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK в случае успеха или ошибки HRESULT в случае сбоя.

### <a name="remarks"></a>Примечания

Эта вспомогательная функция используемой [AtlRegisterTypeLib](#atlregistertypelib) и [AtlUnRegisterTypeLib](#atlunregistertypelib).

##  <a name="atlupdateregistryfromresourced"></a>  AtlUpdateRegistryFromResourceD

Эта функция объявлена устаревшей Visual Studio 2013 и удалена в Visual Studio 2015.

```
<removed>
```

##  <a name="registrydataexchange"></a>  RegistryDataExchange

Эта функция вызывается для чтения из системного реестра или записи в него.

### <a name="syntax"></a>Синтаксис

```
HRESULT RegistryDataExchange(
    T* pT,
    enum RDXOperations rdxOp,
    void* pItem = NULL);
```

### <a name="parameters"></a>Параметры

*pT*<br/>
Указатель на текущий объект.

*rdxOp*<br/>
Значение перечисления, указывающее, какую операцию следует выполнять функцию. См. в таблице в разделе "Примечания" для допустимых значений.

*pItem*<br/>
Указатель на данные, должен быть считан или записать в реестр. Данные также представляет ключ, удаляемый из реестра. Значение по умолчанию имеет значение NULL.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK в случае успеха или ошибки HRESULT в случае сбоя.

### <a name="remarks"></a>Примечания

Макросы [BEGIN_RDX_MAP](registry-data-exchange-macros.md#begin_rdx_map) и [END_RDX_MAP](registry-data-exchange-macros.md#end_rdx_map) разверните на функцию, которая вызывает `RegistryDataExchange`.

Возможных значений перечисления, показывающий, следует выполнять операции функции показаны в следующей таблице:

|Значение перечисления|Операция|
|----------------|---------------|
|eReadFromReg|Чтение данных из реестра.|
|eWriteToReg|Запись данных в реестр.|
|eDeleteFromReg|Удалите раздел из реестра.|

### <a name="requirements"></a>Требования

**Заголовок:** atlbase.h

## <a name="see-also"></a>См. также

[Функции](atl-functions.md)<br/>
[Макросы для обмена данными с реестром](registry-data-exchange-macros.md)
