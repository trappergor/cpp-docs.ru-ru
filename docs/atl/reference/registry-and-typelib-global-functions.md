---
title: "Глобальные функции реестра и библиотеки типов | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- RegistryDataExchange function, global functions
ms.assetid: d58b8a4e-975c-4417-8b34-d3c847f679b3
caps.latest.revision: 22
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: d2d39abf526a58b8442107b5ee816f316ae841f5
ms.openlocfilehash: 9f05db468d5d7fffce149d7a92ba29615c3ae7c1
ms.contentlocale: ru-ru
ms.lasthandoff: 03/31/2017

---
# <a name="registry-and-typelib-global-functions"></a>Глобальные функции реестра и библиотеки типов
Эти функции обеспечивают поддержку для загрузки и регистрации библиотеки типов.  
  
> [!IMPORTANT]
>  Функции, перечисленные в следующих таблицах не может использоваться в приложениях, выполняемых в [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)].  
  
|||  
|-|-|  
|[AfxRegCreateKey](#afxrefcreatekey)|Создает указанный раздел реестра.|
|[AfxRegDeleteKey](#afxrefdeletekey)|Удаляет указанный раздел реестра.|
|[AfxRegisterPreviewHandler](#afxregisterpreviewhandler)|Вспомогательный класс для регистрации обработчика предварительного просмотра.|
|[AfxUnregisterPreviewHandler](#afxunregisterpreviewhandler)| Вспомогательный класс для отмены регистрации обработчика предварительного просмотра. |
|[AtlRegisterTypeLib](#atlregistertypelib)|Эта функция вызывается для регистрации библиотеки типов.|  
|[AtlUnRegisterTypeLib](#atlunregistertypelib)|Эта функция вызывается для отмены регистрации библиотеки типов|  
|[AfxRegOpenKey](#afxregopenkey)|Открывает указанный раздел реестра.|
|[AfxRegOpenKeyEx](#afxregopenkeyex)|Открывает указанный раздел реестра.|
|[AtlLoadTypeLib](#atlloadtypelib)|Эта функция вызывается для загрузки библиотеки типов.|  
|[AtlUpdateRegistryFromResourceD](#atlupdateregistryfromresourced)|Эта функция вызывается для обновления реестра из предоставленного ресурса.|  
|[RegistryDataExchange](#registrydataexchange)|Эта функция вызывается для чтения из системного реестра или записи в него. Вызывается методом [макросы обмена данными реестра](../../atl/reference/registry-data-exchange-macros.md).|  
  
 Эти функции управления какой из узлов в реестре, программа использует для хранения данных.  
  
|||  
|-|-|  
|[AtlGetPerUserRegistration](#atlgetperuserregistration)|Возвращает значение, перенаправляет ли приложение доступ к реестру на **HKEY_CURRENT_USER** ( **HKCU**) узла.|  
|[AtlSetPerUserRegistration](#atlsetperuserregistration)|Задает, перенаправляет ли приложение доступ к реестру на **HKEY_CURRENT_USER** ( **HKCU**) узла.|  

### <a name="requirements"></a>Требования  
 **Заголовок:** atlbase.h

## <a name="atlgetperuserregistration"></a>AtlGetPerUserRegistration
Эта функция используется для определения, перенаправляет ли приложение доступ к реестру на **HKEY_CURRENT_USER** (**HKCU**) узла.  
  
### <a name="syntax"></a>Синтаксис  
  
```  
ATLINLINE ATLAPI AtlGetPerUserRegistration(bool* pEnabled);  
```  
  
### <a name="parameters"></a>Параметры  
 [выходной] `pEnabled`  
 `TRUE`Указывает, что данные реестра, направляются **HKCU** узла; `FALSE` указывает, что приложение записывает данные реестра узла по умолчанию. Узел по умолчанию является **HKEY_CLASSES_ROOT** (**HKCR**).  
  
### <a name="return-value"></a>Возвращаемое значение  
 `S_OK`Если метод выполнен успешно, в противном случае `HRESULT` код ошибки, если произошла ошибка.  
  
### <a name="remarks"></a>Примечания  
 Перенаправление системного реестра не включен по умолчанию. Если этот параметр включен, доступ к реестру перенаправляется **HKEY_CURRENT_USER\Software\Classes**.  
  
 Перенаправление не является общим. Только платформы MFC и ATL, подвержены перенаправления реестра.  
  
### <a name="requirements"></a>Требования  
 **Заголовок:** atlbase.h  

 ## <a name="afxregcreatekey"></a>AfxRegCreateKey
 Создает указанный раздел реестра.  
  
### <a name="syntax"></a>Синтаксис  
  
```  
LONG AFXAPI AfxRegCreateKey(HKEY hKey, LPCTSTR lpSubKey, PHKEY phkResult, CAtlTransactionManager* pTM = NULL);  
```  
  
### <a name="parameters"></a>Параметры  
 `hKey`  
 Дескриптор, чтобы открыть раздел реестра.  
  
 `lpSubKey`  
 Имя ключа, который открывает эту функцию, или создает.  
  
 `phkResult`  
 Указатель на переменную, которая получает дескриптор открытого или созданный ключ.  
  
 `pTM`  
 Указатель на `CAtlTransactionManager` объект.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Если функция выполняется успешно, возвращаемое значение равно ERROR_SUCCESS. Если функция завершается с ошибкой, возвращается код ненулевое значение ошибки, определенные в файле Winerror.h.  

### <a name="requirements"></a>Требования  
 **Заголовок:** afxpriv.h  

## <a name="afxregdeletekey"></a>AfxRegDeleteKey
Удаляет указанный раздел реестра.  
  
### <a name="syntax"></a>Синтаксис  
  
```  
LONG AFXAPI AfxRegDeleteKey(HKEY hKey, LPCTSTR lpSubKey, CAtlTransactionManager* pTM = NULL);  
```  
  
### <a name="parameters"></a>Параметры  
 `hKey`  
 Дескриптор, чтобы открыть раздел реестра.  
  
 `lpSubKey`  
 Имя ключа для удаления.  
  
 `pTM`  
 Указатель на `CAtlTransactionManager` объект.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Если функция выполняется успешно, возвращаемое значение равно ERROR_SUCCESS. Если функция завершается с ошибкой, возвращается код ненулевое значение ошибки, определенные в файле Winerror.h.  
  
### <a name="requirements"></a>Требования  
 **Заголовок:** afxpriv.h  

## <a name="afxregisterpreviewhandler"></a>
Вспомогательный класс для регистрации обработчика предварительного просмотра.  
  
### <a name="syntax"></a>Синтаксис  
  
```  
BOOL AFXAPI AfxRegisterPreviewHandler(LPCTSTR lpszCLSID, LPCTSTR lpszShortTypeName, LPCTSTR lpszFilterExt);  
```  
  
### <a name="parameters"></a>Параметры  
 `lpszCLSID`  
 Указывает идентификатор CLSID обработчика.  
  
 `lpszShortTypeName`  
 Указывает идентификатор ProgID обработчика.  
  
 `lpszFilterExt`  
 Указывает расширение файла зарегистрировано с данным дескриптором.  
  
### <a name="requirements"></a>Требования  
 **Заголовок:** afxdisp.h   

##  <a name="atlregistertypelib"></a>AtlRegisterTypeLib  
 Эта функция вызывается для регистрации библиотеки типов.  
  
  
```
ATLAPI AtlRegisterTypeLib(HINSTANCE hInstTypeLib, LPCOLESTR lpszIndex);
```  
  
### <a name="parameters"></a>Параметры  
 `hInstTypeLib`  
 Дескриптор экземпляра модуля.  
  
 `lpszIndex`  
 Строка в формате «\\\N», где N — целочисленный индекс ресурса библиотеки типов. Может иметь значение NULL, если индекс не является обязательным.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение S_OK в случае успешного выполнения или ошибку HRESULT при сбое.  
  
### <a name="remarks"></a>Примечания  
 Эта вспомогательная функция используемой [AtlComModuleUnregisterServer](server-registration-global-functions.md#atlcommoduleunregisterserver) и [CAtlComModule::RegisterTypeLib](../../atl/reference/catlcommodule-class.md#registertypelib).  
### <a name="requirements"></a>Требования  
 **Заголовок:** atlbase.h

 ## <a name="afxregopenkey"></a>AfxRegOpenKey
 Открывает указанный раздел реестра.  
  
### <a name="syntax"></a>Синтаксис  
  
```  
LONG AFXAPI AfxRegOpenKey(HKEY hKey, LPCTSTR lpSubKey, PHKEY phkResult, CAtlTransactionManager* pTM = NULL);  
```  
  
### <a name="parameters"></a>Параметры  
 `hKey`  
 Дескриптор, чтобы открыть раздел реестра.  
  
 `lpSubKey`  
 Имя ключа, который открывает эту функцию, или создает.  
  
 `phkResult`  
 Указатель на переменную, которая получает дескриптор созданный ключ.  
  
 `pTM`  
 Указатель на `CAtlTransactionManager` объект.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Если функция выполняется успешно, возвращаемое значение равно ERROR_SUCCESS. Если функция завершается с ошибкой, возвращается код ненулевое значение ошибки, определенные в файле Winerror.h.  
  
### <a name="requirements"></a>Требования  
 **Заголовок:** afxpriv.h  

## <a name="afxregopenkeyex"></a>AfxRegOpenKeyEx
Открывает указанный раздел реестра. 

### <a name="syntax"></a>Синтаксис  
  
```  
LONG AFXAPI AfxRegOpenKeyEx(HKEY hKey, LPCTSTR lpSubKey, DWORD ulOptions, REGSAM samDesired, PHKEY phkResult, CAtlTransactionManager* pTM = NULL);  
```  
  
### <a name="parameters"></a>Параметры  
 `hKey`  
 Дескриптор, чтобы открыть раздел реестра.  
  
 `lpSubKey`  
 Имя ключа, который открывает эту функцию, или создает.  
  
 `ulOptions`  
 Этот параметр зарезервирован и должен быть равен нулю.  
  
 `samDesired`  
 Маска, указывающая требуемые права доступа к ключу.  
  
 `phkResult`  
 Указатель на переменную, которая получает дескриптор открытого ключа.  
  
 `pTM`  
 Указатель на `CAtlTransactionManager` объект.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Если функция выполняется успешно, возвращаемое значение равно ERROR_SUCCESS. Если функция завершается с ошибкой, возвращается код ненулевое значение ошибки, определенные в файле Winerror.h.  
  
### <a name="requirements"></a>Требования  
 **Заголовок:** afxpriv.h  

 ## <a name="afxunregisterpreviewhandler"></a>AfxUnregisterPreviewHandler
 Вспомогательный класс для отмены регистрации обработчика предварительного просмотра.  
  
### <a name="syntax"></a>Синтаксис  
  
```  
BOOL AFXAPI AfxUnRegisterPreviewHandler(LPCTSTR lpszCLSID);  
```  
  
### <a name="parameters"></a>Параметры  
 `lpszCLSID`  
 Указывает идентификатор CLSID для отмены регистрации обработчика.  
  
### <a name="requirements"></a>Требования  
 **Заголовок:** afxdisp.h  

## <a name="atlsetperuserregistration"></a>AtlSetPerUserRegistration
Задает, перенаправляет ли приложение доступ к реестру на **HKEY_CURRENT_USER** (**HKCU**) узла.  
  
### <a name="syntax"></a>Синтаксис  
  
```  
ATLINLINE ATLAPI AtlSetPerUserRegistration(bool bEnable);  
```  
  
### <a name="parameters"></a>Параметры  
 [in] `bEnable`  
 `TRUE`Указывает, что данные реестра, направляются **HKCU** узла; `FALSE` указывает, что приложение записывает данные реестра узла по умолчанию. Узел по умолчанию является **HKEY_CLASSES_ROOT** (**HKCR**).  
  
### <a name="return-value"></a>Возвращаемое значение  
 `S_OK`Если метод выполнен успешно, в противном случае `HRESULT` код ошибки, если произошла ошибка.  
  
### <a name="remarks"></a>Примечания  
 Перенаправление системного реестра не включен по умолчанию. Если этот параметр включен, доступ к реестру перенаправляется **HKEY_CURRENT_USER\Software\Classes**.  
  
 Перенаправление не является общим. Только платформы MFC и ATL, подвержены перенаправления реестра.  
### <a name="requirements"></a>Требования  
 **Заголовок:** atlbase.h  

##  <a name="atlunregistertypelib"></a>AtlUnRegisterTypeLib  
 Эта функция вызывается для отмены регистрации библиотеки типов.  
  
### <a name="syntax"></a>Синтаксис  
```
ATLAPI AtlUnRegisterTypeLib(
    HINSTANCE hInstTypeLib, 
    LPCOLESTR lpszIndex);
```  
  
### <a name="parameters"></a>Параметры  
 `hInstTypeLib`  
 Дескриптор экземпляра модуля.  
  
 `lpszIndex`  
 Строка в формате «\\\N», где N — целочисленный индекс ресурса библиотеки типов. Может иметь значение NULL, если индекс не является обязательным.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение S_OK в случае успешного выполнения или ошибку HRESULT при сбое.  
  
### <a name="remarks"></a>Примечания  
 Эта вспомогательная функция используемой [CAtlComModule::UnRegisterTypeLib](../../atl/reference/catlcommodule-class.md#unregistertypelib) и [AtlComModuleUnregisterServer](#atlcommoduleunregisterserver).  
### <a name="requirements"></a>Требования  
 **Заголовок:** atlbase.h

##  <a name="atlloadtypelib"></a>AtlLoadTypeLib  
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
 `hInstTypeLib`  
 Дескриптор модуля, связанных с библиотекой типов.  
  
 `lpszIndex`  
 Строка в формате «\\\N», где N — целочисленный индекс ресурса библиотеки типов. Может иметь значение NULL, если индекс не является обязательным.  
  
 *pbstrPath*  
 При удачном возвращении содержит полный путь к модулю, связанных с библиотекой типов.  
  
 `ppTypeLib`  
 При удачном возвращении содержит указатель на указатель на библиотеку типов для загрузки.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение S_OK в случае успешного выполнения или ошибку HRESULT при сбое.  
  
### <a name="remarks"></a>Примечания  
 Эта вспомогательная функция используемой [AtlRegisterTypeLib](#atlregistertypelib) и [AtlUnRegisterTypeLib](#atlunregistertypelib).  
  
##  <a name="atlupdateregistryfromresourced"></a>AtlUpdateRegistryFromResourceD  
 Эта функция объявлена устаревшей Visual Studio 2013 и удалена в Visual Studio 2015.  
  
```
<removed>
```  
  

  
##  <a name="registrydataexchange"></a>RegistryDataExchange  
 Эта функция вызывается для чтения из системного реестра или записи в него.  

### <a name="syntax"></a>Синтаксис  
```
HRESULT RegistryDataExchange(
    T* pT,
    enum RDXOperations rdxOp,
    void* pItem = NULL);
```  
  
### <a name="parameters"></a>Параметры  
 *pT*  
 Указатель на текущий объект.  
  
 *rdxOp*  
 Значение перечисления, указывающее, какую операцию следует выполнять функции. См. в разделе "Примечания" разрешенные значения в таблице.  
  
 `pItem`  
 Указатель на данные, чтение и запись реестра. Данные также может представлять ключа должна быть удалена из реестра. Значение по умолчанию — NULL.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение S_OK в случае успешного выполнения или ошибку HRESULT при сбое.  
  
### <a name="remarks"></a>Примечания  
 Макросы [BEGIN_RDX_MAP](registry-data-exchange-macros.md#begin_rdx_map) и [END_RDX_MAP](registry-data-exchange-macros.md#end_rdx_map) разверните функцию, которая вызывает `RegistryDataExchange`.  
  
 Возможных значений перечисления, указывающие, что необходимо выполнить операцию функции показаны в следующей таблице:  
  
|Значение перечисления|Операция|  
|----------------|---------------|  
|eReadFromReg|Чтение данных из реестра.|  
|eWriteToReg|Запись данных в реестр.|  
|eDeleteFromReg|Удалите раздел реестра.|  
  
### <a name="requirements"></a>Требования  
 **Заголовок:** atlbase.h

## <a name="see-also"></a>См. также  
 [Функции](atl-functions.md)
 [обмена данными реестра макросы](registry-data-exchange-macros.md)






