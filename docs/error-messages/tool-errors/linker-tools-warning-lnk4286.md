---
title: Предупреждение средств компоновщика LNK4286
ms.date: 04/15/2019
f1_keywords:
- LNK4286
helpviewer_keywords:
- LNK4286
ms.openlocfilehash: 43ed18808ba5ce632dd7dc7095f7bc30e4497ec9
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62352441"
---
# <a name="linker-tools-warning-lnk4286"></a>Предупреждение средств компоновщика LNK4286

> символ "*символ*«определен в»*filename_1.obj*«импортируется путем»*filename_2.obj*"

[__declspec(dllimport)](../../cpp/dllexport-dllimport.md) был указан для *символ* несмотря на то, что этот символ определен в объектном файле *filename_1.obj* в одном образе. Удалить `__declspec(dllimport)` модификатор, чтобы устранить это предупреждение.

## <a name="remarks"></a>Примечания

Предупреждение LNK4286 — общими версия [Предупреждение средств компоновщика LNK4217](linker-tools-warning-lnk4217.md). Компоновщик создает LNK4286 предупреждение, когда он сообщает, какой файл объекта ссылка символа, но не функции.

Чтобы устранить LNK4286, удалите `__declspec(dllimport)` модификатора объявления из опережающее объявление типа *символ* в *filename_2.obj*.

Несмотря на то, что последний созданный код работает правильно, код, созданный для вызова импортированной функции является менее эффективным, чем непосредственный вызов функции. Это предупреждение не отображается при компиляции с помощью [/CLR](../../build/reference/clr-common-language-runtime-compilation.md) параметр.

Дополнительные сведения о импорта и экспорта данных объявления, см. в разделе [dllexport, dllimport](../../cpp/dllexport-dllimport.md).

## <a name="see-also"></a>См. также

[Предупреждение средств компоновщика LNK4049](linker-tools-warning-lnk4049.md) \
[Предупреждение средств компоновщика LNK4217](linker-tools-warning-lnk4217.md) \
[dllexport, dllimport](../../cpp/dllexport-dllimport.md)