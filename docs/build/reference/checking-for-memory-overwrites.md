---
title: Проверка затирания памяти
ms.date: 11/04/2016
helpviewer_keywords:
- memory, overwrites
ms.assetid: da7c5d77-a267-415f-a8ab-ee5ce5bfc286
ms.openlocfilehash: b37bd68519aea1194b601e89fefd0f14d428630a
ms.sourcegitcommit: bff17488ac5538b8eaac57156a4d6f06b37d6b7f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/05/2019
ms.locfileid: "57422199"
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
