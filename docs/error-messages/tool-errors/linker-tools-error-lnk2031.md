---
title: Ошибка средств компоновщика LNK2031 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK2031
dev_langs:
- C++
helpviewer_keywords:
- LNK2031
ms.assetid: 18ed4b6e-3e75-443c-bbd8-2f6030dc89ee
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d86ea6da8a73d9ba2427e9455c4fca87cd32dd2b
ms.sourcegitcommit: a4454b91d556a3dc43d8755cdcdeabcc9285a20e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2018
ms.locfileid: "34703669"
---
# <a name="linker-tools-error-lnk2031"></a>Ошибка средств компоновщика LNK2031

> не удалось создать p/invoke "*function_declaration*» *decorated_name*; в метаданных отсутствует соглашение о вызовах

## <a name="remarks"></a>Примечания

При попытке импортировать собственную функцию в чистом образе, следует помнить, что неявные соглашения о вызовах различаются внутренней и чистой компиляции. Дополнительные сведения об образах чисто см [чистый и проверяемый код (C + +/ CLI)](../../dotnet/pure-and-verifiable-code-cpp-cli.md).

**/CLR: pure** параметр компилятора в Visual Studio 2015 не рекомендуется и не поддерживается в Visual Studio 2017 г.

## <a name="example"></a>Пример

Этот пример кода приводит к возникновению ошибки компонента с экспортированного native, функции которого соглашение о вызовах является неявно [__cdecl](../../cpp/cdecl.md).

```cpp
// LNK2031.cpp
// compile with: /LD
extern "C" {
   __declspec(dllexport) int func() { return 3; }
};
```

## <a name="example"></a>Пример

В следующем примере создается чистый клиент, использующий внутреннюю функцию. Тем не менее соглашение о вызовах в **/CLR: pure** — [__clrcall](../../cpp/clrcall.md). Следующий пример приводит к возникновению ошибки LNK2031.

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