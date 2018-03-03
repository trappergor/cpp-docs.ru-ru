---
title: "Отладка и глобальные функции отчетов об ошибках | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- atlcomcli/ATL::AtlHresultFromLastError
- atlcom/ATL::AtlReportError
- atldef/ATL::AtlThrow
dev_langs:
- C++
helpviewer_keywords:
- functions [ATL], error reporting
ms.assetid: 11339c02-98cd-428d-b3b9-7deeb155a6a3
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 0b3383efcc78a022fc5131984957d94aa4b47838
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="debugging-and-error-reporting-global-functions"></a>Отладка и глобальные функции отчетов об ошибках
Эти функции предоставляют полезные средства отладки и трассировки.  
  
|||  
|-|-|  
|[AtlHresultFromLastError](debugging-and-error-reporting-global-functions.md#atlhresultfromlasterror)|Возвращает `GetLastError` код ошибки в форме HRESULT.|  
|[AtlHresultFromWin32](debugging-and-error-reporting-global-functions.md#atlhresultfromwin32)|Преобразует код ошибки Win32 в HRESULT.|  
|[AtlReportError](debugging-and-error-reporting-global-functions.md#atlreporterror)|Настраивает **IErrorInfo** для предоставления клиенту сведения об ошибке.|  
|[AtlThrow](debugging-and-error-reporting-global-functions.md#atlthrow)|Создает исключение `CAtlException`.|  
|[AtlThrowLastWin32](debugging-and-error-reporting-global-functions.md#atlthrowlastwin32)|Вызывайте эту функцию для сообщения об ошибке на основе результата функции Windows `GetLastError`.|  
  
##  <a name="atlhresultfromlasterror"></a>AtlHresultFromLastError  
 Возвращает значение кода последней ошибки в вызывающем потоке в форме HRESULT.  
  
```
HRESULT AtlHresultFromLastError();
```  
  
### <a name="remarks"></a>Примечания  
 `AtlHresultFromLastError`вызовы `GetLastError` для получения последней ошибки и возвращает ошибку после ее преобразования в значение HRESULT с помощью **HRESULT_FROM_WIN32** макрос.  

### <a name="requirements"></a>Требования  
 **Заголовок:** atlcomcli.h  

##  <a name="atlhresultfromwin32"></a>AtlHresultFromWin32  
 Преобразует код ошибки Win32 в HRESULT.  
  
```
AtlHresultFromWin32(DWORD error);
```  
  
### <a name="parameters"></a>Параметры  
 *Ошибка*  
 Значение ошибки для преобразования.  
  
### <a name="remarks"></a>Примечания  
 Преобразует код ошибки Win32 в HRESULT, с помощью макроса **HRESULT_FROM_WIN32**.  
  
> [!NOTE]
>  Вместо использования **HRESULT_FROM_WIN32(GetLastError())**, используйте функцию [AtlHresultFromLastError](debugging-and-error-reporting-global-functions.md#atlhresultfromlasterror).  

### <a name="requirements"></a>Требования  
 **Заголовок:** atlcomcli.h  

##  <a name="atlreporterror"></a>AtlReportError  
 Настраивает `IErrorInfo` интерфейс для предоставления клиентам объекта сведений об ошибке.  
  
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
 `clsid`  
 [in] Идентификатор CLSID объекта отчет об этой ошибке.  
  
 `lpszDesc`  
 [in] Строка, описывающая ошибку. Указать, что версии Юникода `lpszDesc` относится к типу **LPCOLESTR**; версия ANSI указывает тип `LPCSTR`.  
  
 `iid`  
 [in] Идентификатор IID интерфейса, определение ошибки или `GUID_NULL` Если ошибки определяется операционной системой.  
  
 `hRes`  
 [in] `HRESULT` Требуется возвращается вызывающему.  
  
 `nID`  
 [in] Идентификатор ресурса, в котором хранится строка описания ошибки. Это значение должно лежать между 0x0200 до 0xFFFF, включительно. В отладочных построениях **ASSERT** Если `nID` индекса не является допустимой строкой. В сборках выпуска строка описания ошибки будет присвоено «Unknown Error».  
  
 `dwHelpID`  
 [in] Идентификатор контекста справки для ошибки.  
  
 `lpszHelpFile`  
 [in] Путь и имя файла справки, описывающее ошибку.  
  
 `hInst`  
 [in] Дескриптор для ресурса. По умолчанию этот параметр является **__AtlBaseModuleModule::GetResourceInstance**, где **__AtlBaseModuleModule** — это глобальный экземпляр [CAtlBaseModule](../../atl/reference/catlbasemodule-class.md) или класс производный от него.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Если `hRes` параметр имеет ненулевое значение, возвращает значение `hRes`. Если `hRes` равно нулю, то первые четыре версии `AtlReportError` возвращают `DISP_E_EXCEPTION`. Две последние версии возвращают результат этого макроса **MAKE_HRESULT (1, FACILITY_ITF,** `nID` **)**.  
  
### <a name="remarks"></a>Примечания  
 Строка *lpszDesc* используется как текстовое описание ошибки. Когда клиент получает `hRes` возвращать из `AtlReportError`, клиент может обращаться к **IErrorInfo** структуры для получения сведений об ошибке.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATL_COM#52](../../atl/codesnippet/cpp/debugging-and-error-reporting-global-functions_1.cpp)]  
  
> [!CAUTION]
>  Не используйте `AtlReportError` обработчики catch в C++. Некоторые переопределения этих функций макросы преобразования строк ATL для внутреннего использования, который в свою очередь использовать `_alloca` внутри функции. С помощью `AtlReportError` в блоке catch C++ обработчик может привести к исключениям в обработчики catch C++.  

### <a name="requirements"></a>Требования  
 **Заголовок:** atlcom.h  
    
##  <a name="atlthrow"></a>AtlThrow  
 Вызывайте эту функцию для сообщения об ошибке на основе кода состояния `HRESULT`.  
  
```
__declspec(noreturn) inline void AtlThrow(HRESULT hr);
```  
  
### <a name="parameters"></a>Параметры  
 `hr`  
 Стандартное значение HRESULT.  
  
### <a name="remarks"></a>Примечания  
 Эта функция используется кода ATL и MFC в случае ошибки. Он также может вызываться из кода пользователя. Реализация по умолчанию эта функция зависит от определения символа **_ATL_NO_EXCEPTIONS** и типа проекта MFC и ATL.  
  
 Во всех случаях эта функция отслеживает HRESULT в отладчике.  
  
 В Visual Studio 2015 с обновлением 3 и более поздних версиях эта функция является атрибутом __declspec(noreturn) во избежание ложных предупреждений SAL.  
  
 Если **_ATL_NO_EXCEPTIONS** не определен в проекте MFC, эта функция вызывает [CMemoryException](../../mfc/reference/cmemoryexception-class.md) или [COleException](../../mfc/reference/coleexception-class.md) на основе значения HRESULT.  
  
 Если **_ATL_NO_EXCEPTIONS** не определен в проект ATL, функция создает [CAtlException](../../atl/reference/catlexception-class.md).  
  
 Если **_ATL_NO_EXCEPTIONS** будет определено, функция вызывает сбой утверждения, а не вызывает исключение.  
  
 Для проектов ATL можно предоставить собственную реализацию этой функции для использования библиотеки ATL в случае сбоя. Для этого, определите собственную функцию с такой же сигнатурой, что `AtlThrow` и #define `AtlThrow` на имя функции. Это необходимо сделать перед включением atlexcept.h (что означает, что она должна быть выполнена до включая заголовки ATL, поскольку atlbase.h включает atlexcept.h). Атрибут функции `__declspec(noreturn)` во избежание ложных предупреждений SAL.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATL_Windowing#95](../../atl/codesnippet/cpp/debugging-and-error-reporting-global-functions_2.h)]  

## <a name="requirements"></a>Требования  
 **Заголовок:** atldef.h  

##  <a name="atlthrowlastwin32"></a>AtlThrowLastWin32  
 Вызывайте эту функцию для сообщения об ошибке на основе результата функции Windows `GetLastError`.  
  
```
inline void AtlThrowLastWin32();
```  
  
### <a name="remarks"></a>Примечания  
 Эта функция отслеживает результат `GetLastError` в отладчик.  
  
 Если **_ATL_NO_EXCEPTIONS** не определен в проекте MFC, эта функция вызывает [CMemoryException](../../mfc/reference/cmemoryexception-class.md) или [COleException](../../mfc/reference/coleexception-class.md) на основе значения, возвращенные `GetLastError`.  
  
 Если **_ATL_NO_EXCEPTIONS** не определен в проект ATL, функция создает [CAtlException](../../atl/reference/catlexception-class.md).  
  
 Если **_ATL_NO_EXCEPTIONS** будет определено, функция вызывает сбой утверждения, а не вызывает исключение.  

## <a name="requirements"></a>Требования  
 **Заголовок:** atldef.h  
   
     
## <a name="see-also"></a>См. также  
 [Функции](../../atl/reference/atl-functions.md)   
 [Макросы для отладки и создания отчетов об ошибках](../../atl/reference/debugging-and-error-reporting-macros.md)









