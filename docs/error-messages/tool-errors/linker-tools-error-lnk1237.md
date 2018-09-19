---
title: Ошибка средств компоновщика LNK1237 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK1237
dev_langs:
- C++
helpviewer_keywords:
- LNK1237
ms.assetid: 8722ffa8-096a-4bb0-85f9-f3aa0e10872a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f9ada38fcf3a706f7852f49f60f677fb5dc10d7e
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46065300"
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