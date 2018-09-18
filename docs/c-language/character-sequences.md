---
title: Последовательности символов | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
ms.assetid: 1e6961a9-150e-4c13-b427-9af4b6a1fb7a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 5cf3b52b8a4e76062d06b0b9ca3d4535b79595c5
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46061517"
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