---
title: Комментарии языка ассемблера | Документация Майкрософт
ms.custom: ''
ms.date: 08/30/2018
ms.technology:
- cpp-masm
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- assembly language [C++], comments
- comments [C++], assembly language
- macros [C++], assembly language
- __asm keyword [C++], instructions
ms.assetid: 0dc10850-77f5-426e-9dab-185ea28e06e4
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 02f4c493bac5c2a066dc0b24e2a566d49345288d
ms.sourcegitcommit: a7046aac86f1c83faba1088c80698474e25fe7c3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/04/2018
ms.locfileid: "43683330"
---
# <a name="assembly-language-comments"></a>Комментарии языка ассемблера

**Блок, относящийся только к системам Microsoft**

В инструкциях, которые находятся в блоке `__asm`, можно использовать комментарии в стиле языка ассемблера.

```cpp
__asm mov ax, offset buff ; Load address of buff
```

Поскольку макросы C развертываются в одну логическую строку, в них не следует использовать комментарии в стиле ассемблера. (См. в разделе [определение блоков __asm как макросов C](../../assembler/inline/defining-asm-blocks-as-c-macros.md).) `__asm` Блок может также содержать комментарии в стиле C; Дополнительные сведения см. в разделе [использование C или C++ в блоках __asm](../../assembler/inline/using-c-or-cpp-in-asm-blocks.md).

**Завершение блока, относящегося только к системам Майкрософт**

## <a name="see-also"></a>См. также

[Использование языка ассемблера в блоках __asm](../../assembler/inline/using-assembly-language-in-asm-blocks.md)<br/>