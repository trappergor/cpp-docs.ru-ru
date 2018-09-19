---
title: Ошибка компилятора C3834 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3834
dev_langs:
- C++
helpviewer_keywords:
- C3834
ms.assetid: 059e0dc4-300b-4e74-b6c2-41a57831fe2a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 1032c8210cc3df8f9000452ebe18576a10cf5437
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46072762"
---
# <a name="compiler-error-c3834"></a>Ошибка компилятора C3834

недопустимое явное приведение к Закрепляющему указателю; Вместо этого используйте закрепленную локальную переменную

Явное приведение закрепляющий указатель не допускаются.

## <a name="example"></a>Пример

Следующий пример приводит к возникновению ошибки C3834.

```
// C3834.cpp
// compile with: /clr
int main() {
   int x = 33;

   pin_ptr<int> p = safe_cast<pin_ptr<int> >(&x);   // C3834
   pin_ptr<int> p2 = &x;   // OK
}
```
