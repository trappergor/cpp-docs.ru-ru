---
title: Предупреждение компилятора (уровень 1) C4917 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4917
dev_langs:
- C++
helpviewer_keywords:
- C4917
ms.assetid: c05e2610-4a5d-4f4b-a99b-c15fd7f1d5f1
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 741f847e4df8095e5e91e14dd67e36c6d161071d
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46046268"
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