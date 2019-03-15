---
title: Ошибка средств компоновщика LNK1301
ms.date: 11/04/2016
f1_keywords:
- LNK1301
helpviewer_keywords:
- LNK1301
ms.assetid: 760da428-7182-4b25-b20a-de90d4b9a9cd
ms.openlocfilehash: 6a82d7756f1460c56d87a3d7b1360c140de19827
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2019
ms.locfileid: "57812100"
---
# <a name="linker-tools-error-lnk1301"></a>Ошибка средств компоновщика LNK1301

Найден, несовместимые с /LTCG:parameter модули среды LTCG clr

Модуле, скомпилированном с параметром/CLR и /GL передан компоновщику вместе с одной из профильной оптимизации (PGO) параметров/LTCG.

Оптимизация, управляемая профилями, не поддерживаются для модулей/CLR.

Дополнительные сведения см. в следующих разделах.

- [/GL (оптимизация всей программы)](../../build/reference/gl-whole-program-optimization.md)

- [/LTCG (создание кода во время компоновки)](../../build/reference/ltcg-link-time-code-generation.md)

- [/clr (компиляция среды выполнения)](../../build/reference/clr-common-language-runtime-compilation.md)

- [Профильная оптимизация](../../build/profile-guided-optimizations.md)

### <a name="to-correct-this-error"></a>Исправление ошибки

1. Не компилировать с параметром/CLR или не создавать связь с одним из параметров профильной Оптимизации/LTCG.

## <a name="example"></a>Пример

В следующем примере возникает ошибка LNK1301:

```
// LNK1301.cpp
// compile with: /clr /GL /link /LTCG:PGI LNK1301.obj
// LNK1301 expected
class MyClass {
public:
   int i;
};
```