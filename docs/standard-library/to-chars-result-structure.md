---
title: Структура to_chars_result
ms.date: 07/22/2020
f1_keywords:
- charconv/std::to_chars_result
helpviewer_keywords:
- to_chars_result class
- to_chars_result structure
ms.openlocfilehash: a840b8d030f0ed0d2a4afcc57e1bef1161c76ff3
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87212065"
---
# <a name="to_chars_result-struct"></a>Структура to_chars_result

## <a name="syntax"></a>Синтаксис

```cpp
struct to_chars_result {
    char* ptr;
    errc ec;
};
```

## <a name="members"></a>Участники

|Член|Описание|
|--|--|
|`ptr`| Если `ec` значение равно `errc{}` , преобразование прошло успешно и `ptr` является указателем на один конец записанных символов. В противном случае `ptr` имеет значение `to_chars()` параметра `last` , а содержимое диапазона \[ First (Last)) не указано.|
|`ec` | Код ошибки преобразования. Конкретные коды ошибок см. в разделе [`errc`](system-error-enums.md#errc) .|

## <a name="requirements"></a>Требования

**Заголовок:**\<charconv>

**Пространство имен:** std

**Параметр компилятора:** /std: c++ 17 или более поздней версии является обязательным

## <a name="see-also"></a>См. также раздел

[to_chars](charconv-functions.md#to_chars)