---
title: Сегмент ссылок во встроенной сборке | Документация Майкрософт
ms.custom: ''
ms.date: 08/30/2018
ms.technology:
- cpp-masm
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- references, inline assembly
- segment references in inline assembly
- inline assembly, segment references
- registers
- inline assembly, registers
- registers, inline assembly
ms.assetid: c63e6bb4-49d9-4fa1-bb22-eea21b5cbc0f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 792dda60407928aaf4a7d3fec2a61c0018b8b35a
ms.sourcegitcommit: a7046aac86f1c83faba1088c80698474e25fe7c3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/04/2018
ms.locfileid: "43676393"
---
# <a name="segment-references-in-inline-assembly"></a>Ссылки на сегменты во встроенном коде на языке ассемблера

**Блок, относящийся только к системам Microsoft**

Ссылаться на сегменты следует по регистру, а не по имени (например, имя сегмента `_TEXT` недопустимо). В переопределениях сегментов необходимо явно использовать регистр, как в ES:[BX].

**Завершение блока, относящегося только к системам Майкрософт**

## <a name="see-also"></a>См. также

[Использование языка ассемблера в блоках __asm](../../assembler/inline/using-assembly-language-in-asm-blocks.md)<br/>