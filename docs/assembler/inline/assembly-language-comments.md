---
title: Комментарии языка ассемблера
ms.date: 08/30/2018
helpviewer_keywords:
- assembly language [C++], comments
- comments [C++], assembly language
- macros [C++], assembly language
- __asm keyword [C++], instructions
ms.assetid: 0dc10850-77f5-426e-9dab-185ea28e06e4
ms.openlocfilehash: fc37658eccd99b61d45aa9a9a7a2675ef90eee89
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50578649"
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