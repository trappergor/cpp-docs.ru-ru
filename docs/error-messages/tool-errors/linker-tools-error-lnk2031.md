---
title: Ошибка средств компоновщика LNK2031
ms.date: 11/04/2016
f1_keywords:
- LNK2031
helpviewer_keywords:
- LNK2031
ms.assetid: 18ed4b6e-3e75-443c-bbd8-2f6030dc89ee
ms.openlocfilehash: 096ccb7ff443d24e0d53e73a5950faa1e85aeae6
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80194568"
---
# <a name="linker-tools-error-lnk2031"></a>Ошибка средств компоновщика LNK2031

> не удалось создать p/Invoke для "*function_declaration*" *decorated_name*; Соглашение о вызовах отсутствует в метаданных

## <a name="remarks"></a>Remarks

При попытке импортировать собственную функцию в чистый образ Помните, что неявные соглашения о вызовах отличаются от собственных и чистых компиляций. Дополнительные сведения об чистых образах см. в разделе [чистый иC++проверяемый код (/CLI)](../../dotnet/pure-and-verifiable-code-cpp-cli.md).

Параметр компилятора **/clr: pure** является устаревшим в visual Studio 2015 и не поддерживается в visual Studio 2017.

## <a name="example"></a>Пример

Этот пример кода создает компонент с экспортированной собственной функцией, соглашение о вызовах которого неявно [__cdecl](../../cpp/cdecl.md).

```cpp
// LNK2031.cpp
// compile with: /LD
extern "C" {
   __declspec(dllexport) int func() { return 3; }
};
```

## <a name="example"></a>Пример

В следующем примере создается чистый клиент, использующий собственную функцию. Однако соглашение о вызовах в **/clr: pure** [__clrcall](../../cpp/clrcall.md). Следующий пример приводит к возникновению ошибки LNK2031.

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

В следующем примере показано, как использовать собственную функцию из чистого образа. Обратите внимание на явный описатель соглашения о вызове **__cdecl** .

```cpp
// LNK2031_c.cpp
// compile with: /clr:pure LNK2031.lib
extern "C" int __cdecl func();

int main() {
   return func();
}
```
