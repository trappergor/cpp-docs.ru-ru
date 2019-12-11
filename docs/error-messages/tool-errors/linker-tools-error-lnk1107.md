---
title: Ошибка средств компоновщика LNK1107
ms.date: 11/04/2016
f1_keywords:
- LNK1107
helpviewer_keywords:
- LNK1107
ms.assetid: a37a893d-5efa-4eba-8f40-6c5518b4b9d0
ms.openlocfilehash: c75966d9c6c22f1bd2123fb30282bb2bed467130
ms.sourcegitcommit: 573b36b52b0de7be5cae309d45b68ac7ecf9a6d8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2019
ms.locfileid: "74991026"
---
# <a name="linker-tools-error-lnk1107"></a>Ошибка средств компоновщика LNK1107

Недопустимый или поврежденный файл: не удается прочитать в расположении

Средству не удалось прочитать файл. Повторно создайте файл.

LNK1107 также может возникнуть при попытке передать компоновщику модуль (DLL или. netmodule, созданный с [параметром/clr: Assembly](../../build/reference/clr-common-language-runtime-compilation.md) или [/NOASSEMBLY](../../build/reference/noassembly-create-a-msil-module.md)); Вместо этого передайте OBJ-файл.

При компиляции следующего образца:

```cpp
// LNK1107.cpp
// compile with: /clr /LD
public ref class MyClass {
public:
   void Test(){}
};
```

а затем указать **link LNK1107. dll** в командной строке, вы получите LNK1107.  Чтобы устранить эту ошибку, укажите **link LNK1107. obj** .
