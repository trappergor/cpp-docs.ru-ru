---
title: Определение правила | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- NMAKE program, inference rules
- defining inference rules
ms.assetid: 071cd092-3f2e-4065-b0fb-36a9d393cfa8
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a8a5cb7a0285f7abf8bcf476141451eae1b10f85
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/17/2018
ms.locfileid: "45705579"
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