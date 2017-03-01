---
title: "Макросы обмена данными реестра | Документы Microsoft"
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
- RegistryDataExchange function, macros
ms.assetid: c1bc5e79-2307-43d2-9d10-3a62ffadf473
caps.latest.revision: 16
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
ms.openlocfilehash: ee3c1d639ee4a6c6bd6cf26a8c59bb1a37a4fa02
ms.lasthandoff: 02/24/2017

---
# <a name="registry-data-exchange-macros"></a>Макросы Exchange данных реестра
Эти макросы операции обмена данными реестра.  
  
|||  
|-|-|  
|[BEGIN_RDX_MAP](#begin_rdx_map)|Отмечает начало карты обмен данными реестра.|  
|[END_RDX_MAP](#end_rdx_map)|Отмечает конец карты обмен данными реестра.|  
|[RDX_BINARY](#rdx_binary)|Связывает указанный параметр с переменной типа БАЙТОВ заданный элемент.|  
|[RDX_CSTRING_TEXT](#rdx_cstring_text)|Связывает указанный параметр с переменной типа CString заданный элемент.|  
|[RDX_DWORD](#rdx_dword)|Связывает указанный параметр с переменной указанный член типа DWORD.|  
|[RDX_TEXT](#rdx_text)|Связывает указанный параметр с переменной типа TCHAR указанного элемента.|  

## <a name="requirements"></a>Требования  
 **Заголовок:** atlplus.h  
   
##  <a name="a-namebeginrdxmapa--beginrdxmap"></a><a name="begin_rdx_map"></a>BEGIN_RDX_MAP  
 Отмечает начало карты обмен данными реестра.  
  
```
BEGIN_RDX_MAP
```  
  
### <a name="remarks"></a>Примечания  
 Следующие макросы, используемые в схеме обмена данными реестра для чтения и записи в системном реестре.  
  
|Макрос|Описание|  
|-----------|-----------------|  
|[RDX_BINARY](#rdx_binary)|Связывает указанный параметр с переменной типа БАЙТОВ заданный элемент.|  
|[RDX_DWORD](#rdx_dword)|Связывает указанный параметр с переменной указанный член типа DWORD.|  
|[RDX_CSTRING_TEXT](#rdx_cstring_text)|Связывает указанный параметр с переменной типа CString заданный элемент.|  
|[RDX_TEXT](#rdx_text)|Связывает указанный параметр с переменной типа TCHAR указанного элемента.|  
  
 Глобальная функция [RegistryDataExchange](../../atl/reference/registry-and-typelib-global-functions.md#registrydataexchange), или функция-член с тем же именем, созданные `BEGIN_RDX_MAP` и `END_RDX_MAP` макросы, следует использовать, когда ваш код необходим для обмена данными между системного реестра и переменные, заданные в схеме RDX.  
  
##  <a name="a-nameendrdxmapa--endrdxmap"></a><a name="end_rdx_map"></a>END_RDX_MAP  
 Отмечает конец карты обмен данными реестра.  
  
```
END_RDX_MAP
```  
  
##  <a name="a-namerdxbinarya--rdxbinary"></a><a name="rdx_binary"></a>RDX_BINARY  
 Связывает указанный параметр с переменной типа БАЙТОВ заданный элемент.  
  
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
 Чтобы связать с записью в реестре задано переменную-член.  
  
 `member_size`  
 Размер в байтах, переменной-члена.  
  
### <a name="remarks"></a>Примечания  
 Этот макрос используется вместе с `BEGIN_RDX_MAP` и `END_RDX_MAP` макросы, чтобы связать переменную-член с записью реестра. Глобальная функция [RegistryDataExchange](../../atl/reference/registry-and-typelib-global-functions.md#registrydataexchange), или функция-член с тем же именем, созданные `BEGIN_RDX_MAP` и `END_RDX_MAP` следует использовать макросы, выполнять обмен данными между системного реестра и переменные-члены в RDX карты.  
  
##  <a name="a-namerdxcstringtexta--rdxcstringtext"></a><a name="rdx_cstring_text"></a>RDX_CSTRING_TEXT  
 Связывает указанный параметр с переменной типа CString заданный элемент.  
  
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
 Чтобы связать с записью в реестре задано переменную-член.  
  
 `member_size`  
 Размер в байтах, переменной-члена.  
  
### <a name="remarks"></a>Примечания  
 Этот макрос используется вместе с `BEGIN_RDX_MAP` и `END_RDX_MAP` макросы, чтобы связать переменную-член с записью реестра. Глобальная функция [RegistryDataExchange](../../atl/reference/registry-and-typelib-global-functions.md#registrydataexchange), или функция-член с тем же именем, созданные `BEGIN_RDX_MAP` и `END_RDX_MAP` следует использовать макросы, выполнять обмен данными между системного реестра и переменные-члены в RDX карты.  
  
##  <a name="a-namerdxdworda--rdxdword"></a><a name="rdx_dword"></a>RDX_DWORD  
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
 Чтобы связать с записью в реестре задано переменную-член.  
  
 `member_size`  
 Размер в байтах, переменной-члена.  
  
### <a name="remarks"></a>Примечания  
 Этот макрос используется вместе с `BEGIN_RDX_MAP` и `END_RDX_MAP` макросы, чтобы связать переменную-член с записью реестра. Глобальная функция [RegistryDataExchange](../../atl/reference/registry-and-typelib-global-functions.md#registrydataexchange), или функция-член с тем же именем, созданные `BEGIN_RDX_MAP` и `END_RDX_MAP` следует использовать макросы, выполнять обмен данными между системного реестра и переменные-члены в RDX карты.  
  
##  <a name="a-namerdxtexta--rdxtext"></a><a name="rdx_text"></a>RDX_TEXT  
 Связывает указанный параметр с переменной типа TCHAR указанного элемента.  
  
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
 Чтобы связать с записью в реестре задано переменную-член.  
  
 `member_size`  
 Размер в байтах, переменной-члена.  
  
### <a name="remarks"></a>Примечания  
 Этот макрос используется вместе с `BEGIN_RDX_MAP` и `END_RDX_MAP` макросы, чтобы связать переменную-член с записью реестра. Глобальная функция [RegistryDataExchange](../../atl/reference/registry-and-typelib-global-functions.md#registrydataexchange), или функция-член с тем же именем, созданные `BEGIN_RDX_MAP` и `END_RDX_MAP` следует использовать макросы, выполнять обмен данными между системного реестра и переменные-члены в RDX карты.  
  
## <a name="see-also"></a>См. также  
 [Макросы](../../atl/reference/atl-macros.md)   
 [RegistryDataExchange](../../atl/reference/registry-and-typelib-global-functions.md#registrydataexchange)








