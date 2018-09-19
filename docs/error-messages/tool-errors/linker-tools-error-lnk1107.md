---
title: Ошибка средств компоновщика LNK1107 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK1107
dev_langs:
- C++
helpviewer_keywords:
- LNK1107
ms.assetid: a37a893d-5efa-4eba-8f40-6c5518b4b9d0
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 73a1643d10ea9adc6ac6979eb2de023593ba8d01
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46060711"
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