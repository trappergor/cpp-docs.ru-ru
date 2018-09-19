---
title: Предупреждение компилятора (уровень 4) C4336 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4336
dev_langs:
- C++
helpviewer_keywords:
- C4336
ms.assetid: 93f199dd-d6dd-42c0-82d8-c12d101a7235
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0ce0bc5a8a3df26a330de55c331d46b1f0c1d692
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46051175"
---
# <a name="compiler-warning-level-4-c4336"></a>Предупреждение компилятора (уровень 4) C4336

Импорт типов библиотеки «type_lib1» перед импортом «type_lib2»

Ссылка на библиотеку типов с [#import](../../preprocessor/hash-import-directive-cpp.md) директива. Тем не менее, библиотека типов содержит ссылку на другую библиотеку типов, который не был указан с `#import`. TLB-файл другой найден компилятором.

Две указанные библиотеки типов на диск, созданный из следующих двух файлах (скомпилированный с midl.exe):

```
// c4336a.idl
[uuid("f87070ba-c6d9-405c-a8e4-8cd9ca25c12b")]
library c4336aLib
{
   [uuid("f87070ba-c6d9-405c-a8e4-8cd9ca25c12c")]
   enum E_C4336
   {
      one, two, three
   };
};
```

Второй библиотеки типов:

```
// c4336b.idl
[uuid("f87070ba-c6d9-405c-a8e4-8cd9ca25c12d")]
library C4336bLib
{
   importlib ("c4336a.tlb");
   [uuid("f87070ba-c6d9-405c-a8e4-8cd9ca25c12e")]
   struct S_C4336
   {
      enum E_C4336 e;
   };
};
```

Следующий пример приводит к возникновению ошибки C4336:

```
// C4336.cpp
// compile with: /W4 /LD
// #import "C4336a.tlb"
#import "C4336b.tlb"   // C4336, uncomment previous line to resolve
```