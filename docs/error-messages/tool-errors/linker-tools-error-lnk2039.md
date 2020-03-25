---
title: Ошибка средств компоновщика LNK2039
ms.date: 11/04/2016
f1_keywords:
- LNK2039
helpviewer_keywords:
- LNK2039
ms.assetid: eaa296bd-4901-41f6-8410-6d03ee827144
ms.openlocfilehash: 7712747deb865ec62fa007fcd95ad09630d00cea
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80194503"
---
# <a name="linker-tools-error-lnk2039"></a>Ошибка средств компоновщика LNK2039

импортируется ссылочный класс "\<Type >", определенный в другом obj; Он должен быть либо импортирован, либо определен, но не одновременно

Класс ссылки "<`type`>" импортируется в указанный OBJ-файл, но также определяется в другом obj-файле. Это условие может вызвать сбой во время выполнения или другое непредвиденное поведение.

### <a name="to-correct-this-error"></a>Исправление ошибки

1. Проверьте, необходимо ли определить "`type`" в другом obj-файле, и проверьте, нужно ли его импортировать из файла WinMD.

1. Удалите либо определение, либо импорт.

## <a name="see-also"></a>См. также раздел

[Ошибки и предупреждения средств компоновщика](../../error-messages/tool-errors/linker-tools-errors-and-warnings.md)<br/>
[Ошибка средств компоновщика LNK1332](../../error-messages/tool-errors/linker-tools-error-lnk1332.md)
