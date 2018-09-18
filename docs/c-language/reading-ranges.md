---
title: Диапазоны чтения | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
ms.assetid: 99de29ce-ab14-46f4-97e1-2081fd996b53
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 76530dfdac917dfbde50bc3fb1b17a3c31178729
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46030249"
---
# <a name="reading-ranges"></a>Диапазоны чтения

**ANSI 4.9.6.2** Интерпретация символа дефиса (-), который не является ни первым, ни последним символом в списке сканирования для преобразования % [ в функции `fscanf`

В следующей строке

```
fscanf( fileptr, "%[A-Z]", strptr);
```

считывается любое количество символов в диапазоне A–Z в строке, на которую указывает `strptr`.

## <a name="see-also"></a>См. также

[Функции библиотеки](../c-language/library-functions.md)