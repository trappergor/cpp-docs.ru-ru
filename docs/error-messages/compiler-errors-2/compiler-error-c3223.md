---
title: Ошибка компилятора C3223 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3223
dev_langs:
- C++
helpviewer_keywords:
- C3223
ms.assetid: 1f4380b4-0413-40db-a868-62f97babaf78
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 18a035d5a5be5e74d6925277dc1dc62bec8639c2
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46036505"
---
# <a name="compiler-error-c3223"></a>Ошибка компилятора C3223

"свойство": нельзя применить typeid к свойству

Нельзя применить [typeid](../../windows/typeid-cpp-component-extensions.md) к свойству.

## <a name="example"></a>Пример

В следующем примере возникает ошибка C3223:

```
// C3223.cpp
// compile with: /clr
ref class R {
public:
   property int myprop;
};

int main() {
   System::Type^ type2 = R::myprop::typeid;   // C3223
}
```