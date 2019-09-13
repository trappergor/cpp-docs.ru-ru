---
title: Предупреждение компилятора (уровень 4) C4242
ms.date: 11/04/2016
f1_keywords:
- C4242
helpviewer_keywords:
- C4242
ms.assetid: 8df742e1-fbf1-42f3-8e93-c0e1c222dc7e
ms.openlocfilehash: ed145444d6eec583c448a3a49167ca1f82644f0b
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/15/2019
ms.locfileid: "69510011"
---
# <a name="compiler-warning-level-4-c4242"></a>Предупреждение компилятора (уровень 4) C4242

"идентификатор": преобразование из "тип1" в "тип2", возможна утрата данных

Типы различаются. Преобразование типов может привести к утрате данных. Компилятор выполняет преобразование типов.

Это предупреждение отключено по умолчанию. Подробнее: [Выключенные по умолчанию предупреждения компилятора](../../preprocessor/compiler-warnings-that-are-off-by-default.md) .

Дополнительные сведения о C4242 см. в разделе [Общие ошибки компилятора](/windows/win32/WinProg64/common-compiler-errors).

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