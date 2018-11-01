---
title: Массивы в выражениях
ms.date: 11/04/2016
helpviewer_keywords:
- expressions [C++], arrays in
- arrays [C++], in expressions
ms.assetid: 6e5a795b-d6bd-4e39-b313-6a20d47c4d4b
ms.openlocfilehash: 0f2ef43c2a5bc4f8a44378c21d6d53b14f07ea07
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50478173"
---
# <a name="arrays-in-expressions"></a>Массивы в выражениях

Если идентификатор типа массива отображается в выражении, отличное от `sizeof`, взятия адреса (**&**), или инициализации ссылки, он преобразуется в указатель на первый элемент массива. Пример:

```cpp
char szError1[] = "Error: Disk drive not ready.";
char *psz = szError1;
```

Указатель `psz` указывает на первый элемент массива `szError1`. Обратите внимание, что массивы, в отличие от указателей, не являются изменяемыми l-значениями. Таким образом, следующее присвоение незаконно.

```cpp
szError1 = psz;
```

## <a name="see-also"></a>См. также

[Массивы](../cpp/arrays-cpp.md)