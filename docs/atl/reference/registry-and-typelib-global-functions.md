---
title: "Глобальные функции реестра и TypeLib | Документы Microsoft"
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
translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 9d454f2eac1b29785fe40a480fc43c7c34a861a3
ms.lasthandoff: 02/24/2017

---
# <a name="registry-and-typelib-global-functions"></a>Глобальные функции реестра и библиотеки типов
Эти функции обеспечивают поддержку для загрузки и регистрации библиотеки типов.  
  
> [!IMPORTANT]
>  Функции, перечисленные в следующих таблицах не может использоваться в приложениях, выполняемых в [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)].  
  
|||  
|-|-|  
|[AtlRegisterTypeLib](#atlregistertypelib)|Эта функция вызывается для регистрации библиотеки типов.|  
|[AtlUnRegisterTypeLib](#atlunregistertypelib)|Эта функция вызывается для отмены регистрации библиотеки типов|  
|[AtlLoadTypeLib](#atlloadtypelib)|Эта функция вызывается для загрузки библиотеки типов.|  
|[AtlUpdateRegistryFromResourceD](#atlupdateregistryfromresourced)|Эта функция вызывается для обновления реестра из предоставленного ресурса.|  
|[RegistryDataExchange](#registrydataexchange)|Эта функция вызывается для чтения из системного реестра или записи в него. Вызывается методом [макросы обмена данными реестра](../../atl/reference/registry-data-exchange-macros.md).|  
  
 Эти функции управления узла в реестре, программа использует для хранения информации.  
  
|||  
|-|-|  
|[AtlGetPerUserRegistration](#atlgetperuserregistration)|Извлекает перенаправляет ли приложение доступ к реестру на **HKEY_CURRENT_USER** ( **HKCU**) узла.|  
|[AtlSetPerUserRegistration](#atlsetperuserregistration)|Задает, перенаправляет ли приложение доступ к реестру на **HKEY_CURRENT_USER** ( **HKCU**) узла.|  

### <a name="requirements"></a>Требования  
 **Заголовок:** atlbase.h

## <a name="a-nameatlgetperuserregistrationa-atlgetperuserregistration"></a><a name="atlgetperuserregistration"></a>AtlGetPerUserRegistration
Эта функция используется для определения, перенаправляет ли приложение доступ к реестру на **HKEY_CURRENT_USER** (**HKCU**) узла.  
  
### <a name="syntax"></a>Синтаксис  
  
```  
ATLINLINE ATLAPI AtlGetPerUserRegistration(bool* pEnabled);  
```  
  
### <a name="parameters"></a>Параметры  
 [выходной] `pEnabled`  
 `TRUE`Указывает, что данные реестра, направляются **HKCU** узла; `FALSE` указывает, что приложение записывает данные реестра в узел по умолчанию. Узел по умолчанию является **HKEY_CLASSES_ROOT** (**HKCR**).  
  
### <a name="return-value"></a>Возвращаемое значение  
 `S_OK`Если метод выполнен успешно, в противном случае `HRESULT` код ошибки, если происходит ошибка.  
  
### <a name="remarks"></a>Примечания  
 Перенаправление системного реестра не включена по умолчанию. Если этот параметр включен, доступ к реестру перенаправляется к **HKEY_CURRENT_USER\Software\Classes**.  
  
 Перенаправление не является общим. Только платформы MFC и ATL, подвержены перенаправления реестра.  
  
### <a name="requirements"></a>Требования  
 **Заголовок:** atlbase.h  

##  <a name="a-nameatlregistertypeliba--atlregistertypelib"></a><a name="atlregistertypelib"></a>AtlRegisterTypeLib  
 Эта функция вызывается для регистрации библиотеки типов.  
  
  
```
ATLAPI AtlRegisterTypeLib(HINSTANCE hInstTypeLib, LPCOLESTR lpszIndex);
```  
  
### <a name="parameters"></a>Параметры  
 `hInstTypeLib`  
 Дескриптор экземпляра модуля.  
  
 `lpszIndex`  
 Строка в формате «\\\N», где N — целочисленный индекс библиотеки типов ресурсов. Может иметь значение NULL, если индекс не является обязательным.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение S_OK в случае успешного выполнения или значение HRESULT ошибки в случае сбоя.  
  
### <a name="remarks"></a>Примечания  
 Эта вспомогательная функция используемой [AtlComModuleUnregisterServer](server-registration-global-functions.md#atlcommoduleunregisterserver) и [CAtlComModule::RegisterTypeLib](../../atl/reference/catlcommodule-class.md#registertypelib).  
### <a name="requirements"></a>Требования  
 **Заголовок:** atlbase.h

## <a name="a-nameatlsetperuserregistrationa-atlsetperuserregistration"></a><a name="atlsetperuserregistration"></a>AtlSetPerUserRegistration
Задает, перенаправляет ли приложение доступ к реестру на **HKEY_CURRENT_USER** (**HKCU**) узла.  
  
### <a name="syntax"></a>Синтаксис  
  
```  
ATLINLINE ATLAPI AtlSetPerUserRegistration(bool bEnable);  
```  
  
### <a name="parameters"></a>Параметры  
 [in] `bEnable`  
 `TRUE`Указывает, что данные реестра, направляются **HKCU** узла; `FALSE` указывает, что приложение записывает данные реестра в узел по умолчанию. Узел по умолчанию является **HKEY_CLASSES_ROOT** (**HKCR**).  
  
### <a name="return-value"></a>Возвращаемое значение  
 `S_OK`Если метод выполнен успешно, в противном случае `HRESULT` код ошибки, если происходит ошибка.  
  
### <a name="remarks"></a>Примечания  
 Перенаправление системного реестра не включена по умолчанию. Если этот параметр включен, доступ к реестру перенаправляется к **HKEY_CURRENT_USER\Software\Classes**.  
  
 Перенаправление не является общим. Только платформы MFC и ATL, подвержены перенаправления реестра.  
### <a name="requirements"></a>Требования  
 **Заголовок:** atlbase.h  

##  <a name="a-nameatlunregistertypeliba--atlunregistertypelib"></a><a name="atlunregistertypelib"></a>AtlUnRegisterTypeLib  
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
 Строка в формате «\\\N», где N — целочисленный индекс библиотеки типов ресурсов. Может иметь значение NULL, если индекс не является обязательным.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение S_OK в случае успешного выполнения или значение HRESULT ошибки в случае сбоя.  
  
### <a name="remarks"></a>Примечания  
 Эта вспомогательная функция используемой [CAtlComModule::UnRegisterTypeLib](../../atl/reference/catlcommodule-class.md#unregistertypelib) и [AtlComModuleUnregisterServer](#atlcommoduleunregisterserver).  
### <a name="requirements"></a>Требования  
 **Заголовок:** atlbase.h

##  <a name="a-nameatlloadtypeliba--atlloadtypelib"></a><a name="atlloadtypelib"></a>AtlLoadTypeLib  
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
 Строка в формате «\\\N», где N — целочисленный индекс библиотеки типов ресурсов. Может иметь значение NULL, если индекс не является обязательным.  
  
 *pbstrPath*  
 При удачном возвращении содержит полный путь к модулю, связанных с библиотекой типов.  
  
 `ppTypeLib`  
 При удачном возвращении содержит указатель на указатель на библиотеки типов для загрузки.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение S_OK в случае успешного выполнения или значение HRESULT ошибки в случае сбоя.  
  
### <a name="remarks"></a>Примечания  
 Эта вспомогательная функция используемой [AtlRegisterTypeLib](#atlregistertypelib) и [AtlUnRegisterTypeLib](#atlunregistertypelib).  
  
##  <a name="a-nameatlupdateregistryfromresourceda--atlupdateregistryfromresourced"></a><a name="atlupdateregistryfromresourced"></a>AtlUpdateRegistryFromResourceD  
 Эта функция объявлена устаревшей Visual Studio 2013 и удалена в Visual Studio 2015.  
  
```
<removed>
```  
  
### <a name="parameters"></a>Параметры  
  
### <a name="return-value"></a>Возвращаемое значение  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-nameregistrydataexchangea--registrydataexchange"></a><a name="registrydataexchange"></a>RegistryDataExchange  
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
 Значение перечисления, указывающее, какую операцию следует выполнять функцию. См. в таблице в разделе примечаний для допустимых значений.  
  
 `pItem`  
 Указатель на данные, чтение и запись в реестр. Данные также может представлять ключ для удаления из реестра. Значение по умолчанию — NULL.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение S_OK в случае успешного выполнения или значение HRESULT ошибки в случае сбоя.  
  
### <a name="remarks"></a>Примечания  
 Макросы [BEGIN_RDX_MAP](registry-data-exchange-macros.md#begin_rdx_map) и [END_RDX_MAP](registry-data-exchange-macros.md#end_rdx_map) разверните функцию, которая вызывает `RegistryDataExchange`.  
  
 Возможных значений перечисления, обозначающие, что необходимо выполнить операцию функции показаны в следующей таблице:  
  
|Значение перечисления|Операция|  
|----------------|---------------|  
|eReadFromReg|Чтение данных из реестра.|  
|eWriteToReg|Запись данных в реестр.|  
|eDeleteFromReg|Удалите из реестра.|  
  
### <a name="requirements"></a>Требования  
 **Заголовок:** atlbase.h

## <a name="see-also"></a>См. также  
 [Функции](atl-functions.md)
 [обмена данными реестра макросы](registry-data-exchange-macros.md)






