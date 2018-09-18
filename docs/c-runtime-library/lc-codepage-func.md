---
title: ___lc_codepage_func | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: conceptual
apiname:
- ___lc_codepage_func
apilocation:
- msvcr120.dll
- msvcr110_clr0400.dll
- msvcr80.dll
- msvcr100.dll
- msvcr90.dll
- msvcr110.dll
- msvcrt.dll
apitype: DLLExport
f1_keywords:
- lc_codepage_func
- ___lc_codepage_func
dev_langs:
- C++
helpviewer_keywords:
- ___lc_codepage_func
ms.assetid: 6a663bd0-5a63-4a2f-9507-872ec1582aae
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a35486b271822cb9c7d0dc1bed1e885c13f1dd12
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46087673"
---
# <a name="lccodepagefunc"></a>___lc_codepage_func

Внутренняя функция CRT. Получает текущую кодовую страницу потока.

## <a name="syntax"></a>Синтаксис

```cpp
UINT ___lc_codepage_func(void);
```

## <a name="return-value"></a>Возвращаемое значение

Текущая кодовая страница потока.

## <a name="remarks"></a>Примечания

`___lc_codepage_func` — это внутренняя функция CRT, которая используется другими функциями CRT для получения текущей кодовой страницы из локального хранилища потока для данных CRT. Эти сведения также доступны при использовании функции [_get_current_locale](../c-runtime-library/reference/get-current-locale.md).

*Кодовая страница* представляет собой сопоставление однобайтовых или двухбайтовых кодов с конкретными символами. Разные кодовые страницы включают разные специальные символы, как правило, настроенные для языка или группы языков. Дополнительные сведения о кодовых страницах см. в разделе [Code Pages](../c-runtime-library/code-pages.md).

Внутренние функции CRT связаны с конкретной реализацией и подлежат изменению в каждом выпуске. Мы не рекомендуем использовать их в коде.

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|`___lc_codepage_func`|crt\src\setlocal.h|

## <a name="see-also"></a>См. также

[_get_current_locale](../c-runtime-library/reference/get-current-locale.md)<br/>
[setlocale, _wsetlocale](../c-runtime-library/reference/setlocale-wsetlocale.md)<br/>
[_create_locale, _wcreate_locale](../c-runtime-library/reference/create-locale-wcreate-locale.md)<br/>
[_free_locale](../c-runtime-library/reference/free-locale.md)