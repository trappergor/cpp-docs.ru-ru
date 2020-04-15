---
title: Глобальные функции реестра и библиотеки типов
ms.date: 03/27/2019
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
helpviewer_keywords:
- RegistryDataExchange function, global functions
ms.assetid: d58b8a4e-975c-4417-8b34-d3c847f679b3
ms.openlocfilehash: 69df927ddd04c19d10703854aa8c8948894309d1
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81326076"
---
# <a name="registry-and-typelib-global-functions"></a>Глобальные функции реестра и библиотеки типов

Эти функции обеспечивают поддержку для загрузки и регистрации библиотеки типов.

> [!IMPORTANT]
> Функции, перечисленные в следующих таблицах, не могут использоваться в приложениях, выполняемых в Windows Runtime.

|||
|-|-|
|[AfxRegCreateKey](#afxregcreatekey)|Создает указанный ключ реестра.|
|[AfxRegDeleteKey](#afxregdeletekey)|Удаляет указанный ключ реестра.|
|[AfxRegisterPreviewHandler](#afxregisterpreviewhandler)|Помощник для регистрации обработчика предварительного просмотра.|
|[AfxUnregisterPreviewHandler](#afxunregisterpreviewhandler)| Помощник, чтобы отменить регистрацию обработчика предварительного просмотра. |
|[AtlRegisterTypeLib](#atlregistertypelib)|Эта функция вызывается для регистрации библиотеки типов.|
|[AtlUnRegisterTypeLib](#atlunregistertypelib)|Эта функция называется отменить регистрацию библиотеки типа|
|[AfxRegOpenKey](#afxregopenkey)|Открывает указанный ключ реестра.|
|[AfxRegOpenKeyEx](#afxregopenkeyex)|Открывает указанный ключ реестра.|
|[AtlLoadTypeLib](#atlloadtypelib)|Эта функция вызывается для загрузки библиотеки типов.|
|[AtlUpdateRegistryFromResourceD](#atlupdateregistryfromresourced)|Эта функция вызывается для обновления реестра из предоставленного ресурса.|
|[RegistryDataExchange](#registrydataexchange)|Эта функция вызывается для чтения из системного реестра или записи в него. Вызывается [реестра обмена данными Макрос](../../atl/reference/registry-data-exchange-macros.md).|

Эти функции контролируют, какой узла в реестре программа использует для хранения информации.

|||
|-|-|
|[AtlGetPerUserRegistration](#atlgetperuserregistration)|Получает ли приложение перенаправляет доступ к реестру **HKEY_CURRENT_USER** **(HKCU**) узла.|
|[AtlSetPerUserRegistration](#atlsetperuserregistration)|Устанавливает, перенаправляет ли приложение доступ **HKEY_CURRENT_USER** к HKEY_CURRENT_USER **(HKCU**) узла.|

### <a name="requirements"></a>Требования

**Заголовок:** atlbase.h

## <a name="atlgetperuserregistration"></a><a name="atlgetperuserregistration"></a>AtlGetPerUserРегистрация

Используйте эту функцию, чтобы определить, перенаправляет ли приложение доступ к узле **HKEY_CURRENT_USER** **(HKCU)**.

### <a name="syntax"></a>Синтаксис

```
ATLINLINE ATLAPI AtlGetPerUserRegistration(bool* pEnabled);
```

### <a name="parameters"></a>Параметры

*pEnabled*<br/>
(ваут) TRUE указывает на то, что информация о реестре направляется в узлы **HKCU;** FALSE указывает, что приложение записывает информацию о реестре в узлы по умолчанию. Узла по умолчанию **HKEY_CLASSES_ROOT** **(HKCR).**

### <a name="return-value"></a>Возвращаемое значение

S_OK, если метод успешен, в противном случае код ошибки HRESULT, если происходит ошибка.

### <a name="remarks"></a>Remarks

Перенаправление реестра не включено по умолчанию. Если вы включите эту опцию, доступ к реестру перенаправляется **HKEY_CURRENT_USER классы программного обеспечения.**

Перенаправление не является глобальным. Только mFC и ATL рамках, пострадавших от этого реестра перенаправления.

### <a name="requirements"></a>Требования

**Заголовок:** atlbase.h

## <a name="afxregcreatekey"></a><a name="afxregcreatekey"></a>AfxRegCreateKey

Создает указанный ключ реестра.

### <a name="syntax"></a>Синтаксис

```
LONG AFXAPI AfxRegCreateKey(HKEY hKey, LPCTSTR lpSubKey, PHKEY phkResult, CAtlTransactionManager* pTM = NULL);
```

### <a name="parameters"></a>Параметры

*hKey*<br/>
Ручка к ключу открытого реестра.

*lpSubKey*<br/>
Имя ключа, который эта функция открывает или создает.

*phkResult*<br/>
Указатель на переменную, которая получает ручку к открытому или созданного ключу.

*Ptm*<br/>
Указатель на `CAtlTransactionManager` объект.

### <a name="return-value"></a>Возвращаемое значение

Если функция успешно, значение возврата ERROR_SUCCESS. Если функция выходит из строя, значение возврата является кодом ошибки ненулевого, определенным в Winerror.h.

### <a name="requirements"></a>Требования

**Заголовок:** afxpriv.h

## <a name="afxregdeletekey"></a><a name="afxregdeletekey"></a>AfxRegDeleteKey

Удаляет указанный ключ реестра.

### <a name="syntax"></a>Синтаксис

```
LONG AFXAPI AfxRegDeleteKey(HKEY hKey, LPCTSTR lpSubKey, CAtlTransactionManager* pTM = NULL);
```

### <a name="parameters"></a>Параметры

*hKey*<br/>
Ручка к ключу открытого реестра.

*lpSubKey*<br/>
Имя ключа, которое будет удалено.

*Ptm*<br/>
Указатель на `CAtlTransactionManager` объект.

### <a name="return-value"></a>Возвращаемое значение

Если функция успешно, значение возврата ERROR_SUCCESS. Если функция выходит из строя, значение возврата является кодом ошибки ненулевого, определенным в Winerror.h.

### <a name="requirements"></a>Требования

**Заголовок:** afxpriv.h

## <a name="afxregisterpreviewhandler"></a>

Помощник для регистрации обработчика предварительного просмотра.

### <a name="syntax"></a>Синтаксис

```
BOOL AFXAPI AfxRegisterPreviewHandler(LPCTSTR lpszCLSID, LPCTSTR lpszShortTypeName, LPCTSTR lpszFilterExt);
```

### <a name="parameters"></a>Параметры

*lpszCLSID*<br/>
Определяет CLSID обработчика.

*lpszShortTypeName*<br/>
Определяет ProgID обработчика.

*lpszFilterExt*<br/>
Упогоняет расширение файла, зарегистрированное этим обработчиком.

### <a name="requirements"></a>Требования

**Заголовок:** afxdisp.h

## <a name="atlregistertypelib"></a><a name="atlregistertypelib"></a>AtlRegisterTypeLibLib

Эта функция вызывается для регистрации библиотеки типов.

```
ATLAPI AtlRegisterTypeLib(HINSTANCE hInstTypeLib, LPCOLESTR lpszIndex);
```

### <a name="parameters"></a>Параметры

*hInstTypeLib*<br/>
Ручка к экземпляру модуля.

*lpszИндекс*<br/>
Строка в\\формате "N", где N является инкемгерным индексом ресурса библиотеки типа. Может быть NULL, если индекс не требуется.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK на успех, или ошибка HRESULT на отказ.

### <a name="remarks"></a>Remarks

Эта функция помощника используется [AtlComModuleUnregisterServer](server-registration-global-functions.md#atlcommoduleunregisterserver) и [CAtlComModule::RegisterTypeLib](../../atl/reference/catlcommodule-class.md#registertypelib).

### <a name="requirements"></a>Требования

**Заголовок:** atlbase.h

## <a name="afxregopenkey"></a><a name="afxregopenkey"></a>AfxRegOpenKey

Открывает указанный ключ реестра.

### <a name="syntax"></a>Синтаксис

```
LONG AFXAPI AfxRegOpenKey(HKEY hKey, LPCTSTR lpSubKey, PHKEY phkResult, CAtlTransactionManager* pTM = NULL);
```

### <a name="parameters"></a>Параметры

*hKey*<br/>
Ручка к ключу открытого реестра.

*lpSubKey*<br/>
Имя ключа, который эта функция открывает или создает.

*phkResult*<br/>
Указатель на переменную, которая получает ручку к созданного ключу.

*Ptm*<br/>
Указатель на `CAtlTransactionManager` объект.

### <a name="return-value"></a>Возвращаемое значение

Если функция успешно, значение возврата ERROR_SUCCESS. Если функция выходит из строя, значение возврата является кодом ошибки ненулевого, определенным в Winerror.h.

### <a name="requirements"></a>Требования

**Заголовок:** afxpriv.h

## <a name="afxregopenkeyex"></a><a name="afxregopenkeyex"></a>AfxRegOpenKeyEx

Открывает указанный ключ реестра.

### <a name="syntax"></a>Синтаксис

```
LONG AFXAPI AfxRegOpenKeyEx(HKEY hKey, LPCTSTR lpSubKey, DWORD ulOptions, REGSAM samDesired, PHKEY phkResult, CAtlTransactionManager* pTM = NULL);
```

### <a name="parameters"></a>Параметры

*hKey*<br/>
Ручка к ключу открытого реестра.

*lpSubKey*<br/>
Имя ключа, который эта функция открывает или создает.

*ulOptions*<br/>
Этот параметр зарезервирован и должен быть нулевым.

*samDesired*<br/>
Маска, которая определяет желаемые права доступа к ключу.

*phkResult*<br/>
Указатель на переменную, которая получает ручку к открытому ключу.

*Ptm*<br/>
Указатель на `CAtlTransactionManager` объект.

### <a name="return-value"></a>Возвращаемое значение

Если функция успешно, значение возврата ERROR_SUCCESS. Если функция выходит из строя, значение возврата является кодом ошибки ненулевого, определенным в Winerror.h.

### <a name="requirements"></a>Требования

**Заголовок:** afxpriv.h

## <a name="afxunregisterpreviewhandler"></a><a name="afxunregisterpreviewhandler"></a>AfxUnregisterPreviewHandler

Помощник, чтобы отменить регистрацию обработчика предварительного просмотра.

### <a name="syntax"></a>Синтаксис

```
BOOL AFXAPI AfxUnRegisterPreviewHandler(LPCTSTR lpszCLSID);
```

### <a name="parameters"></a>Параметры

*lpszCLSID*<br/>
Упоняет CLSID обработчика для незарегистрированного.

### <a name="requirements"></a>Требования

**Заголовок:** afxdisp.h

## <a name="atlsetperuserregistration"></a><a name="atlsetperuserregistration"></a>AtlSetPerUserРегистрация

Устанавливает, перенаправляет ли приложение доступ **HKEY_CURRENT_USER** к HKEY_CURRENT_USER **(HKCU**) узла.

### <a name="syntax"></a>Синтаксис

```
ATLINLINE ATLAPI AtlSetPerUserRegistration(bool bEnable);
```

### <a name="parameters"></a>Параметры

*bEnable*<br/>
(в) TRUE указывает на то, что информация о реестре направляется в узлы **HKCU;** FALSE указывает, что приложение записывает информацию о реестре в узлы по умолчанию. Узла по умолчанию **HKEY_CLASSES_ROOT** **(HKCR).**

### <a name="return-value"></a>Возвращаемое значение

S_OK, если метод успешен, в противном случае код ошибки HRESULT, если происходит ошибка.

### <a name="remarks"></a>Remarks

Перенаправление реестра не включено по умолчанию. Если вы включите эту опцию, доступ к реестру перенаправляется **HKEY_CURRENT_USER классы программного обеспечения.**

Перенаправление не является глобальным. Только mFC и ATL рамках, пострадавших от этого реестра перенаправления.

### <a name="requirements"></a>Требования

**Заголовок:** atlbase.h

## <a name="atlunregistertypelib"></a><a name="atlunregistertypelib"></a>AtlUnRegisterTypeLibLib

Эта функция вызывается для отмены регистрации библиотеки типов.

### <a name="syntax"></a>Синтаксис

```
ATLAPI AtlUnRegisterTypeLib(
    HINSTANCE hInstTypeLib,
    LPCOLESTR lpszIndex);
```

### <a name="parameters"></a>Параметры

*hInstTypeLib*<br/>
Ручка к экземпляру модуля.

*lpszИндекс*<br/>
Строка в\\формате "N", где N является инкемгерным индексом ресурса библиотеки типа. Может быть NULL, если индекс не требуется.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK на успех, или ошибка HRESULT на отказ.

### <a name="remarks"></a>Remarks

Эта функция помощника используется [CAtlComModule::UnRegisterTypeLib](../../atl/reference/catlcommodule-class.md#unregistertypelib) и [AtlComModuleUnRegisterServer](server-registration-global-functions.md#atlcommoduleunregisterserver).

### <a name="requirements"></a>Требования

**Заголовок:** atlbase.h

## <a name="atlloadtypelib"></a><a name="atlloadtypelib"></a>AtlLoadTypeLib

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
Обработка модуля, связанного с библиотекой типов.

*lpszИндекс*<br/>
Строка в\\формате "N", где N является инкемгерным индексом ресурса библиотеки типа. Может быть NULL, если индекс не требуется.

*pbstrPath*<br/>
При успешном возвращении содержится полный путь модуля, связанный с библиотекой типов.

*ppTypeLib*<br/>
При успешном возвращении содержит указатель на указатель на загруженную библиотеку типа.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK на успех, или ошибка HRESULT на отказ.

### <a name="remarks"></a>Remarks

Эта функция помощника используется [AtlRegisterTypeLib](#atlregistertypelib) и [AtlUnRegisterTypeLib](#atlunregistertypelib).

## <a name="atlupdateregistryfromresourced"></a><a name="atlupdateregistryfromresourced"></a>AtlUpdateRegistryFromResourceD

Эта функция объявлена устаревшей Visual Studio 2013 и удалена в Visual Studio 2015.

```
<removed>
```

## <a name="registrydataexchange"></a><a name="registrydataexchange"></a>RegistryDataExchange

Эта функция вызывается для чтения из системного реестра или записи в него.

### <a name="syntax"></a>Синтаксис

```
HRESULT RegistryDataExchange(
    T* pT,
    enum RDXOperations rdxOp,
    void* pItem = NULL);
```

### <a name="parameters"></a>Параметры

*Pt*<br/>
Указатель на текущий объект.

*rdxOp*<br/>
Значение перечисления, которое указывает, какую операцию должна выполнять функция. Смотрите таблицу в разделе Замечания для допустимых значений.

*pItem*<br/>
Указатель на данные, которые должны быть прочитаны из реестра или написаны. Данные также могут представлять ключ, который будет удален из реестра. Значение по умолчанию — NULL.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK на успех, или ошибка HRESULT на отказ.

### <a name="remarks"></a>Remarks

МакросBEGIN_RDX_MAP [BEGIN_RDX_MAP](registry-data-exchange-macros.md#begin_rdx_map) и [END_RDX_MAP](registry-data-exchange-macros.md#end_rdx_map) расширить функцию, которая вызывает `RegistryDataExchange`.

Возможные значения, указывающие на операцию, которую должна выполнить функция, отображаются в следующей таблице:

|Значение Enum|Операция|
|----------------|---------------|
|eReadFromReg|Читайте данные из реестра.|
|eWriteToReg|Запишите данные в реестр.|
|eDeleteFromReg|Удалите ключ из реестра.|

### <a name="requirements"></a>Требования

**Заголовок:** atlbase.h

## <a name="see-also"></a>См. также раздел

[Функции](atl-functions.md)<br/>
[Макрос обмена данными реестра](registry-data-exchange-macros.md)
