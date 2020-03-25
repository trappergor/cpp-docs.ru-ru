---
title: Комментарии языка ассемблера
ms.date: 08/30/2018
helpviewer_keywords:
- assembly language [C++], comments
- comments [C++], assembly language
- macros [C++], assembly language
- __asm keyword [C++], instructions
ms.assetid: 0dc10850-77f5-426e-9dab-185ea28e06e4
ms.openlocfilehash: a8b2c98c61d58d72e78dbffd4f3b6ed7707d2d7a
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80169608"
---
# <a name="assembly-language-comments"></a>Комментарии языка ассемблера

**Блок, относящийся только к системам Microsoft**

В инструкциях, которые находятся в блоке `__asm`, можно использовать комментарии в стиле языка ассемблера.

```cpp
__asm mov ax, offset buff ; Load address of buff
```

Поскольку макросы C развертываются в одну логическую строку, в них не следует использовать комментарии в стиле ассемблера. (См. раздел [определение __Asm блоков в качестве макросов C](../../assembler/inline/defining-asm-blocks-as-c-macros.md).) Блок `__asm` может также содержать комментарии в стиле C. Дополнительные сведения см. [в разделе Использование C C++ или в блоках __asm](../../assembler/inline/using-c-or-cpp-in-asm-blocks.md).

**Завершение блока, относящегося только к системам Майкрософт**

## <a name="see-also"></a>См. также раздел

[Использование языка ассемблера в блоках __asm](../../assembler/inline/using-assembly-language-in-asm-blocks.md)<br/>
