---
title: Предупреждение компилятора (уровень 4) C4242 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4242
dev_langs:
- C++
helpviewer_keywords:
- C4242
ms.assetid: 8df742e1-fbf1-42f3-8e93-c0e1c222dc7e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 9879b9258902a496dd46c59c44f7bf211726e460
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46056876"
---
# <a name="compiler-warning-level-4-c4242"></a>Предупреждение компилятора (уровень 4) C4242

«Идентификатор»: преобразование из «тип1» в «тип2», возможна потеря данных

Типы являются разными. Преобразование типа может привести к потере данных. Преобразование типа выполняется компилятором.

Это предупреждение отключено по умолчанию. Подробнее: [Выключенные по умолчанию предупреждения компилятора](../../preprocessor/compiler-warnings-that-are-off-by-default.md) .

Дополнительные сведения об ошибке C4242 см. в разделе [типичные ошибки компилятора](/windows/desktop/WinProg64/common-compiler-errors).

Следующий пример приводит к возникновению ошибки C4242:

```
// C4242.cpp
// compile with: /W4
#pragma warning(4:4242)
int func() {
   return 0;
}

int main() {
   char a;
   a = func();   // C4242, return type and variable type do not match
}
```