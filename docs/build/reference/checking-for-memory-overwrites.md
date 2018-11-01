---
title: Проверка затирания памяти
ms.date: 11/04/2016
helpviewer_keywords:
- memory, overwrites
ms.assetid: da7c5d77-a267-415f-a8ab-ee5ce5bfc286
ms.openlocfilehash: ff900c7366a28d19d3b90cbd4a6d9ee732e4ce02
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50621563"
---
# <a name="checking-for-memory-overwrites"></a>Проверка затирания памяти

Если вы получаете нарушение прав доступа при вызове функции обработки кучи, существует возможность, что приложение повредило ее. Признаком такой ситуации будет следующим:

```
Access Violation in _searchseg
```

[_Heapchk](../../c-runtime-library/reference/heapchk.md) функция доступна в обоих отладки и сборки выпуска (только для Windows NT) для проверки целостности кучи библиотеки времени выполнения. Можно использовать `_heapchk` так же, как `AfxCheckMemory` функцию для изолирования затирания, например:

```
if(_heapchk()!=_HEAPOK)
   DebugBreak();
```

Если эта функция никогда не выполняется, необходимо изолировать в какой момент куча была повреждена.

## <a name="see-also"></a>См. также

[Устранение проблем сборки выпуска](../../build/reference/fixing-release-build-problems.md)