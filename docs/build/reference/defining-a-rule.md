---
title: Определение правила
ms.date: 11/04/2016
helpviewer_keywords:
- NMAKE program, inference rules
- defining inference rules
ms.assetid: 071cd092-3f2e-4065-b0fb-36a9d393cfa8
ms.openlocfilehash: cd82dc5b0693e563fd3d75a0215265089ff57913
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2019
ms.locfileid: "57827183"
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
