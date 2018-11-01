---
title: Ошибка средств компоновщика LNK2031
ms.date: 11/04/2016
f1_keywords:
- LNK2031
helpviewer_keywords:
- LNK2031
ms.assetid: 18ed4b6e-3e75-443c-bbd8-2f6030dc89ee
ms.openlocfilehash: 003b9a58bfb08130f034530f59e2de27efa2ae8d
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50484850"
---
# <a name="linker-tools-error-lnk2031"></a>Ошибка средств компоновщика LNK2031

> не удалось создать p/invoke для "*function_declaration*" *decorated_name*; в метаданных отсутствует соглашение о вызовах

## <a name="remarks"></a>Примечания

При попытке импортировать неуправляемую функцию в чистом образе, помните, что неявные соглашения о вызовах различаются между внутренней и чистой компиляции. Дополнительные сведения о чисто образах см. в разделе [чистый и проверяемый код (C + +/ CLI)](../../dotnet/pure-and-verifiable-code-cpp-cli.md).

**/CLR: pure** параметр компилятора в Visual Studio 2015 не рекомендуется и не поддерживается в Visual Studio 2017.

## <a name="example"></a>Пример

Этот пример кода создает компонент с функцией экспортированного, native, которого соглашение о вызовах является неявно [__cdecl](../../cpp/cdecl.md).

```cpp
// LNK2031.cpp
// compile with: /LD
extern "C" {
   __declspec(dllexport) int func() { return 3; }
};
```

## <a name="example"></a>Пример

В следующем примере создается чистый клиент, использующий внутреннюю функцию. Тем не менее соглашение о вызовах в разделе **/CLR: pure** — [__clrcall](../../cpp/clrcall.md). Следующий пример приводит к возникновению ошибки LNK2031.

```cpp
// LNK2031_b.cpp
// compile with: /clr:pure LNK2031.lib
// LNK2031 expected
extern "C" int func();

int main() {
   return func();
}
```

## <a name="example"></a>Пример

Следующий пример показано, как использовать внутреннюю функцию для чистого образа. Обратите внимание на явный **__cdecl** вызов описателя соглашения.

```cpp
// LNK2031_c.cpp
// compile with: /clr:pure LNK2031.lib
extern "C" int __cdecl func();

int main() {
   return func();
}
```