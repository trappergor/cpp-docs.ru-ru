---
title: "Отладка и глобальные функции отчетов об ошибках | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- functions [ATL], error reporting
ms.assetid: 11339c02-98cd-428d-b3b9-7deeb155a6a3
caps.latest.revision: 17
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: 604a4bf49490ad2599c857eb3afd527d67e1e25b
ms.openlocfilehash: 4a412910d13d10606080c14412d33d2b614fdcec
ms.lasthandoff: 02/24/2017

---
# <a name="debugging-and-error-reporting-global-functions"></a>Отладка и глобальные функции отчетов об ошибках
Эти функции предоставляют полезные средства отладки и трассировки.  
  
|||  
|-|-|  
|[AtlHresultFromLastError](http://msdn.microsoft.com/library/74530d7d-3c91-484c-acf3-aff755715d66)|Возвращает `GetLastError` код ошибки в форме HRESULT.|  
|[AtlHresultFromWin32](http://msdn.microsoft.com/library/63add2dd-274c-4e72-a98c-040b93413a2f)|Преобразует код ошибки Win32 в HRESULT.|  
|[AtlReportError](http://msdn.microsoft.com/library/86b046a5-ea18-4ecf-9aab-40fc1eab847c)|Настраивает **IErrorInfo** для предоставления клиенту сведения об ошибке.|  
|[AtlThrow](http://msdn.microsoft.com/library/2bd111da-8170-488d-914a-c9bf6b6765f7)|Создает исключение `CAtlException`.|  
|[AtlThrowLastWin32](http://msdn.microsoft.com/library/8bce8e56-c7cd-4ebb-8c62-80ebc63a3d07)|Вызывайте эту функцию для сообщения об ошибке на основе результата функции Windows `GetLastError`.|  
  
##  <a name="a-nameatlhresultfromlasterrora--atlhresultfromlasterror"></a><a name="atlhresultfromlasterror"></a>AtlHresultFromLastError  
 Возвращает значение кода последней ошибки в вызывающем потоке в форме HRESULT.  
  
```
HRESULT AtlHresultFromLastError();
```  
  
### <a name="remarks"></a>Примечания  
 `AtlHresultFromLastError`вызовы `GetLastError` для получения последней ошибки и возвращает ошибку, после его преобразования в значение HRESULT с помощью **HRESULT_FROM_WIN32** макрос.  

### <a name="requirements"></a>Требования  
 **Заголовок:** atlcomcli.h  

##  <a name="a-nameatlhresultfromwin32a--atlhresultfromwin32"></a><a name="atlhresultfromwin32"></a>AtlHresultFromWin32  
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
>  Вместо использования **HRESULT_FROM_WIN32(GetLastError())**, используйте функцию [AtlHresultFromLastError](http://msdn.microsoft.com/library/74530d7d-3c91-484c-acf3-aff755715d66).  

### <a name="requirements"></a>Требования  
 **Заголовок:** atlcomcli.h  

##  <a name="a-nameatlreporterrora--atlreporterror"></a><a name="atlreporterror"></a>AtlReportError  
 Настраивает `IErrorInfo` интерфейс, чтобы предоставить сведения об ошибке клиентам объекта.  
  
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
 [in] Идентификатор CLSID объекта сообщает об ошибке.  
  
 `lpszDesc`  
 [in] Строка, описывающая ошибку. Укажите версии Юникода, `lpszDesc` типа **LPCOLESTR**; тип в формате ANSI `LPCSTR`.  
  
 `iid`  
 [in] Идентификатор IID интерфейса, определение ошибки или `GUID_NULL` при ошибке определяется операционной системой.  
  
 `hRes`  
 [in] `HRESULT` Требуется возвращается вызывающему.  
  
 `nID`  
 [in] Идентификатор ресурса, где хранится строка описания ошибки. Это значение должно находиться между 0x0200 и 0xFFFF включительно. В отладочных построениях **ASSERT** Если это приведет к `nID` индекса не является допустимой строкой. В сборке выпуска строку описания ошибки будет присвоено «Неизвестная ошибка».  
  
 `dwHelpID`  
 [in] Идентификатор контекста справки для ошибки.  
  
 `lpszHelpFile`  
 [in] Путь и имя файла справки, описывающий ошибку.  
  
 `hInst`  
 [in] Дескриптор для ресурса. По умолчанию этот параметр является **__AtlBaseModuleModule::GetResourceInstance**, где **__AtlBaseModuleModule** — глобальный экземпляр [CAtlBaseModule](../../atl/reference/catlbasemodule-class.md) или класс, производный от него.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Если `hRes` параметр имеет ненулевое значение, возвращает значение `hRes`. Если `hRes` равно нулю, то первые четыре версии `AtlReportError` вернуть `DISP_E_EXCEPTION`. Последние две версии возвращают результат макрос **MAKE_HRESULT (1, FACILITY_ITF,** `nID` **)**.  
  
### <a name="remarks"></a>Примечания  
 Строка *lpszDesc* используется как текстовое описание ошибки. Когда клиент получает `hRes` возврата из `AtlReportError`, клиент может обращаться к **IErrorInfo** структуры подробные сведения об ошибке.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATL_COM&#52;](../../atl/codesnippet/cpp/debugging-and-error-reporting-global-functions_1.cpp)]  
  
> [!CAUTION]
>  Не используйте `AtlReportError` обработчики catch C++. Некоторые переопределения этих функций использовать макросы преобразования строк ATL, который в свою очередь использовать `_alloca` внутри функции. С помощью `AtlReportError` в блоке catch C++ обработчик может привести к исключениям в обработчиках catch C++.  

### <a name="requirements"></a>Требования  
 **Заголовок:** файле atlcom.h  
    
##  <a name="a-nameatlthrowa--atlthrow"></a><a name="atlthrow"></a>AtlThrow  
 Вызывайте эту функцию для сообщения об ошибке на основе кода состояния `HRESULT`.  
  
```
__declspec(noreturn) inline void AtlThrow(HRESULT hr);
```  
  
### <a name="parameters"></a>Параметры  
 `hr`  
 Стандартное значение HRESULT.  
  
### <a name="remarks"></a>Примечания  
 Эта функция используется кодом библиотеки ATL и MFC в случае ошибки. Он также может вызываться из собственного кода. Реализация по умолчанию эта функция зависит от определения символа **_ATL_NO_EXCEPTIONS** и от типа проекта, MFC или библиотеки ATL.  
  
 Во всех случаях эта функция отслеживает HRESULT в отладчик.  
  
 В Visual Studio 2015 г. обновление 3 и более поздних версий эта функция является атрибутом __declspec(noreturn) во избежание ложных предупреждений SAL.  
  
 Если **_ATL_NO_EXCEPTIONS** не определен в проекте MFC, эта функция вызывает [CMemoryException](../../mfc/reference/cmemoryexception-class.md) или [COleException](../../mfc/reference/coleexception-class.md) на основе значения HRESULT.  
  
 Если **_ATL_NO_EXCEPTIONS** не определен в проекте ATL, функция создает [CAtlException](../../atl/reference/catlexception-class.md).  
  
 Если **_ATL_NO_EXCEPTIONS** будет определено, функция вызывает сбой утверждения, вместо вызова исключения.  
  
 Для проектов ATL можно предоставить собственную реализацию этой функции для использования библиотеки ATL в случае сбоя. Для этого, определите собственную функцию с такой же сигнатурой, как `AtlThrow` и #define `AtlThrow` на имя функции. Это необходимо сделать перед включением atlexcept.h (что означает, что должно быть выполнено до включая заголовки ATL, поскольку atlbase.h включает atlexcept.h). Атрибут функции `__declspec(noreturn)` во избежание ложных предупреждений SAL.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATL_Windowing&#95;](../../atl/codesnippet/cpp/debugging-and-error-reporting-global-functions_2.h)]  

## <a name="requirements"></a>Требования  
 **Заголовок:** atldef.h  

##  <a name="a-nameatlthrowlastwin32a--atlthrowlastwin32"></a><a name="atlthrowlastwin32"></a>AtlThrowLastWin32  
 Вызывайте эту функцию для сообщения об ошибке на основе результата функции Windows `GetLastError`.  
  
```
inline void AtlThrowLastWin32();
```  
  
### <a name="remarks"></a>Примечания  
 Эта функция трассировки результат `GetLastError` в отладчик.  
  
 Если **_ATL_NO_EXCEPTIONS** не определен в проекте MFC, эта функция вызывает [CMemoryException](../../mfc/reference/cmemoryexception-class.md) или [COleException](../../mfc/reference/coleexception-class.md) на основе значения, возвращаемые `GetLastError`.  
  
 Если **_ATL_NO_EXCEPTIONS** не определен в проекте ATL, функция создает [CAtlException](../../atl/reference/catlexception-class.md).  
  
 Если **_ATL_NO_EXCEPTIONS** будет определено, функция вызывает сбой утверждения, вместо вызова исключения.  

## <a name="requirements"></a>Требования  
 **Заголовок:** atldef.h  
   
     
## <a name="see-also"></a>См. также  
 [Функции](../../atl/reference/atl-functions.md)   
 [Макросы отладки и сообщения об ошибках](../../atl/reference/debugging-and-error-reporting-macros.md)










