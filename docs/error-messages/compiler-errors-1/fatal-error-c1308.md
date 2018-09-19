---
title: Неустранимая ошибка C1308 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C1308
dev_langs:
- C++
helpviewer_keywords:
- C1308
ms.assetid: 46177997-069e-433a-8e20-93c846d78ffd
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: dd778e95f3ace413dbeb409da3c4b2493208e8bf
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46104191"
---
# <a name="fatal-error-c1308"></a>Неустранимая ошибка C1308

Связывание сборок не поддерживается

.Netmodule допустим в качестве входных данных компоновщика, но не сборка. Это ошибка может возникать при попытке связать сборки, скомпилированной с `/clr:safe`.

Дополнительные сведения см. в разделе [NETMODULE-файлы в качестве входных файлов компоновщика](../../build/reference/netmodule-files-as-linker-input.md).

Следующий пример приводит к возникновению ошибки C1308:

```
// C1308.cpp
// compile with: /clr:safe /LD
public ref class MyClass {
public:
   int i;
};
```

И потом

```
// C1308b.cpp
// compile with: /clr /link C1308b.obj C1308.dll
// C1308 expected
#using "C1308.dll"
int main() {
   MyClass ^ my = gcnew MyClass();
}
```