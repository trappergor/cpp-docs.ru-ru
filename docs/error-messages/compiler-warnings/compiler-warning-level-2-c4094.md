---
title: Предупреждение (уровень 2) C4094 компилятора | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4094
dev_langs:
- C++
helpviewer_keywords:
- C4094
ms.assetid: e68929fb-3a1c-4be7-920b-d5f79f534f99
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 2b9317cbc31ef8bddb14da11af1087a148fd3188
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46078716"
---
# <a name="compiler-warning-level-2-c4094"></a>Компилятор предупреждение (уровень 2) C4094

без тега «токен» не объявлены символы

Компилятор обнаружил пустое объявление, с помощью непомеченный структуры, объединения или класса. Объявление учитывается.

## <a name="example"></a>Пример

```
// C4094.cpp
// compile with: /W2
struct
{
};   // C4094

int main()
{
}
```

Это условие вызывает ошибку совместимости ANSI ([/Za](../../build/reference/za-ze-disable-language-extensions.md)).