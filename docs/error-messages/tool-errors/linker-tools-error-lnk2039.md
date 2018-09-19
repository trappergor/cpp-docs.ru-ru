---
title: Ошибка средств компоновщика LNK2039 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK2039
dev_langs:
- C++
helpviewer_keywords:
- LNK2039
ms.assetid: eaa296bd-4901-41f6-8410-6d03ee827144
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ac4fdde90911427a1a193bfb6f3a950a7bdcf180
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46081797"
---
# <a name="linker-tools-error-lnk2039"></a>Ошибка средств компоновщика LNK2039

импортируется ссылочный класс\<тип > ", определенный в another.obj; он должен быть либо импортированных, или определен, но не оба

Класс ссылки "<`type`>" импортируется в указанный OBJ-файле, но также определен в другой OBJ-файле. Это условие может вызвать сбой во время выполнения или другие непредсказуемые последствия.

### <a name="to-correct-this-error"></a>Исправление ошибки

1. Проверьте ли "`type`" должен быть определен в OBJ-файл и проверьте ли его необходимо импортировать из файла .winmd.

1. Удалите определение или импорта.

## <a name="see-also"></a>См. также

[Ошибки и предупреждения средств компоновщика](../../error-messages/tool-errors/linker-tools-errors-and-warnings.md)<br/>
[Ошибка средств компоновщика LNK1332](../../error-messages/tool-errors/linker-tools-error-lnk1332.md)