---
title: Ошибка средств компоновщика LNK1237
ms.date: 11/04/2016
f1_keywords:
- LNK1237
helpviewer_keywords:
- LNK1237
ms.assetid: 8722ffa8-096a-4bb0-85f9-f3aa0e10872a
ms.openlocfilehash: c56b2eb86c7605fb3330d7b1bb01e3235466ede6
ms.sourcegitcommit: 573b36b52b0de7be5cae309d45b68ac7ecf9a6d8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2019
ms.locfileid: "74990959"
---
# <a name="linker-tools-error-lnk1237"></a>Ошибка средств компоновщика LNK1237

во время создания кода компилятор представил ссылку на символ "Symbol", определенный в модуле "Module", скомпилированном с параметром/GL

Во время создания кода компилятор не должен вводить символы, которые позже разрешаются в определениях, скомпилированных с параметром **/GL**. `symbol` — это символ, который был введен и позднее разрешается в определение, скомпилированное с параметром **/GL**.

Дополнительные сведения см. в разделе [/GL (оптимизация всей программы)](../../build/reference/gl-whole-program-optimization.md).

Чтобы разрешить LNK1237, не компилируйте символ с параметром **/GL** или используйте [/include (принудительные ссылки на символы)](../../build/reference/include-force-symbol-references.md) для принудительной ссылки на символ.

## <a name="example"></a>Пример

Следующий пример приводит к возникновению ошибки LNK1237. Чтобы устранить эту ошибку, не инициализируйте массив в LNK1237_a. cpp и добавьте **/include: __chkstk** в команду Link.

```cpp
// LNK1237_a.cpp
int main() {
   char c[5000] = {0};
}
```

```cpp
// LNK1237_b.cpp
// compile with: /GS- /GL /c LNK1237_a.cpp
// processor: x86
// post-build command: (lib LNK1237_b.obj /LTCG & link LNK1237_a.obj LNK1237_b.lib /nodefaultlib /entry:main /LTCG)
extern "C" void _chkstk(size_t s) {}
```
