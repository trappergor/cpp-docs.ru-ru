---
title: Ошибка средств компоновщика LNK1352
description: Ошибка средств компоновщика LNK1352 возникает при попыток неподдерживаемого объединения разделов.
ms.date: 09/10/2019
f1_keywords:
- LNK1352
helpviewer_keywords:
- LNK1352
ms.openlocfilehash: 38f773bfd669529dfb1ada9c7bb59e6f0962c9c7
ms.sourcegitcommit: 3caf5261b3ea80d9cf14038c116ba981d655cd13
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/11/2019
ms.locfileid: "70908396"
---
# <a name="linker-tools-error-lnk1352"></a>Ошибка средств компоновщика LNK1352

> "*section_name_1*" и "*section_name_2*" не могут быть объединены в разные разделы

## <a name="remarks"></a>Примечания

Компоновщик обнаружил неразрешенное слияние раздела, так как *section_name_1* и *section_name_2* должны быть объединены в один раздел. Например, эта ошибка возникает, если компоновщик обнаруживает попытку объединить `.stls` раздел `.tls` и раздел в разные разделы.

### <a name="to-correct-this-error"></a>Исправление ошибки

Проверьте параметр [/Merge](../../build/reference/merge-combine-sections.md) в командной строке компоновщика для этой проблемы.

## <a name="see-also"></a>См. также

[Ошибки и предупреждения средств компоновщика](../../error-messages/tool-errors/linker-tools-errors-and-warnings.md)
