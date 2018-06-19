---
title: Макросы обмена данными реестра | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- atlplus/ATL::BEGIN_RDX_MAP
- atlplus/ATL::END_RDX_MAP
- atlplus/ATL::RDX_BINARY
- atlplus/ATL::RDX_CSTRING_TEXT
- atlplus/ATL::RDX_DWORD
- atlplus/ATL::RDX_TEXT
dev_langs:
- C++
helpviewer_keywords:
- RegistryDataExchange function, macros
ms.assetid: c1bc5e79-2307-43d2-9d10-3a62ffadf473
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 62a26e8d602010ce637114464a844d2f95e635c9
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32363062"
---
# <a name="registry-data-exchange-macros"></a>Макросы Exchange данных реестра
Эти макросы операции обмена данными реестра.  
  
|||  
|-|-|  
|[BEGIN_RDX_MAP](#begin_rdx_map)|Отмечает начало карты обмен данными реестра.|  
|[END_RDX_MAP](#end_rdx_map)|Отмечает конец карты обмен данными реестра.|  
|[RDX_BINARY](#rdx_binary)|Связывает указанный параметр с переменной указанный член типа BYTE.|  
|[RDX_CSTRING_TEXT](#rdx_cstring_text)|Связывает указанный параметр с переменной типа CString заданного элемента.|  
|[RDX_DWORD](#rdx_dword)|Связывает указанный параметр с переменной указанный член типа DWORD.|  
|[RDX_TEXT](#rdx_text)|Связывает указанный параметр с переменной типа TCHAR заданного элемента.|  

## <a name="requirements"></a>Требования  
 **Заголовок:** atlplus.h  
   
##  <a name="begin_rdx_map"></a>  BEGIN_RDX_MAP  
 Отмечает начало карты обмен данными реестра.  
  
```
BEGIN_RDX_MAP
```  
  
### <a name="remarks"></a>Примечания  
 Следующие макросы, используемые в схеме обмена данными реестра для чтения и записи в системном реестре.  
  
|Макрос|Описание|  
|-----------|-----------------|  
|[RDX_BINARY](#rdx_binary)|Связывает указанный параметр с переменной указанный член типа BYTE.|  
|[RDX_DWORD](#rdx_dword)|Связывает указанный параметр с переменной указанный член типа DWORD.|  
|[RDX_CSTRING_TEXT](#rdx_cstring_text)|Связывает указанный параметр с переменной типа CString заданного элемента.|  
|[RDX_TEXT](#rdx_text)|Связывает указанный параметр с переменной типа TCHAR заданного элемента.|  
  
 Глобальная функция [RegistryDataExchange](../../atl/reference/registry-and-typelib-global-functions.md#registrydataexchange), или функция-член с тем же именем, созданные `BEGIN_RDX_MAP` и `END_RDX_MAP` макросов, можно использовать всякий раз, когда код должен для обмена данными между системного реестра и переменные, заданные в схеме RDX.  
  
##  <a name="end_rdx_map"></a>  END_RDX_MAP  
 Отмечает конец карты обмен данными реестра.  
  
```
END_RDX_MAP
```  
  
##  <a name="rdx_binary"></a>  RDX_BINARY  
 Связывает указанный параметр с переменной указанный член типа BYTE.  
  
```
RDX_BINARY(
    rootkey, 
    subkey, 
    valuename, 
    member, 
    member_size )
```  
  
### <a name="parameters"></a>Параметры  
 `rootkey`  
 Корневого раздела реестра.  
  
 `subkey`  
 Подраздел реестра.  
  
 `valuename`  
 Раздел реестра.  
  
 `member`  
 Переменная члена для связи с указанным реестра.  
  
 `member_size`  
 Размер в байтах в переменной-члена.  
  
### <a name="remarks"></a>Примечания  
 Этот макрос используется в сочетании с `BEGIN_RDX_MAP` и `END_RDX_MAP` макросы, чтобы связать переменную-член с записью реестра. Глобальная функция [RegistryDataExchange](../../atl/reference/registry-and-typelib-global-functions.md#registrydataexchange), или функция-член с тем же именем, созданные `BEGIN_RDX_MAP` и `END_RDX_MAP` макросы, следует использовать для выполнения обмен данными между системного реестра и элемент переменные в RDX карты.  
  
##  <a name="rdx_cstring_text"></a>  RDX_CSTRING_TEXT  
 Связывает указанный параметр с переменной типа CString заданного элемента.  
  
```
RDX_CSTRING_TEXT(
    rootkey, 
    subkey, 
    valuename, 
    member, 
    member_size )
```  
  
### <a name="parameters"></a>Параметры  
 `rootkey`  
 Корневого раздела реестра.  
  
 `subkey`  
 Подраздел реестра.  
  
 `valuename`  
 Раздел реестра.  
  
 `member`  
 Переменная члена для связи с указанным реестра.  
  
 `member_size`  
 Размер в байтах в переменной-члена.  
  
### <a name="remarks"></a>Примечания  
 Этот макрос используется в сочетании с `BEGIN_RDX_MAP` и `END_RDX_MAP` макросы, чтобы связать переменную-член с записью реестра. Глобальная функция [RegistryDataExchange](../../atl/reference/registry-and-typelib-global-functions.md#registrydataexchange), или функция-член с тем же именем, созданные `BEGIN_RDX_MAP` и `END_RDX_MAP` макросы, следует использовать для выполнения обмен данными между системного реестра и элемент переменные в RDX карты.  
  
##  <a name="rdx_dword"></a>  RDX_DWORD  
 Связывает указанный параметр с переменной указанный член типа DWORD.  
  
```
RDX_DWORD(
    rootkey, 
    subkey, 
    valuename, 
    member, 
    member_size )
```  
  
### <a name="parameters"></a>Параметры  
 `rootkey`  
 Корневого раздела реестра.  
  
 `subkey`  
 Подраздел реестра.  
  
 `valuename`  
 Раздел реестра.  
  
 `member`  
 Переменная члена для связи с указанным реестра.  
  
 `member_size`  
 Размер в байтах в переменной-члена.  
  
### <a name="remarks"></a>Примечания  
 Этот макрос используется в сочетании с `BEGIN_RDX_MAP` и `END_RDX_MAP` макросы, чтобы связать переменную-член с записью реестра. Глобальная функция [RegistryDataExchange](../../atl/reference/registry-and-typelib-global-functions.md#registrydataexchange), или функция-член с тем же именем, созданные `BEGIN_RDX_MAP` и `END_RDX_MAP` макросы, следует использовать для выполнения обмен данными между системного реестра и элемент переменные в RDX карты.  
  
##  <a name="rdx_text"></a>  RDX_TEXT  
 Связывает указанный параметр с переменной типа TCHAR заданного элемента.  
  
```
RDX_TEXT(
    rootkey, 
    subkey, 
    valuename, 
    member, 
    member_size )
```  
  
### <a name="parameters"></a>Параметры  
 `rootkey`  
 Корневого раздела реестра.  
  
 `subkey`  
 Подраздел реестра.  
  
 `valuename`  
 Раздел реестра.  
  
 `member`  
 Переменная члена для связи с указанным реестра.  
  
 `member_size`  
 Размер в байтах в переменной-члена.  
  
### <a name="remarks"></a>Примечания  
 Этот макрос используется в сочетании с `BEGIN_RDX_MAP` и `END_RDX_MAP` макросы, чтобы связать переменную-член с записью реестра. Глобальная функция [RegistryDataExchange](../../atl/reference/registry-and-typelib-global-functions.md#registrydataexchange), или функция-член с тем же именем, созданные `BEGIN_RDX_MAP` и `END_RDX_MAP` макросы, следует использовать для выполнения обмен данными между системного реестра и элемент переменные в RDX карты.  
  
## <a name="see-also"></a>См. также  
 [Макросы](../../atl/reference/atl-macros.md)   
 [RegistryDataExchange](../../atl/reference/registry-and-typelib-global-functions.md#registrydataexchange)







