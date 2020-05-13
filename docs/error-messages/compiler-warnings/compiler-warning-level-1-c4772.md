---
title: Предупреждение компилятора (уровень 1) C4772
ms.date: 11/04/2016
f1_keywords:
- C4772
helpviewer_keywords:
- C4772
ms.assetid: dafe6fd8-9faf-41f5-9d66-a55838742c14
ms.openlocfilehash: 89156b2f29fd21160e6abddc3ecb21efaee6dde1
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80175139"
---
# <a name="compiler-warning-level-1-c4772"></a>Предупреждение компилятора (уровень 1) C4772

> \#импорт ссылается на тип из отсутствующей библиотеки типов; в качестве заполнителя используется "*missed-Type*"

Ссылка на библиотеку типов была указана с помощью директивы [#import](../../preprocessor/hash-import-directive-cpp.md) . Однако библиотека типов содержала ссылку на другую библиотеку типов, на которую нет ссылок в `#import`. Этот файл TLB не найден компилятором.

Обратите внимание, что компилятор не обнаружит библиотеки типов в разных каталогах, если для указания этих каталогов используется параметр компилятора [/i (дополнительные каталоги включения)](../../build/reference/i-additional-include-directories.md) . Если требуется, чтобы компилятор нашел библиотеки типов в разных каталогах, добавьте эти каталоги в переменную среды PATH.

По умолчанию это предупреждение выдается как ошибка. C4772 не может быть подавлен с помощью/W0.

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

Это вторая библиотека типов, необходимая для воспроизведения C4772.

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
