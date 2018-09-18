---
title: Категории языковых стандартов | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: conceptual
f1_keywords:
- LC_MAX
- LC_MIN
- LC_MONETARY
- LC_TIME
- LC_NUMERIC
- LC_COLLATE
- LC_CTYPE
- LC_ALL
dev_langs:
- C++
helpviewer_keywords:
- LC_MIN constant
- LC_MONETARY constant
- LC_CTYPE constant
- locale constants
- LC_MAX constant
- LC_ALL constant
- LC_TIME constant
- LC_NUMERIC constant
- LC_COLLATE constant
ms.assetid: 868f1493-fe5d-4722-acab-bfcd374a063a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 12162e7d6eabfc60b3b4c028b990b720a502f516
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46077884"
---
# <a name="locale-categories"></a>Категории языковых стандартов

## <a name="syntax"></a>Синтаксис

```

#include <locale.h>

```

## <a name="remarks"></a>Примечания

Категории языковых стандартов представляют собой константы манифеста, с помощью которых подпрограммы локализации указывают, какую информацию о языковом стандарте программы они будут использовать. Языковой стандарт определяет расположение (или страну, или регион), для которого можно настроить определенные аспекты программы. Например, языковой стандарт влияет на форматирование дат и отображение денежных значений.

|Категории языкового стандарта|Части программы, на которые они влияют|
|---------------------|-------------------------------|
|`LC_ALL`|Любое применение языкового стандарта (все категории)|
|`LC_COLLATE`|Поведение функций `strcoll` и `strxfrm`|
|`LC_CTYPE`|Поведение функций обработки символов (за исключением **isdigit**, `isxdigit`, `mbstowcs` и `mbtowc`)|
|`LC_MAX`|Аналогично `LC_TIME`|
|`LC_MIN`|Аналогично `LC_ALL`|
|`LC_MONETARY`|Информация о форматировании денежных значений, возвращаемая функцией `localeconv`|
|`LC_NUMERIC`|Символ десятичного разделителя для процедур форматированного вывода (например, `printf`), для процедур преобразования данных и для форматирования в выводе функции `localeconv`, не имеющего отношения к денежным значениям.|
|`LC_TIME`|Поведение функции `strftime`|

См. пример в описании функций [setlocale, _wsetlocale](../c-runtime-library/reference/setlocale-wsetlocale.md).

## <a name="see-also"></a>См. также

[localeconv](../c-runtime-library/reference/localeconv.md)<br/>
[setlocale, _wsetlocale](../c-runtime-library/reference/setlocale-wsetlocale.md)<br/>
[Функции strcoll](../c-runtime-library/strcoll-functions.md)<br/>
[strftime, wcsftime, _strftime_l, _wcsftime_l](../c-runtime-library/reference/strftime-wcsftime-strftime-l-wcsftime-l.md)<br/>
[strxfrm, wcsxfrm, _strxfrm_l, _wcsxfrm_l](../c-runtime-library/reference/strxfrm-wcsxfrm-strxfrm-l-wcsxfrm-l.md)<br/>
[Глобальные константы](../c-runtime-library/global-constants.md)