---
title: Глобальные функции отладки и отчетов об ошибках
ms.date: 11/04/2016
f1_keywords:
- atlcomcli/ATL::AtlHresultFromLastError
- atlcom/ATL::AtlReportError
- atldef/ATL::AtlThrow
helpviewer_keywords:
- functions [ATL], error reporting
ms.assetid: 11339c02-98cd-428d-b3b9-7deeb155a6a3
ms.openlocfilehash: f7483b7473383958089b0c88d0b3c2645ddc2a4f
ms.sourcegitcommit: 7ecd91d8ce18088a956917cdaf3a3565bd128510
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/16/2020
ms.locfileid: "79423138"
---
# <a name="debugging-and-error-reporting-global-functions"></a>Глобальные функции отладки и отчетов об ошибках

Эти функции предоставляют полезные средства отладки и трассировки.

|||
|-|-|
|[атлхресултфромластеррор](debugging-and-error-reporting-global-functions.md#atlhresultfromlasterror)|Возвращает `GetLastError` код ошибки в виде HRESULT.|
|[AtlHresultFromWin32](debugging-and-error-reporting-global-functions.md#atlhresultfromwin32)|Преобразует код ошибки Win32 в HRESULT.|
|[атлрепортеррор](debugging-and-error-reporting-global-functions.md#atlreporterror)|Настраивает `IErrorInfo` для предоставления клиенту сведений об ошибке.|
|[атлсров](debugging-and-error-reporting-global-functions.md#atlthrow)|Формирует исключение `CAtlException`.|
|[AtlThrowLastWin32](debugging-and-error-reporting-global-functions.md#atlthrowlastwin32)|Вызывайте эту функцию для сообщения об ошибке на основе результата функции Windows `GetLastError`.|

##  <a name="atlhresultfromlasterror"></a>атлхресултфромластеррор

Возвращает значение кода последней ошибки в вызывающем потоке в форме HRESULT.

```
HRESULT AtlHresultFromLastError();
```

### <a name="remarks"></a>Remarks

`AtlHresultFromLastError` вызывает `GetLastError` для получения последней ошибки и возвращает ошибку после ее преобразования в значение HRESULT с помощью макроса HRESULT_FROM_WIN32.

### <a name="requirements"></a>Требования

**Заголовок:** atlcomcli. h

##  <a name="atlhresultfromwin32"></a>AtlHresultFromWin32

Преобразует код ошибки Win32 в HRESULT.

```
AtlHresultFromWin32(DWORD error);
```

### <a name="parameters"></a>Параметры

*error*<br/>
Значение ошибки для преобразования.

### <a name="remarks"></a>Remarks

Преобразует код ошибки Win32 в значение HRESULT с помощью макроса HRESULT_FROM_WIN32.

> [!NOTE]
>  Вместо использования `HRESULT_FROM_WIN32(GetLastError())`используйте функцию [атлхресултфромластеррор](debugging-and-error-reporting-global-functions.md#atlhresultfromlasterror).

### <a name="requirements"></a>Требования

**Заголовок:** atlcomcli. h

##  <a name="atlreporterror"></a>атлрепортеррор

Устанавливает интерфейс `IErrorInfo`, чтобы предоставить сведения об ошибке клиентам объекта.

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

*этому*<br/>
окне Идентификатор CLSID объекта, сообщающего об ошибке.

*лпсздеск*<br/>
окне Строка, описывающая ошибку. Версии Юникода указывают, что *лпсздеск* имеет тип лпколестр; версия ANSI указывает тип LPCSTR.

*IID*<br/>
окне Идентификатор IID интерфейса, определяющего ошибку, или GUID_NULL, если ошибка определяется операционной системой.

*хрес*<br/>
окне Значение HRESULT, которое требуется вернуть вызывающему объекту.

*nID*<br/>
окне Идентификатор ресурса, в котором хранится строка описания ошибки. Это значение должно находиться в диапазоне от 0x0200 до 0xFFFF включительно. В отладочных сборках оператор **Assert** приведет к тому, что *NID* не индексирует допустимую строку. В сборках выпуска для строки описания ошибки будет задано значение "Неизвестная ошибка".

*двхелпид*<br/>
окне Идентификатор контекста справки для ошибки.

*лпсзелпфиле*<br/>
окне Путь и имя файла справки, описывающего ошибку.

*хинст*<br/>
окне Маркер ресурса. По умолчанию этот параметр имеет значение `__AtlBaseModuleModule::GetResourceInstance`, где `__AtlBaseModuleModule` является глобальным экземпляром [катлбасемодуле](../../atl/reference/catlbasemodule-class.md) или производным от него классом.

### <a name="return-value"></a>Возвращаемое значение

Если параметр *хрес* не равен нулю, возвращает значение *хрес*. Если *хрес* равен нулю, то первые четыре версии `AtlReportError` возвращают DISP_E_EXCEPTION. Последние две версии возвращают результат макроса **MAKE_HRESULT (1, FACILITY_ITF,** `nID` **)** .

### <a name="remarks"></a>Remarks

Строка *лпсздеск* используется в качестве текстового описания ошибки. Когда клиент получает *хрес* , возвращаемый из `AtlReportError`, клиент может получить доступ к структуре `IErrorInfo` для получения сведений об ошибке.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_COM#52](../../atl/codesnippet/cpp/debugging-and-error-reporting-global-functions_1.cpp)]

> [!CAUTION]
>  Не используйте `AtlReportError` в C++ обработчиках catch. Некоторые переопределения этих функций используют встроенные макросы преобразования строк ATL, которые, в свою очередь, используют функцию `_alloca` внутренне. Использование `AtlReportError` в обработчике C++ catch может вызвать исключения в C++ обработчиках catch.

### <a name="requirements"></a>Требования

**Заголовок:** атлком. h

##  <a name="atlthrow"></a>атлсров

Вызовите эту функцию, чтобы сообщить об ошибке на основе кода состояния HRESULT.

```
__declspec(noreturn) inline void AtlThrow(HRESULT hr);
```

### <a name="parameters"></a>Параметры

*кадров*<br/>
Стандартное значение HRESULT.

### <a name="remarks"></a>Remarks

Эта функция используется в коде ATL и MFC в случае возникновения ошибки. Его также можно вызывать из собственного кода. Реализация по умолчанию этой функции зависит от определения символа _ATL_NO_EXCEPTIONS и от типа проекта, MFC или ATL.

Во всех случаях эта функция выполняет трассировку HRESULT с отладчиком.

В Visual Studio 2015 с обновлением 3 и более поздних версий эта функция имеет атрибут __declspec (noreturn), чтобы избежать ложных предупреждений SAL.

Если _ATL_NO_EXCEPTIONS не определен в проекте MFC, эта функция создает исключение [CMemoryException](../../mfc/reference/cmemoryexception-class.md) или [COleException](../../mfc/reference/coleexception-class.md) на основе значения HRESULT.

Если _ATL_NO_EXCEPTIONS не определен в проекте ATL, функция создает исключение [катлексцептион](../../atl/reference/catlexception-class.md).

Если определено _ATL_NO_EXCEPTIONS, функция вызывает сбой утверждения, а не создает исключение.

Для проектов ATL можно предоставить собственную реализацию этой функции, которая будет использоваться библиотекой ATL в случае сбоя. Для этого определите собственную функцию с той же сигнатурой, что и `AtlThrow`, а #define `AtlThrow` в качестве имени функции. Это необходимо сделать перед включением атлексцепт. h (это означает, что перед включением всех заголовков ATL необходимо выполнить его, так как atlbase. h содержит атлексцепт. h). Атрибут `__declspec(noreturn)` функции во избежание ложных предупреждений SAL.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_Windowing#95](../../atl/codesnippet/cpp/debugging-and-error-reporting-global-functions_2.h)]

## <a name="requirements"></a>Требования

**Заголовок:** атлдеф. h

##  <a name="atlthrowlastwin32"></a>AtlThrowLastWin32

Вызывайте эту функцию для сообщения об ошибке на основе результата функции Windows `GetLastError`.

```
inline void AtlThrowLastWin32();
```

### <a name="remarks"></a>Remarks

Эта функция отслеживает результат `GetLastError` отладчику.

Если _ATL_NO_EXCEPTIONS не определен в проекте MFC, эта функция создает исключение [CMemoryException](../../mfc/reference/cmemoryexception-class.md) или [COleException](../../mfc/reference/coleexception-class.md) на основе значения, возвращаемого `GetLastError`.

Если _ATL_NO_EXCEPTIONS не определен в проекте ATL, функция создает исключение [катлексцептион](../../atl/reference/catlexception-class.md).

Если определено _ATL_NO_EXCEPTIONS, функция вызывает сбой утверждения, а не создает исключение.

## <a name="requirements"></a>Требования

**Заголовок:** атлдеф. h

## <a name="see-also"></a>См. также раздел

[Функции](../../atl/reference/atl-functions.md)<br/>
[Макросы для отладки и создания отчетов об ошибках](../../atl/reference/debugging-and-error-reporting-macros.md)
