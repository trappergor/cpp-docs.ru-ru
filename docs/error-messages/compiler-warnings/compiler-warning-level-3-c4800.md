---
title: Предупреждение компилятора (уровень 3) C4800 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4800
dev_langs:
- C++
helpviewer_keywords:
- C4800
ms.assetid: 4f409799-a250-45ed-bb5f-657691b0d9f7
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b5a19c27731192a5fe2930aec3e78fb66d790484
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46090911"
---
# <a name="compiler-warning-level-3-c4800"></a>Предупреждение компилятора (уровень 3) C4800

> "*тип*": принудительно задано логическое значение «true» или «false» (предупреждение о производительности)

Это предупреждение создается в том случае, если значение, не `bool` присваивается или преобразуется в тип `bool`. Как правило, это сообщение в результате назначения `int` переменных `bool` переменные где `int` переменная содержит только значения **true** и **false**и может быть повторно объявлен как тип `bool`. Если невозможно перезаписать выражение для использования типа `bool`, затем можно добавить "`!=0`" к выражению, предоставляющего тип выражения `bool`. Приведение выражения к типу `bool` не отключить предупреждения, что было сделано намеренно.

Это предупреждение больше не создается в Visual Studio 2017.

## <a name="example"></a>Пример

Следующий пример приводит к возникновению ошибки C4800 и показаны способы ее устранения:

```cpp
// C4800.cpp
// compile with: /W3
int main() {
   int i = 0;

   // To fix, instead try:
   // bool i = 0;

   bool j = i;   // C4800
   j++;
}
```