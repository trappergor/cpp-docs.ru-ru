---
title: Предупреждение компилятора (уровень 1) C4917
ms.date: 11/04/2016
f1_keywords:
- C4917
helpviewer_keywords:
- C4917
ms.assetid: c05e2610-4a5d-4f4b-a99b-c15fd7f1d5f1
ms.openlocfilehash: 97f6f0a08c8ef292d81471cb5d0d94e359466933
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62393497"
---
# <a name="compiler-warning-level-1-c4917"></a>Предупреждение компилятора (уровень 1) C4917

«оператор_объявления»: идентификатор GUID может быть связан только с классом, интерфейсом или пространством имен

Определяемая пользователем структура, отличных от [класс](../../cpp/class-cpp.md), [интерфейс](../../cpp/interface.md), или [пространство имен](../../cpp/namespaces-cpp.md) не может иметь идентификатор GUID.

Это предупреждение отключено по умолчанию. Подробнее: [Выключенные по умолчанию предупреждения компилятора](../../preprocessor/compiler-warnings-that-are-off-by-default.md) .

## <a name="example"></a>Пример

В следующем примере кода возникает C4917:

```cpp
// C4917.cpp
// compile with: /W1
#pragma warning(default : 4917)
__declspec(uuid("00000000-0000-0000-0000-000000000001")) struct S
{
} s;   // C4917, don't put uuid on a struct

int main()
{
}
```