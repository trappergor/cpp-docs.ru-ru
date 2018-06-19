---
title: Предупреждение (уровень 1) C4772 компилятора | Документы Microsoft
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4772
dev_langs:
- C++
helpviewer_keywords:
- C4772
ms.assetid: dafe6fd8-9faf-41f5-9d66-a55838742c14
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: cbdcfec8d36568c31c291a9de8f9af3aac821fc6
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33282276"
---
# <a name="compiler-warning-level-1-c4772"></a>Предупреждение компилятора (уровень 1) C4772

> \#Импорт ссылается на тип из отсутствующей библиотеки типов; "*отсутствует тип*" используется как заполнитель

Библиотека типов была ссылка в [#import](../../preprocessor/hash-import-directive-cpp.md) директивы. Однако эта библиотека типов содержит ссылку на другую библиотеку типов, который не был указан с `#import`. Это TLB-файл компилятором не найден.

Обратите внимание, что компилятор не найдет библиотеки типов в разных каталогах, при использовании [/I (Дополнительные каталоги включаемых файлов)](../../build/reference/i-additional-include-directories.md) параметр компилятора для указания этих каталогов. Если требуется, чтобы компилятор нашел библиотеки типов в разных каталогах, добавьте их переменной среды PATH.

По умолчанию это предупреждение выдается как ошибка. C4772 не может быть отменено с помощью/W0.

## <a name="example"></a>Пример

Это первая библиотека типов, необходимая для воспроизведения C4772.

```IDL
// c4772a.idl
[uuid("f87070ba-c6d9-405c-a8e4-8cd9ca25c12b")]
library C4772aLib
{
   [uuid("f87070ba-c6d9-405c-a8e4-8cd9ca25c100")]
   enum E_C4772a
   {
      one, two, three
   };
};
```

Это второй библиотеки типов, необходимая для воспроизведения C4772.

```IDL
// c4772b.idl
// post-build command: del /f C4772a.tlb
// C4772a.tlb is available when c4772b.tlb is built
[uuid("f87070ba-c6d9-405c-a8e4-8cd9ca25c12d")]
library C4772bLib
{
   importlib ("c4772a.tlb");
   [uuid("f87070ba-c6d9-405c-a8e4-8cd9ca25c12e")]
   struct S_C4772b
   {
      enum E_C4772a e;
   };
};
```

Следующий пример приводит к возникновению ошибки C4772:

```cpp
// C4772.cpp
// assumes that C4772a.tlb is not available to the compiler
// #import "C4772a.tlb"
#import "C4772b.tlb"   // C4772 uncomment previous line to resolve
                       // and make sure c4772a.tlb is on disk
```