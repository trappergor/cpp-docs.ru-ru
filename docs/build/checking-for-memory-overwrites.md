---
title: Проверка затирания памяти
ms.date: 11/04/2016
helpviewer_keywords:
- memory, overwrites
ms.assetid: da7c5d77-a267-415f-a8ab-ee5ce5bfc286
ms.openlocfilehash: 2c59cb96d640df6dcd96b9e0eafbcd325ed475f5
ms.sourcegitcommit: c6f8e6c2daec40ff4effd8ca99a7014a3b41ef33
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/24/2019
ms.locfileid: "64342255"
---
# <a name="checking-for-memory-overwrites"></a>Проверка затирания памяти

Если при вызове функции управления кучей вы получаете ошибку, связанную с нарушением прав доступа, возможно, ваша программа вызвала повреждение кучи. Как правило, в такой ситуации проявляются следующие признаки:

```
Access Violation in _searchseg
```

Функция [_heapchk](../c-runtime-library/reference/heapchk.md) доступна в сборках отладки и выпуска (только для Windows NT) для проверки целостности кучи библиотеки времени выполнения. Вы можете использовать `_heapchk` аналогично функции `AfxCheckMemory` для изоляции перезаписи кучи, например:

```
if(_heapchk()!=_HEAPOK)
   DebugBreak();
```

Если эта функция завершается сбоем, необходимо изолировать точку, в которой произошло повреждение кучи.

## <a name="see-also"></a>См. также

[Устранение проблем сборки выпуска](fixing-release-build-problems.md)
