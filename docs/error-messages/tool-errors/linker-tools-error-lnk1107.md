---
title: Ошибка средств компоновщика LNK1107
ms.date: 11/04/2016
f1_keywords:
- LNK1107
helpviewer_keywords:
- LNK1107
ms.assetid: a37a893d-5efa-4eba-8f40-6c5518b4b9d0
ms.openlocfilehash: 68048d9f824283d002a4ea8b64d88f37bbeefc48
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50646567"
---
# <a name="linker-tools-error-lnk1107"></a>Ошибка средств компоновщика LNK1107

Недопустимый или поврежденный файл: не удается прочитать в расположении

Средство не удалось прочитать файл. Повторно создайте файл.

LNK1107 также может возникать при попытке передать модуль (расширение DLL или .netmodule, созданных с помощью [/clr:noAssembly](../../build/reference/clr-common-language-runtime-compilation.md) или [/NOASSEMBLY предписывает](../../build/reference/noassembly-create-a-msil-module.md)) в компоновщик; передать OBJ-файле, вместо этого.

При компиляции следующего примера:

```
// LNK1107.cpp
// compile with: /clr /LD
public ref class MyClass {
public:
   void Test(){}
};
```

а затем укажите **связать LNK1107.dll** в командной строке, вы получите LNK1107.  Чтобы устранить эту ошибку, укажите **связать LNK1107.obj** вместо этого.