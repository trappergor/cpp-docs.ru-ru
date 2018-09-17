---
title: Проверка перезаписи памяти | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- memory, overwrites
ms.assetid: da7c5d77-a267-415f-a8ab-ee5ce5bfc286
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 246f625e899016080662f27a5901962c1c62f1a8
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/17/2018
ms.locfileid: "45718655"
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