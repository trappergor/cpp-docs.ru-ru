---
title: Определение правила
ms.date: 11/04/2016
helpviewer_keywords:
- NMAKE program, inference rules
- defining inference rules
ms.assetid: 071cd092-3f2e-4065-b0fb-36a9d393cfa8
ms.openlocfilehash: 0e8356f57b85d503328bb282e2f9f785ac20fa4c
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50431174"
---
# <a name="defining-a-rule"></a>Определение правила

*Fromext* представляет расширение зависимого файла, и *toext* представляет расширение целевого файла.

```
.fromext.toext:
   commands
```

## <a name="remarks"></a>Примечания

Расширения не чувствительны к регистру. Макросы могут вызываться для представления *fromext* и *toext*; макросы разворачиваются во время предварительной обработки. Точка (.) выше *fromext* должны находиться в начале строки. Двоеточие (:), предшествует нуль или более пробелов или вкладки. Он может следовать только пробелы или вкладки, точку с запятой (;) для указания команды, знак номера (#), чтобы указать комментарий или символа новой строки. Другие пробелы не допускаются. Команды указываются как в блоках описания.

## <a name="what-do-you-want-to-know-more-about"></a>Дополнительные сведения

[Пути поиска в правилах](../build/search-paths-in-rules.md)

## <a name="see-also"></a>См. также

[Правила вывода](../build/inference-rules.md)