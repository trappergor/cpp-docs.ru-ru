---
title: setlocale
ms.date: 11/04/2016
f1_keywords:
- setlocale_CPP
- vc-pragma.setlocale
helpviewer_keywords:
- pragmas, setlocale
- setlocale pragma
ms.assetid: e60b43d9-fbdf-4c4e-ac85-805523a13b86
ms.openlocfilehash: e5a190e18dd38c5d2b6e03703c5ee08043cd6e41
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50487962"
---
# <a name="setlocale"></a>setlocale

Определяет языковой стандарт (страна или регион и язык), используемый при преобразовании констант и строковых литералов с расширенными символами.

## <a name="syntax"></a>Синтаксис

```
#pragma setlocale( "[locale-string]" )
```

## <a name="remarks"></a>Примечания

Поскольку алгоритм преобразования многобайтовых символов в расширенные символы может зависеть от языкового стандарта или компиляция может выполняться в среде с языковым стандартом, отличным от стандарта среды, в которой будет запускаться исполняемый файл, данная директива #pragma позволяет указать целевой языковой стандарт во время компиляции. Это гарантирует, что строки с расширенными символами будут сохраняться в правильном формате.

Значение по умолчанию *строке языкового стандарта* — «».

Языковом стандарте «C» сопоставляет каждый символ в строке его значению с **wchar_t** (short без знака). Другие значения, допустимые для `setlocale` этих записей, которые находятся в [строки языка](../c-runtime-library/language-strings.md) списка. Например, можно указать директиву:

```cpp
#pragma setlocale("dutch")
```

Возможность указания строки с названием языка зависит от кодовых страниц и идентификаторов языков, поддерживаемых компьютером.

## <a name="see-also"></a>См. также

[Директивы Pragma и ключевое слово __Pragma](../preprocessor/pragma-directives-and-the-pragma-keyword.md)