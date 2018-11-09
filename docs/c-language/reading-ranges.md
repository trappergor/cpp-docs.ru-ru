---
title: Диапазоны чтения
ms.date: 11/04/2016
ms.assetid: 99de29ce-ab14-46f4-97e1-2081fd996b53
ms.openlocfilehash: b5c6a6baf43b8786fbd0301e4b89ea856d839606
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50604123"
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