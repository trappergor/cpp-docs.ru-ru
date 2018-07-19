---
title: Отладка и глобальные функции отчетов об ошибках | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: d41cc60b9a30254e46a9ca3ef3d3ad7dbc0dfcfb
ms.sourcegitcommit: 7d68f8303e021e27dc8f4d36e764ed836e93d24f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/06/2018
ms.locfileid: "37882917"
---
# <a name="debugging-and-error-reporting-global-functions"></a>Отладка и глобальные функции отчетов об ошибках
Эти функции предоставляют полезные средства отладки и трассировки.  
  
|||  
|-|-|  
|[AtlHresultFromLastError](debugging-and-error-reporting-global-functions.md#atlhresultfromlasterror)|Возвращает `GetLastError` код ошибки в форме HRESULT.|  
|[AtlHresultFromWin32](debugging-and-error-reporting-global-functions.md#atlhresultfromwin32)|Преобразует код ошибки Win32 в HRESULT.|  
|[AtlReportError](debugging-and-error-reporting-global-functions.md#atlreporterror)|Настраивает `IErrorInfo` для предоставления клиенту сведения об ошибке.|  
|[AtlThrow](debugging-and-error-reporting-global-functions.md#atlthrow)|Создает исключение `CAtlException`.|  
|[AtlThrowLastWin32](debugging-and-error-reporting-global-functions.md#atlthrowlastwin32)|Вызывайте эту функцию для сообщения об ошибке на основе результата функции Windows `GetLastError`.|  
  
##  <a name="atlhresultfromlasterror"></a>  AtlHresultFromLastError  
 Возвращает значение кода последней ошибки в вызывающем потоке в форме HRESULT.  
  
```
HRESULT AtlHresultFromLastError();
```  
  
### <a name="remarks"></a>Примечания  
 `AtlHresultFromLastError` вызовы `GetLastError` для получения последней ошибки и возвращает ошибку после его преобразования в значение HRESULT, с помощью макроса HRESULT_FROM_WIN32.  

### <a name="requirements"></a>Требования  
 **Заголовок:** atlcomcli.h  

##  <a name="atlhresultfromwin32"></a>  AtlHresultFromWin32  
 Преобразует код ошибки Win32 в HRESULT.  
  
```
AtlHresultFromWin32(DWORD error);
```  
  
### <a name="parameters"></a>Параметры  
 *Ошибка*  
 Значение ошибки, которое необходимо преобразовать.  
  
### <a name="remarks"></a>Примечания  
 Преобразует код ошибки Win32 в HRESULT, с помощью макроса HRESULT_FROM_WIN32.  
  
> [!NOTE]
>  Вместо использования `HRESULT_FROM_WIN32(GetLastError())`, используйте функцию [AtlHresultFromLastError](debugging-and-error-reporting-global-functions.md#atlhresultfromlasterror).  

### <a name="requirements"></a>Требования  
 **Заголовок:** atlcomcli.h  

##  <a name="atlreporterror"></a>  AtlReportError  
 Настраивает `IErrorInfo` интерфейс для предоставления клиенту объекта сведений об ошибке.  
  
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
 *CLSID*  
 [in] CLSID объекта с сообщением об ошибке.  
  
 *lpszDesc*  
 [in] Строка, описывающая ошибку. Указать, что версии Юникода *lpszDesc* имеет тип LPCOLESTR; версия ANSI указывает тип LPCSTR.  
  
 *IID*  
 [in] Идентификатор IID интерфейса, определяющего ошибку или GUID_NULL, если ошибки определяется операционной системой.  
  
 *hRes*  
 [in] Значение HRESULT, который вы хотите возвращается вызывающей стороне.  
  
 *nID*  
 [in] Идентификатор ресурса, где хранится строка описания ошибки. Это значение должно лежать между 0x0200 и 0xFFFF, включительно. В отладочных сборках **ASSERT** Если *nID* индекса не является допустимой строкой. Строка описания ошибки в сборках выпуска будет указано значение «Unknown Error».  
  
 *dwHelpID*  
 [in] Идентификатор контекста справки для ошибки.  
  
 *lpszHelpFile*  
 [in] Путь и имя файла справки, описывающий ошибку.  
  
 *hInst*  
 [in] Дескриптор для ресурса. По умолчанию этот параметр является `__AtlBaseModuleModule::GetResourceInstance`, где `__AtlBaseModuleModule` — это глобальный экземпляр [CAtlBaseModule](../../atl/reference/catlbasemodule-class.md) или класс, производный от него.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Если *hRes* параметр имеет ненулевое значение, возвращает значение *hRes*. Если *hRes* равно нулю, то в первых четырех версиях `AtlReportError` возвращает DISP_E_EXCEPTION. Две последние версии возвращают результат этого макроса **MAKE_HRESULT (1, FACILITY_ITF,** `nID` **)**.  
  
### <a name="remarks"></a>Примечания  
 Строка *lpszDesc* используется в качестве текстовое описание ошибки. Когда клиент получает *hRes* после возврата из `AtlReportError`, клиент может получить доступ к `IErrorInfo` структуру для получения сведений об ошибке.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATL_COM#52](../../atl/codesnippet/cpp/debugging-and-error-reporting-global-functions_1.cpp)]  
  
> [!CAUTION]
>  Не используйте `AtlReportError` обработчики catch C++. Некоторые переопределения метода этих функций использовать макросы преобразования строк ATL, который в свою очередь, используют `_alloca` внутри функции. С помощью `AtlReportError` в блоке catch C++ обработчик может привести к исключениям в обработчики catch C++.  

### <a name="requirements"></a>Требования  
 **Заголовок:** atlcom.h  
    
##  <a name="atlthrow"></a>  AtlThrow  
 Вызывайте эту функцию для сообщения об ошибке, на основе кода состояния HRESULT.  
  
```
__declspec(noreturn) inline void AtlThrow(HRESULT hr);
```  
  
### <a name="parameters"></a>Параметры  
 *hr*  
 Стандартное значение HRESULT.  
  
### <a name="remarks"></a>Примечания  
 Эта функция используется кодом библиотеки ATL и MFC, в случае ошибки. Он также может вызываться из кода. Реализация по умолчанию эта функция зависит от определения _ATL_NO_EXCEPTIONS символов и типа проекта, MFC или ATL.  
  
 В любом случае эта функция выполняет трассировку HRESULT к отладчику.  
  
 В Visual Studio 2015 с обновлением 3 и более поздних версиях эта функция используется с атрибутом __declspec(noreturn) во избежание ложных предупреждений SAL.  
  
 Если _ATL_NO_EXCEPTIONS не определен в проекте MFC, эта функция создает [CMemoryException](../../mfc/reference/cmemoryexception-class.md) или [COleException](../../mfc/reference/coleexception-class.md) на основе значения HRESULT.  
  
 Если _ATL_NO_EXCEPTIONS не определен в проекте ATL, функция создает [CAtlException](../../atl/reference/catlexception-class.md).  
  
 Если определен _ATL_NO_EXCEPTIONS, функция вызывает сбой утверждения вместо выдачи исключения.  
  
 Для проектов ATL можно предоставить собственную реализацию этой функции для использования библиотеки ATL в случае сбоя. Чтобы сделать это, определить собственную функцию с сигнатурой `AtlThrow` и #define `AtlThrow` на имя функции. Это необходимо сделать перед включением atlexcept.h (что означает, что должна быть выполнена прежде чем включать какие-либо заголовки ATL, поскольку atlbase.h включает atlexcept.h). Атрибут функции `__declspec(noreturn)` во избежание ложных предупреждений SAL.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATL_Windowing#95](../../atl/codesnippet/cpp/debugging-and-error-reporting-global-functions_2.h)]  

## <a name="requirements"></a>Требования  
 **Заголовок:** atldef.h  

##  <a name="atlthrowlastwin32"></a>  AtlThrowLastWin32  
 Вызывайте эту функцию для сообщения об ошибке на основе результата функции Windows `GetLastError`.  
  
```
inline void AtlThrowLastWin32();
```  
  
### <a name="remarks"></a>Примечания  
 Эта функция выполняет трассировку результат `GetLastError` к отладчику.  
  
 Если _ATL_NO_EXCEPTIONS не определен в проекте MFC, эта функция создает [CMemoryException](../../mfc/reference/cmemoryexception-class.md) или [COleException](../../mfc/reference/coleexception-class.md) на основе значения, возвращаемые `GetLastError`.  
  
 Если _ATL_NO_EXCEPTIONS не определен в проекте ATL, функция создает [CAtlException](../../atl/reference/catlexception-class.md).  
  
 Если определен _ATL_NO_EXCEPTIONS, функция вызывает сбой утверждения вместо выдачи исключения.  

## <a name="requirements"></a>Требования  
 **Заголовок:** atldef.h  
   
     
## <a name="see-also"></a>См. также  
 [Функции](../../atl/reference/atl-functions.md)   
 [Макросы для отладки и создания отчетов об ошибках](../../atl/reference/debugging-and-error-reporting-macros.md)









