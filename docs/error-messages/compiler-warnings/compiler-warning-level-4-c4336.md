---
title: Предупреждение компилятора (уровень 4) C4336
ms.date: 11/04/2016
f1_keywords:
- C4336
helpviewer_keywords:
- C4336
ms.assetid: 93f199dd-d6dd-42c0-82d8-c12d101a7235
ms.openlocfilehash: 33c4a25618c1afcf93704b161483bc4c0a6e16a0
ms.sourcegitcommit: d0504e2337bb671e78ec6dd1c7b05d89e7adf6a7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2019
ms.locfileid: "74683323"
---
# <a name="compiler-warning-level-4-c4336"></a>Предупреждение компилятора (уровень 4) C4336

импортировать библиотеку типов "type_lib1" для перекрестных ссылок перед импортом "type_lib2"

Ссылка на библиотеку типов была указана с помощью директивы [#import](../../preprocessor/hash-import-directive-cpp.md) . Однако библиотека типов содержала ссылку на другую библиотеку типов, на которую нет ссылок в `#import`. Этот файл TLB был найден компилятором.

При наличии двух библиотек типов на диске, созданных из следующих двух файлов (скомпилированных с помощью MIDL. exe):

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

Вторая библиотека типов:

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

```cpp
// C4336.cpp
// compile with: /W4 /LD
// #import "C4336a.tlb"
#import "C4336b.tlb"   // C4336, uncomment previous line to resolve
```