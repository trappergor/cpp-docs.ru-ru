---
title: Ошибка средств компоновщика LNK1301
ms.date: 11/04/2016
f1_keywords:
- LNK1301
helpviewer_keywords:
- LNK1301
ms.assetid: 760da428-7182-4b25-b20a-de90d4b9a9cd
ms.openlocfilehash: fe64eecfbc9fed57c3748afd5804b76d6e4284a4
ms.sourcegitcommit: 573b36b52b0de7be5cae309d45b68ac7ecf9a6d8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2019
ms.locfileid: "74990936"
---
# <a name="linker-tools-error-lnk1301"></a>Ошибка средств компоновщика LNK1301

Найдены модули CLR LTCG, несовместимые с/LTCG: Parameter

Модуль, скомпилированный с параметрами/CLR и/GL, передан компоновщику вместе с одним из параметров профильной оптимизации (PGO)/ЛТКГ.

Оптимизированные для профилирования оптимизации не поддерживаются для модулей/CLR.

Дополнительные сведения см. в следующих разделах.

- [/GL (оптимизация всей программы)](../../build/reference/gl-whole-program-optimization.md)

- [/LTCG (создание кода во время компоновки)](../../build/reference/ltcg-link-time-code-generation.md)

- [/clr (компиляция среды выполнения)](../../build/reference/clr-common-language-runtime-compilation.md)

- [Профильная оптимизация](../../build/profile-guided-optimizations.md)

### <a name="to-correct-this-error"></a>Исправление ошибки

1. Не компилируйте с параметром/CLR или не используйте компоновку с одним из параметров PGO в/ЛТКГ.

## <a name="example"></a>Пример

Следующий пример приводит к возникновению ошибки LNK1301:

```cpp
// LNK1301.cpp
// compile with: /clr /GL /link /LTCG:PGI LNK1301.obj
// LNK1301 expected
class MyClass {
public:
   int i;
};
```
