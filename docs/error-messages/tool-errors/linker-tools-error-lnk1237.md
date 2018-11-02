---
title: Ошибка средств компоновщика LNK1237
ms.date: 11/04/2016
f1_keywords:
- LNK1237
helpviewer_keywords:
- LNK1237
ms.assetid: 8722ffa8-096a-4bb0-85f9-f3aa0e10872a
ms.openlocfilehash: ae1a397cdcc10cd89fd046a94e78c15dd46dceed
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50581328"
---
# <a name="linker-tools-error-lnk1237"></a>Ошибка средств компоновщика LNK1237

При создании кода компилятор ввел ссылку на символ «символ», определенный в модуле «модуль», откомпилированном с параметром /GL

При создании кода компилятор не должен вводить символы, которые позднее разрешаются в определения компиляции **/GL**. `symbol` — это символ, введенный и более поздней версии, разрешенный для определения, скомпилированного с **/GL**.

Дополнительные сведения см. в разделе [/GL (оптимизация всей программы)](../../build/reference/gl-whole-program-optimization.md).

Чтобы устранить ошибку LNK1237, не компилируйте символ с **/GL** или использовать [/Include (принудительное ссылки на символы)](../../build/reference/include-force-symbol-references.md) для принудительного создания ссылки на символ.

## <a name="example"></a>Пример

Следующий пример приводит к возникновению ошибки LNK1237. Чтобы устранить эту ошибку, не инициализируйте массив в файле LNK1237_a.cpp и добавьте **/ include: __chkstk** к команде link.

```
// LNK1237_a.cpp
int main() {
   char c[5000] = {0};
}
```

```
// LNK1237_b.cpp
// compile with: /GS- /GL /c LNK1237_a.cpp
// processor: x86
// post-build command: (lib LNK1237_b.obj /LTCG & link LNK1237_a.obj LNK1237_b.lib /nodefaultlib /entry:main /LTCG)
extern "C" void _chkstk(size_t s) {}
```