---
title: Ошибка компилятора C2765
ms.date: 11/04/2016
f1_keywords:
- C2765
helpviewer_keywords:
- C2765
ms.assetid: 47ad86f3-a7e0-47ad-85ff-0f5534458cb9
ms.openlocfilehash: 7b34bd8b352e8872722e9402d8d0113ae6157292
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62257651"
---
# <a name="compiler-error-c2765"></a>Ошибка компилятора C2765

«функция»: явная специализация шаблона функции не может иметь аргументы по умолчанию

Аргументы по умолчанию не разрешены для явной специализации шаблона функции. Дополнительные сведения см. в разделе [явная специализация шаблонов функций](../../cpp/explicit-specialization-of-function-templates.md).

Следующий пример приводит к возникновению ошибки C2765:

```
// C2765.cpp
template<class T> void f(T t) {};

template<> void f<char>(char c = 'a') {}   // C2765
// try the following line instead
// template<> void f<char>(char c) {}
```