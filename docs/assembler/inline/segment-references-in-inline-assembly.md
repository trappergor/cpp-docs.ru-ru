---
title: Ссылки на сегменты во встроенном коде на языке ассемблера
ms.date: 08/30/2018
helpviewer_keywords:
- references, inline assembly
- segment references in inline assembly
- inline assembly, segment references
- registers
- inline assembly, registers
- registers, inline assembly
ms.assetid: c63e6bb4-49d9-4fa1-bb22-eea21b5cbc0f
ms.openlocfilehash: 5c07fa897da23a55f376a20e7588c8c8c269d1a6
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62167378"
---
# <a name="segment-references-in-inline-assembly"></a>Ссылки на сегменты во встроенном коде на языке ассемблера

**Блок, относящийся только к системам Microsoft**

Ссылаться на сегменты следует по регистру, а не по имени (например, имя сегмента `_TEXT` недопустимо). В переопределениях сегментов необходимо явно использовать регистр, как в ES:[BX].

**Завершение блока, относящегося только к системам Майкрософт**

## <a name="see-also"></a>См. также

[Использование языка ассемблера в блоках __asm](../../assembler/inline/using-assembly-language-in-asm-blocks.md)<br/>