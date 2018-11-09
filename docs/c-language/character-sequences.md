---
title: Последовательности символов
ms.date: 11/04/2016
ms.assetid: 1e6961a9-150e-4c13-b427-9af4b6a1fb7a
ms.openlocfilehash: dea24a2ae5887ea8c0111d8251ba4d9d03ccba0f
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50489665"
---
# <a name="character-sequences"></a>Последовательности символов

**ANSI 3.8.2** Сопоставление последовательностей символов в исходных файлах

В операторах препроцессора используется тот же набор символов, что и в операторах исходного файла, однако escape-последовательности не поддерживаются.

Таким образом, при определении пути к включаемому файлу необходимо указывать только одну обратную косую черту.

```
#include "path1\path2\myfile"
```

Однако в самом исходном коде необходимо указывать две обратные косые черты подряд:

```
fil = fopen( "path1\\path2\\myfile", "rt" );
```

## <a name="see-also"></a>См. также

[Директивы предварительной обработки](../c-language/preprocessing-directives.md)