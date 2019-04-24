---
title: Ошибка средств компоновщика LNK2039
ms.date: 11/04/2016
f1_keywords:
- LNK2039
helpviewer_keywords:
- LNK2039
ms.assetid: eaa296bd-4901-41f6-8410-6d03ee827144
ms.openlocfilehash: 57d0c101358f84816c8d0cf96eb5137833df0b48
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59027575"
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