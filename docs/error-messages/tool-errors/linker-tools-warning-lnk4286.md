---
title: Предупреждение LNK4286 средств компоновщика
ms.date: 04/09/2019
f1_keywords:
- LNK4286
helpviewer_keywords:
- LNK4286
ms.openlocfilehash: f4ab9104c68534eaf1278a6cacb91623c24a237b
ms.sourcegitcommit: 0ad3f4517e64900a2702dd3d366586f9e2bce2c2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/10/2019
ms.locfileid: "59477641"
---
# <a name="linker-tools-warning-lnk4286"></a>Предупреждение LNK4286 средств компоновщика

> символ "*символ*«определен в»*filename_1.obj*«импортируется путем»*filename_2.obj*"

[__declspec(dllimport)](../../cpp/dllexport-dllimport.md) был указан для *символ* несмотря на то, что этот символ определен в объектном файле *filename_1.obj* в одном образе. Удалить `__declspec(dllimport)` модификатор, чтобы устранить это предупреждение.

## <a name="remarks"></a>Примечания

Предупреждение LNK4286 — общими версия [Предупреждение средств компоновщика LNK4217](linker-tools-warning-lnk4217.md). Компоновщик создает LNK4286 предупреждение, когда он сообщает, какой файл объекта ссылка символа, но не функции.

Чтобы устранить LNK4286, удалите `__declspec(dllimport)` модификатора объявления из опережающее объявление типа *символ* в *filename_2.obj*.

Несмотря на то, что последний созданный код работает правильно, код, созданный для вызова импортированной функции является менее эффективным, чем непосредственный вызов функции. Это предупреждение не отображается при компиляции с помощью [/CLR](../../build/reference/clr-common-language-runtime-compilation.md) параметр.

Дополнительные сведения о импорта и экспорта данных объявления, см. в разделе [dllexport, dllimport](../../cpp/dllexport-dllimport.md).

## <a name="see-also"></a>См. также

[Предупреждение средств компоновщика LNK4049](linker-tools-warning-lnk4049.md) \
[Предупреждение LNK4286 средств компоновщика](linker-tools-warning-lnk4286.md) \
[dllexport, dllimport](../../cpp/dllexport-dllimport.md)