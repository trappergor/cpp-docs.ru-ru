---
title: Специальные символы в макросах | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- special characters, in NMAKE macros
ms.assetid: c0a06cfc-7103-4ee2-a585-e8f6e85dccd7
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 55a94001e2f912049518120911c25ae64afa24da
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/17/2018
ms.locfileid: "45721432"
---
# <a name="special-characters-in-macros"></a>Специальные символы в макросах

Знак номера (#), после определения указывает комментарий. Чтобы указать знака литерал в макрос, используйте знак вставки (^), как в ^ #.

Знак доллара ($) служит для вызова макросов. Чтобы указать литерал $, используйте $$.

Чтобы расширить определение на новую строку, завершение строки обратную косую черту (\\). При вызове макроса символ обратной косой черты, а также новой строки заменяется пробелом. Чтобы указать обратную косую черту в конце строки, укажите перед ним знак крышки (^), или следовать ей описатель комментария (#).

Для указания символа новой строки, заканчивающиеся строке знак крышки (^), как:

```
CMDS = cls^
dir
```

## <a name="see-also"></a>См. также

[Определение макроса NMAKE](../build/defining-an-nmake-macro.md)