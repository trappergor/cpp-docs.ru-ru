---
title: Предупреждение компилятора (уровень 1) C4772
ms.date: 11/04/2016
f1_keywords:
- C4772
helpviewer_keywords:
- C4772
ms.assetid: dafe6fd8-9faf-41f5-9d66-a55838742c14
ms.openlocfilehash: 95243ab66d5d0296e1c316ff8dde7add75a030cd
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50540027"
---
# <a name="compiler-warning-level-1-c4772"></a>Предупреждение компилятора (уровень 1) C4772

> \#Импорт ссылается на тип из отсутствующей библиотеки типов; "*отсутствует тип*" используется в качестве заполнителя

Ссылка на библиотеку типов с [#import](../../preprocessor/hash-import-directive-cpp.md) директива. Тем не менее, библиотека типов содержит ссылку на другую библиотеку типов, который не был указан с `#import`. Этот TLB-файл не найден компилятор.

Обратите внимание, что компилятор не найдет библиотеки типов в разных каталогах при использовании [/I (Дополнительные каталоги включаемых файлов)](../../build/reference/i-additional-include-directories.md) параметр компилятора для указания этих каталогов. Если требуется, чтобы компилятор для поиска библиотеки типов в разных каталогах, добавьте их в переменную среды PATH.

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