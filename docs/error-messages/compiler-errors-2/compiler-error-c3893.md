---
title: Ошибка компилятора C3893 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3893
dev_langs:
- C++
helpviewer_keywords:
- C3893
ms.assetid: 90d52eae-6ef2-4db1-b7ad-92f9e8b140fb
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 857d13de61f03bf0784d8cd10ad092d16f7acdaa
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46087051"
---
# <a name="compiler-error-c3893"></a>Ошибка компилятора C3893

«var»: l значения можно использовать данные-член initonly допускается только в конструкторе экземпляра класса «имя_типа»

Статические [initonly](../../dotnet/initonly-cpp-cli.md) данные-члены можно только получить свои адреса в статическом конструкторе.

Элементы данных initonly (не статического) экземпляра может иметь только адреса в конструкторы экземпляров (не статического).

Следующий пример приводит к возникновению ошибки C3893:

```
// C3893.cpp
// compile with: /clr
ref struct Y1 {
   Y1() : data_var(0) {
      int% i = data_var;   // OK
   }
   initonly int data_var;
};

int main(){
   Y1^ y= gcnew Y1;
   int% i = y->data_var;   // C3893
}
```