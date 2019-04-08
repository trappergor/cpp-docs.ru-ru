---
title: Ошибка средств компоновщика LNK2039
ms.date: 11/04/2016
f1_keywords:
- LNK2039
helpviewer_keywords:
- LNK2039
ms.assetid: eaa296bd-4901-41f6-8410-6d03ee827144
ms.openlocfilehash: 57d0c101358f84816c8d0cf96eb5137833df0b48
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/05/2019
ms.locfileid: "59027575"
---
# <a name="linker-tools-error-lnk2039"></a>Ошибка средств компоновщика LNK2039

импортируется ссылочный класс\<тип > ", определенный в another.obj; он должен быть либо импортированных, или определен, но не оба

Класс ссылки "<`type`>" импортируется в указанный OBJ-файле, но также определен в другой OBJ-файле. Это условие может вызвать сбой во время выполнения или другие непредсказуемые последствия.

### <a name="to-correct-this-error"></a>Исправление ошибки

1. Проверьте ли "`type`" должен быть определен в OBJ-файл и проверьте ли его необходимо импортировать из файла .winmd.

1. Удалите определение или импорта.

## <a name="see-also"></a>См. также

[Ошибки и предупреждения инструментов компоновщика](../../error-messages/tool-errors/linker-tools-errors-and-warnings.md)<br/>
[Ошибка средств компоновщика LNK1332](../../error-messages/tool-errors/linker-tools-error-lnk1332.md)