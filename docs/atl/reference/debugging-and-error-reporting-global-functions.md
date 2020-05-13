---
title: Отладка и отчетность об ошибках глобальных функций
ms.date: 11/04/2016
f1_keywords:
- atlcomcli/ATL::AtlHresultFromLastError
- atlcom/ATL::AtlReportError
- atldef/ATL::AtlThrow
helpviewer_keywords:
- functions [ATL], error reporting
ms.assetid: 11339c02-98cd-428d-b3b9-7deeb155a6a3
ms.openlocfilehash: f7636b1f4e13340b223edd8c63c39bbeb21c8bd0
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81330206"
---
# <a name="debugging-and-error-reporting-global-functions"></a>Отладка и отчетность об ошибках глобальных функций

Эти функции обеспечивают полезную отладку и отслеживание объектов.

|||
|-|-|
|[AtlHresultFromLastError](debugging-and-error-reporting-global-functions.md#atlhresultfromlasterror)|Возвращает `GetLastError` код ошибки в виде HRESULT.|
|[AtlHresultFromWin32](debugging-and-error-reporting-global-functions.md#atlhresultfromwin32)|Преобразует код ошибки Win32 в HRESULT.|
|[AtlReportError](debugging-and-error-reporting-global-functions.md#atlreporterror)|Настраивается `IErrorInfo` для предоставления клиенту сведений об ошибках.|
|[AtlThrow](debugging-and-error-reporting-global-functions.md#atlthrow)|Формирует исключение `CAtlException`.|
|[AtlThrowLastWin32](debugging-and-error-reporting-global-functions.md#atlthrowlastwin32)|Вызывайте эту функцию для сообщения об ошибке на основе результата функции Windows `GetLastError`.|

## <a name="atlhresultfromlasterror"></a><a name="atlhresultfromlasterror"></a>AtlHresultFromLastError

Возвращает значение кода последней ошибки в вызывающем потоке в форме HRESULT.

```
HRESULT AtlHresultFromLastError();
```

### <a name="remarks"></a>Remarks

`AtlHresultFromLastError`требует `GetLastError` получить последнюю ошибку и возвращает ошибку после преобразования ее в HRESULT с помощью HRESULT_FROM_WIN32 макроса.

### <a name="requirements"></a>Требования

**Заголовок:** atlcomcli.h

## <a name="atlhresultfromwin32"></a><a name="atlhresultfromwin32"></a>AtlHresultFromWin32

Преобразует код ошибки Win32 в HRESULT.

```
AtlHresultFromWin32(DWORD error);
```

### <a name="parameters"></a>Параметры

*error*<br/>
Значение ошибки для преобразования.

### <a name="remarks"></a>Remarks

Преобразует код ошибки Win32 в HRESULT, используя макроHRESULT_FROM_WIN32.

> [!NOTE]
> Вместо `HRESULT_FROM_WIN32(GetLastError())`использования, использовать функцию [AtlHresultFromLastError](debugging-and-error-reporting-global-functions.md#atlhresultfromlasterror).

### <a name="requirements"></a>Требования

**Заголовок:** atlcomcli.h

## <a name="atlreporterror"></a><a name="atlreporterror"></a>AtlReportError

Настройка `IErrorInfo` интерфейса для предоставления информации об ошибках клиентам объекта.

```
HRESULT WINAPI AtlReportError(
    const CLSID& clsid,
    LPCOLESTR lpszDesc,
    const IID& iid = GUID_NULL,
    HRESULT hRes = 0);

HRESULT WINAPI AtlReportError(
    const CLSID& clsid,
    LPCOLESTR lpszDesc,
    DWORD dwHelpID,
    LPCOLESTR lpszHelpFile,
    const IID& iid = GUID_NULL,
    HRESULT hRes = 0);

HRESULT WINAPI AtlReportError(
    const CLSID& clsid,
    LPCSTR lpszDesc,
    const IID& iid = GUID_NULL,
    HRESULT hRes = 0);

HRESULT WINAPI AtlReportError(
    const CLSID& clsid,
    LPCSTR lpszDesc,
    DWORD dwHelpID,
    LPCSTR lpszHelpFile,
    const IID& iid = GUID_NULL,
    HRESULT hRes = 0);

HRESULT WINAPI AtlReportError(
    const CLSID& clsid,
    UINT nID,
    const IID& iid = GUID_NULL,
    HRESULT hRes = 0,
    HINSTANCE hInst = _AtlBaseModule.GetResourceInstance());

HRESULT WINAPI AtlReportError(
    const CLSID& clsid,
    UINT nID,
    DWORD dwHelpID,
    LPCOLESTR lpszHelpFile,
    const IID& iid = GUID_NULL,
    HRESULT hRes = 0,
    HINSTANCE hInst = _AtlBaseModule.GetResourceInstance());
```

### <a name="parameters"></a>Параметры

*clsid*<br/>
(в) CLSID объекта, сообщая об ошибке.

*lpszDesc*<br/>
(в) Строка, описывающая ошибку. Версии Unicode указывают, что *lpszDesc* имеет тип LPCOLESTR; версия ANSI определяет тип LPCSTR.

*Iid*<br/>
(в) IID интерфейса, определяющий ошибку или GUID_NULL, если ошибка определена операционной системой.

*hRes*<br/>
(в) HRESULT вы хотите вернуться к вызывающему абоненту.

*nID*<br/>
(в) Идентификатор ресурса, в котором хранится строка описания ошибок. Это значение должно лежать между 0x0200 и 0xFFFF, включительно. В отладке сборки, **ASSERT** приведет, если *nID* не индексирует действительную строку. В сборках релизов строка описания ошибок будет установлена на "Неизвестная ошибка".

*dwHelpID*<br/>
(в) Идентификатор контекста справки для ошибки.

*lpszHelpFile*<br/>
(в) Путь и имя файла справки, описывающие ошибку.

*hInst*<br/>
(в) Ручка к ресурсу. По умолчанию этот `__AtlBaseModuleModule::GetResourceInstance`параметр находится в `__AtlBaseModuleModule` глобальном экземпляре [CAtlBaseModule](../../atl/reference/catlbasemodule-class.md) или класса, полученного из него.

### <a name="return-value"></a>Возвращаемое значение

Если параметр *hRes* незеро, возвращает значение *hRes.* Если *hRes* равен нулю, `AtlReportError` то первые четыре версии возврата DISP_E_EXCEPTION. Последние две версии возвращают результат **макро-MAKE_HRESULT (1,** `nID` **FACILITY_ITF)**.

### <a name="remarks"></a>Remarks

Строка *lpszDesc* используется в качестве текстового описания ошибки. Когда клиент получает *hRes* вы `AtlReportError`возвращаете сярвые от, клиент может достигнуть `IErrorInfo` структуры для деталей о ошибке.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_COM#52](../../atl/codesnippet/cpp/debugging-and-error-reporting-global-functions_1.cpp)]

> [!CAUTION]
> Не используйте `AtlReportError` обработчики ловли се. Некоторые переопределения этих функций используют макросы преобразования строкATL `_alloca` внутренне, которые, в свою очередь, используют функцию внутренне. Использование `AtlReportError` обработчика ловли сс-ке может привести к исключениям в обработчиках ловли се.

### <a name="requirements"></a>Требования

**Заголовок:** atlcom.h

## <a name="atlthrow"></a><a name="atlthrow"></a>AtlThrow

Вызовите эту функцию, чтобы сигнализировать об ошибке на основе кода состояния HRESULT.

```
__declspec(noreturn) inline void AtlThrow(HRESULT hr);
```

### <a name="parameters"></a>Параметры

*Hr*<br/>
Стандартное значение HRESULT.

### <a name="remarks"></a>Remarks

Эта функция используется кодом ATL и MFC в случае ошибки. Он также может быть вызван из вашего собственного кода. Реализация этой функции по умолчанию зависит от определения символа _ATL_NO_EXCEPTIONS и типа проекта, MFC или ATL.

Во всех случаях эта функция отслеживает HRESULT к отладчику.

В Visual Studio 2015 Update 3 и позже, эта функция приписывается __declspec (безвозврат), чтобы избежать ложных предупреждений SAL.

Если _ATL_NO_EXCEPTIONS не определенв в проекте MFC, эта функция бросает [CMemoryException](../../mfc/reference/cmemoryexception-class.md) или [COleException](../../mfc/reference/coleexception-class.md) на основе значения HRESULT.

Если _ATL_NO_EXCEPTIONS не определена в проекте ATL, функция бросает [CAtlException](../../atl/reference/catlexception-class.md).

Если _ATL_NO_EXCEPTIONS определен, функция вызывает сбой утверждения вместо того, чтобы бросать исключение.

Для проектов ATL можно обеспечить собственную реализацию этой функции, которая будет использоваться ATL в случае сбоя. Для этого определите свою собственную функцию с той же подписью, `AtlThrow` что и #define `AtlThrow` название вашей функции. Это должно быть сделано до включения atlexcept.h (что означает, что это должно быть сделано до включения любых заголовков ATL, так как atlbase.h включает в себя atlexcept.h). Атрибут вашей функции, `__declspec(noreturn)` чтобы избежать ложных предупреждений SAL.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_Windowing#95](../../atl/codesnippet/cpp/debugging-and-error-reporting-global-functions_2.h)]

## <a name="requirements"></a>Требования

**Заголовок:** atldef.h

## <a name="atlthrowlastwin32"></a><a name="atlthrowlastwin32"></a>AtlThrowLastWin32

Вызывайте эту функцию для сообщения об ошибке на основе результата функции Windows `GetLastError`.

```
inline void AtlThrowLastWin32();
```

### <a name="remarks"></a>Remarks

Эта функция отслеживает `GetLastError` результат отладчика.

Если _ATL_NO_EXCEPTIONS не определенв в проекте MFC, эта функция бросает [CMemoryException](../../mfc/reference/cmemoryexception-class.md) или `GetLastError` [COleException](../../mfc/reference/coleexception-class.md) на основе значения, возвращенного .

Если _ATL_NO_EXCEPTIONS не определена в проекте ATL, функция бросает [CAtlException](../../atl/reference/catlexception-class.md).

Если _ATL_NO_EXCEPTIONS определен, функция вызывает сбой утверждения вместо того, чтобы бросать исключение.

## <a name="requirements"></a>Требования

**Заголовок:** atldef.h

## <a name="see-also"></a>См. также раздел

[Функции](../../atl/reference/atl-functions.md)<br/>
[Макросы отлады и отчетности об ошибках](../../atl/reference/debugging-and-error-reporting-macros.md)
