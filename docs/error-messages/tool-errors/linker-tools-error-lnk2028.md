---
title: Ошибка средств компоновщика LNK2028
ms.date: 11/04/2016
f1_keywords:
- LNK2028
helpviewer_keywords:
- LNK2028
ms.assetid: e2b03293-6066-464d-a050-ce747bcf7f0e
ms.openlocfilehash: ed2dc1a95d4dd7c447b360da21b5046e20f79083
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50643681"
---
# <a name="linker-tools-error-lnk2028"></a>Ошибка средств компоновщика LNK2028

"*exported_function*" (*decorated_name*) на которые ссылается функция "*function_containing_function_call*" (*decorated_name*)

## <a name="remarks"></a>Примечания

При попытке импортировать неуправляемую функцию в чистом образе, помните, что неявные соглашения о вызовах различаются между внутренней и чистой компиляции.

**/CLR: pure** параметр компилятора в Visual Studio 2015 не рекомендуется и не поддерживается в Visual Studio 2017.

## <a name="example"></a>Пример

Этот пример кода создает компонент с функцией экспортированного, native, которого соглашение о вызовах является неявно [__cdecl](../../cpp/cdecl.md).

```cpp
// LNK2028.cpp
// compile with: /LD
__declspec(dllexport) int func() {
   return 3;
}
```

## <a name="example"></a>Пример

В следующем примере создается чистый клиент, использующий внутреннюю функцию. Тем не менее соглашение о вызовах в разделе **/CLR: pure** — [__clrcall](../../cpp/clrcall.md). Следующий пример приводит к возникновению ошибки LNK2028.

```cpp
// LNK2028_b.cpp
// compile with: /clr:pure lnk2028.lib
// LNK2028 expected
int func();

int main() {
   return func();
}
```