---
title: Определение правила
ms.date: 11/04/2016
helpviewer_keywords:
- NMAKE program, inference rules
- defining inference rules
ms.assetid: 071cd092-3f2e-4065-b0fb-36a9d393cfa8
ms.openlocfilehash: cd82dc5b0693e563fd3d75a0215265089ff57913
ms.sourcegitcommit: c6f8e6c2daec40ff4effd8ca99a7014a3b41ef33
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/24/2019
ms.locfileid: "64342888"
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

[Пути поиска в правилах](search-paths-in-rules.md)

## <a name="see-also"></a>См. также

[Правила вывода](inference-rules.md)
