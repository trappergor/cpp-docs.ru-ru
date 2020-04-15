---
title: Макрос обмена данными реестра
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
ms.openlocfilehash: a7d580e4907cec40f97c0cead616665fff7b8a01
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81326072"
---
# <a name="registry-data-exchange-macros"></a>Макрос обмена данными реестра

Эти макросы выполняют операции по обмену данными реестра.

|||
|-|-|
|[BEGIN_RDX_MAP](#begin_rdx_map)|Отмечает начало карты обмена данными реестра.|
|[END_RDX_MAP](#end_rdx_map)|Отметка окончания карты обмена данными реестра.|
|[RDX_BINARY](#rdx_binary)|Ассоциирует указанную запись реестра с указанной переменной типа BYTE.|
|[RDX_CSTRING_TEXT](#rdx_cstring_text)|Связывает указанную запись реестра с указанной переменной типа CString.|
|[RDX_DWORD](#rdx_dword)|Связывает указанную запись реестра с указанной переменной типа DWORD.|
|[RDX_TEXT](#rdx_text)|Связывает указанную запись реестра с указанной переменной типа TCHAR.|

## <a name="requirements"></a>Требования

**Заголовок:** atlplus.h

## <a name="begin_rdx_map"></a><a name="begin_rdx_map"></a>BEGIN_RDX_MAP

Отмечает начало карты обмена данными реестра.

```
BEGIN_RDX_MAP
```

### <a name="remarks"></a>Remarks

Следующие макросы используются на карте обмена данными реестра для чтения и записи записей в системном реестре:

|Макрос|Описание|
|-----------|-----------------|
|[RDX_BINARY](#rdx_binary)|Ассоциирует указанную запись реестра с указанной переменной типа BYTE.|
|[RDX_DWORD](#rdx_dword)|Связывает указанную запись реестра с указанной переменной типа DWORD.|
|[RDX_CSTRING_TEXT](#rdx_cstring_text)|Связывает указанную запись реестра с указанной переменной типа CString.|
|[RDX_TEXT](#rdx_text)|Связывает указанную запись реестра с указанной переменной типа TCHAR.|

Глобальная функция [RegistryDataExchange](../../atl/reference/registry-and-typelib-global-functions.md#registrydataexchange), или функция члена с тем же именем, созданные BEGIN_RDX_MAP и END_RDX_MAP макросов, должны использоваться всякий раз, когда ваш код должен обмениваться данными между системным реестром и переменными, указанными на карте RDX.

## <a name="end_rdx_map"></a><a name="end_rdx_map"></a>END_RDX_MAP

Отметка окончания карты обмена данными реестра.

```
END_RDX_MAP
```

## <a name="rdx_binary"></a><a name="rdx_binary"></a>RDX_BINARY

Ассоциирует указанную запись реестра с указанной переменной типа BYTE.

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
Корень ключа реестра.

*Подраздел*<br/>
Подключка реестра.

*значение*<br/>
Ключ реестра.

*Член*<br/>
Переменная участника, связаваемый с указанной записью реестра.

*member_size*<br/>
Размер, в байтах, переменной члена.

### <a name="remarks"></a>Remarks

Этот макрос используется в сочетании с BEGIN_RDX_MAP и END_RDX_MAP макросов для ассоциировать переменную члена с данной записью реестра. Глобальная функция [RegistryDataExchange](../../atl/reference/registry-and-typelib-global-functions.md#registrydataexchange), или функция члена с тем же именем, созданная BEGIN_RDX_MAP и END_RDX_MAP макросов, должна использоваться для выполнения обмена данными между системным реестром и переменными членов на карте RDX.

## <a name="rdx_cstring_text"></a><a name="rdx_cstring_text"></a>RDX_CSTRING_TEXT

Связывает указанную запись реестра с указанной переменной типа CString.

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
Корень ключа реестра.

*Подраздел*<br/>
Подключка реестра.

*значение*<br/>
Ключ реестра.

*Член*<br/>
Переменная участника, связаваемый с указанной записью реестра.

*member_size*<br/>
Размер, в байтах, переменной члена.

### <a name="remarks"></a>Remarks

Этот макрос используется в сочетании с BEGIN_RDX_MAP и END_RDX_MAP макросов для ассоциировать переменную члена с данной записью реестра. Глобальная функция [RegistryDataExchange](../../atl/reference/registry-and-typelib-global-functions.md#registrydataexchange), или функция члена с тем же именем, созданная BEGIN_RDX_MAP и END_RDX_MAP макросов, должна использоваться для выполнения обмена данными между системным реестром и переменными членов на карте RDX.

## <a name="rdx_dword"></a><a name="rdx_dword"></a>RDX_DWORD

Связывает указанную запись реестра с указанной переменной типа DWORD.

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
Корень ключа реестра.

*Подраздел*<br/>
Подключка реестра.

*значение*<br/>
Ключ реестра.

*Член*<br/>
Переменная участника, связаваемый с указанной записью реестра.

*member_size*<br/>
Размер, в байтах, переменной члена.

### <a name="remarks"></a>Remarks

Этот макрос используется в сочетании с BEGIN_RDX_MAP и END_RDX_MAP макросов для ассоциировать переменную члена с данной записью реестра. Глобальная функция [RegistryDataExchange](../../atl/reference/registry-and-typelib-global-functions.md#registrydataexchange), или функция члена с тем же именем, созданная BEGIN_RDX_MAP и END_RDX_MAP макросов, должна использоваться для выполнения обмена данными между системным реестром и переменными членов на карте RDX.

## <a name="rdx_text"></a><a name="rdx_text"></a>RDX_TEXT

Связывает указанную запись реестра с указанной переменной типа TCHAR.

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
Корень ключа реестра.

*Подраздел*<br/>
Подключка реестра.

*значение*<br/>
Ключ реестра.

*Член*<br/>
Переменная участника, связаваемый с указанной записью реестра.

*member_size*<br/>
Размер, в байтах, переменной члена.

### <a name="remarks"></a>Remarks

Этот макрос используется в сочетании с BEGIN_RDX_MAP и END_RDX_MAP макросов для ассоциировать переменную члена с данной записью реестра. Глобальная функция [RegistryDataExchange](../../atl/reference/registry-and-typelib-global-functions.md#registrydataexchange), или функция члена с тем же именем, созданная BEGIN_RDX_MAP и END_RDX_MAP макросов, должна использоваться для выполнения обмена данными между системным реестром и переменными членов на карте RDX.

## <a name="see-also"></a>См. также раздел

[Макросы](../../atl/reference/atl-macros.md)<br/>
[RegistryDataExchange](../../atl/reference/registry-and-typelib-global-functions.md#registrydataexchange)
