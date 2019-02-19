---
title: Диапазоны чтения
ms.date: 11/04/2016
ms.assetid: 99de29ce-ab14-46f4-97e1-2081fd996b53
ms.openlocfilehash: 86bb24647084d8bdc452960bab631587c2413276
ms.sourcegitcommit: f4be868c0d1d78e550fba105d4d3c993743a1f4b
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/12/2019
ms.locfileid: "56150497"
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
