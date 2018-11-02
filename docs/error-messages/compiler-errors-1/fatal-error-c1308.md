---
title: Неустранимая ошибка C1308
ms.date: 11/04/2016
f1_keywords:
- C1308
helpviewer_keywords:
- C1308
ms.assetid: 46177997-069e-433a-8e20-93c846d78ffd
ms.openlocfilehash: 0128953b3b3fa0f29a6764c1d7dab0ece67dfae7
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50640626"
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