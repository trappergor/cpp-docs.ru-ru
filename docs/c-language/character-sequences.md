---
title: Последовательности символов
ms.date: 11/04/2016
ms.assetid: 1e6961a9-150e-4c13-b427-9af4b6a1fb7a
ms.openlocfilehash: 42fb6b61771feb3eaedfb4ce1e674003df91b263
ms.sourcegitcommit: f4be868c0d1d78e550fba105d4d3c993743a1f4b
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/12/2019
ms.locfileid: "56149941"
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
