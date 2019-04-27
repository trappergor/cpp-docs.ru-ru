---
title: Макросы для обмена данными реестра
ms.date: 11/04/2016
f1_keywords:
- atlplus/ATL::BEGIN_RDX_MAP
- atlplus/ATL::END_RDX_MAP
- atlplus/ATL::RDX_BINARY
- atlplus/ATL::RDX_CSTRING_TEXT
- atlplus/ATL::RDX_DWORD
- atlplus/ATL::RDX_TEXT
helpviewer_keywords:
- RegistryDataExchange function, macros
ms.assetid: c1bc5e79-2307-43d2-9d10-3a62ffadf473
ms.openlocfilehash: 69b823cbcd85ebaaeb05979283ea4f8fea80f4b6
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62197488"
---
# <a name="registry-data-exchange-macros"></a>Макросы для обмена данными реестра

Эти макросы операции обмена данными реестра.

|||
|-|-|
|[BEGIN_RDX_MAP](#begin_rdx_map)|Отмечает начало карты обмен данными реестра.|
|[END_RDX_MAP](#end_rdx_map)|Помечает конец карты обмен данными реестра.|
|[RDX_BINARY](#rdx_binary)|Связывает указанной записи реестра с переменную-член указанного типа BYTE.|
|[RDX_CSTRING_TEXT](#rdx_cstring_text)|Связывает указанной записи реестра с переменной типа CString указанного элемента.|
|[RDX_DWORD](#rdx_dword)|Связывает указанной записи реестра с указанного элемента переменной типа DWORD.|
|[RDX_TEXT](#rdx_text)|Связывает указанной записи реестра с переменной типа TCHAR указанного элемента.|

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
|[RDX_BINARY](#rdx_binary)|Связывает указанной записи реестра с переменную-член указанного типа BYTE.|
|[RDX_DWORD](#rdx_dword)|Связывает указанной записи реестра с указанного элемента переменной типа DWORD.|
|[RDX_CSTRING_TEXT](#rdx_cstring_text)|Связывает указанной записи реестра с переменной типа CString указанного элемента.|
|[RDX_TEXT](#rdx_text)|Связывает указанной записи реестра с переменной типа TCHAR указанного элемента.|

Глобальная функция [RegistryDataExchange](../../atl/reference/registry-and-typelib-global-functions.md#registrydataexchange), или функция-член с тем же именем, созданные BEGIN_RDX_MAP и END_RDX_MAP макросы, должны использоваться всякий раз, когда ваш код должен для обмена данными между системного реестра и переменные, указанные в RDX карты.

##  <a name="end_rdx_map"></a>  END_RDX_MAP

Помечает конец карты обмен данными реестра.

```
END_RDX_MAP
```

##  <a name="rdx_binary"></a>  RDX_BINARY

Связывает указанной записи реестра с переменную-член указанного типа BYTE.

```
RDX_BINARY(
    rootkey,
    subkey,
    valuename,
    member,
    member_size )
```

### <a name="parameters"></a>Параметры

*корень*<br/>
Корневого раздела реестра.

*подраздел*<br/>
Подраздел реестра.

*valueName*<br/>
Раздел реестра.

*member*<br/>
Переменная-член должен быть сопоставлен указанной записи реестра.

*member_size*<br/>
Размер в байтах в переменной-члена.

### <a name="remarks"></a>Примечания

Этот макрос используется в сочетании с макросами BEGIN_RDX_MAP и END_RDX_MAP должен быть сопоставлен переменной-члена заданного реестра. Глобальная функция [RegistryDataExchange](../../atl/reference/registry-and-typelib-global-functions.md#registrydataexchange), или функция-член с тем же именем, созданные BEGIN_RDX_MAP и END_RDX_MAP макросы, следует использовать для выполнения обмен данными между системного реестра и переменных-членов в сопоставлении RDX.

##  <a name="rdx_cstring_text"></a>  RDX_CSTRING_TEXT

Связывает указанной записи реестра с переменной типа CString указанного элемента.

```
RDX_CSTRING_TEXT(
    rootkey,
    subkey,
    valuename,
    member,
    member_size )
```

### <a name="parameters"></a>Параметры

*корень*<br/>
Корневого раздела реестра.

*подраздел*<br/>
Подраздел реестра.

*valueName*<br/>
Раздел реестра.

*member*<br/>
Переменная-член должен быть сопоставлен указанной записи реестра.

*member_size*<br/>
Размер в байтах в переменной-члена.

### <a name="remarks"></a>Примечания

Этот макрос используется в сочетании с макросами BEGIN_RDX_MAP и END_RDX_MAP должен быть сопоставлен переменной-члена заданного реестра. Глобальная функция [RegistryDataExchange](../../atl/reference/registry-and-typelib-global-functions.md#registrydataexchange), или функция-член с тем же именем, созданные BEGIN_RDX_MAP и END_RDX_MAP макросы, следует использовать для выполнения обмен данными между системного реестра и переменных-членов в сопоставлении RDX.

##  <a name="rdx_dword"></a>  RDX_DWORD

Связывает указанной записи реестра с указанного элемента переменной типа DWORD.

```
RDX_DWORD(
    rootkey,
    subkey,
    valuename,
    member,
    member_size )
```

### <a name="parameters"></a>Параметры

*корень*<br/>
Корневого раздела реестра.

*подраздел*<br/>
Подраздел реестра.

*valueName*<br/>
Раздел реестра.

*member*<br/>
Переменная-член должен быть сопоставлен указанной записи реестра.

*member_size*<br/>
Размер в байтах в переменной-члена.

### <a name="remarks"></a>Примечания

Этот макрос используется в сочетании с макросами BEGIN_RDX_MAP и END_RDX_MAP должен быть сопоставлен переменной-члена заданного реестра. Глобальная функция [RegistryDataExchange](../../atl/reference/registry-and-typelib-global-functions.md#registrydataexchange), или функция-член с тем же именем, созданные BEGIN_RDX_MAP и END_RDX_MAP макросы, следует использовать для выполнения обмен данными между системного реестра и переменных-членов в сопоставлении RDX.

##  <a name="rdx_text"></a>  RDX_TEXT

Связывает указанной записи реестра с переменной типа TCHAR указанного элемента.

```
RDX_TEXT(
    rootkey,
    subkey,
    valuename,
    member,
    member_size )
```

### <a name="parameters"></a>Параметры

*корень*<br/>
Корневого раздела реестра.

*подраздел*<br/>
Подраздел реестра.

*valueName*<br/>
Раздел реестра.

*member*<br/>
Переменная-член должен быть сопоставлен указанной записи реестра.

*member_size*<br/>
Размер в байтах в переменной-члена.

### <a name="remarks"></a>Примечания

Этот макрос используется в сочетании с макросами BEGIN_RDX_MAP и END_RDX_MAP должен быть сопоставлен переменной-члена заданного реестра. Глобальная функция [RegistryDataExchange](../../atl/reference/registry-and-typelib-global-functions.md#registrydataexchange), или функция-член с тем же именем, созданные BEGIN_RDX_MAP и END_RDX_MAP макросы, следует использовать для выполнения обмен данными между системного реестра и переменных-членов в сопоставлении RDX.

## <a name="see-also"></a>См. также

[Макросы](../../atl/reference/atl-macros.md)<br/>
[RegistryDataExchange](../../atl/reference/registry-and-typelib-global-functions.md#registrydataexchange)
