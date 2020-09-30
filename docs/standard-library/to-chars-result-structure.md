---
title: Структура to_chars_result
ms.date: 07/22/2020
f1_keywords:
- charconv/std::to_chars_result
helpviewer_keywords:
- to_chars_result class
- to_chars_result structure
ms.openlocfilehash: 4e46d1cc9d0b6a02d731ad25c2e85c99300d7234
ms.sourcegitcommit: a1676bf6caae05ecd698f26ed80c08828722b237
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/29/2020
ms.locfileid: "91509656"
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

|Участник|Описание|
|--|--|
|`ptr`| Если `ec` значение равно `errc{}` , преобразование прошло успешно и `ptr` является указателем на один конец записанных символов. В противном случае `ptr` имеет значение `to_chars()` параметра `last` , а содержимое диапазона \[ First (Last)) не указано.|
|`ec` | Код ошибки преобразования. Конкретные коды ошибок см. в разделе [`errc`](system-error-enums.md#errc) .|

## <a name="requirements"></a>Требования

**Заголовок:**\<charconv>

**Пространство имен:** std

**Параметр компилятора:** /std: c++ 17 или более поздней версии является обязательным

## <a name="see-also"></a>См. также раздел

[to_chars](charconv-functions.md#to_chars)
