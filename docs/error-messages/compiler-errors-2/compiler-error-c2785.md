---
title: Ошибка компилятора C2785
ms.date: 11/04/2016
f1_keywords:
- C2785
helpviewer_keywords:
- C2785
ms.assetid: d8d13360-0d00-4815-8475-b49c7f0dc0f3
ms.openlocfilehash: fcf2bbb01f2aac668ff52884a6ccfb36c66aa89d
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62395382"
---
# <a name="compiler-error-c2785"></a>Ошибка компилятора C2785

«объявление1» и «объявление2» имеют различные возвращаемые типы

Тип возвращаемого значения специализации шаблона функции отличается от тип возвращаемого значения шаблона основной функции.

### <a name="to-correct-this-error"></a>Исправление ошибки

1. Проверьте все специализации шаблона функции для обеспечения согласованности.

## <a name="example"></a>Пример

Следующий пример приводит к возникновению ошибки C2785:

```
// C2785.cpp
// compile with: /c
template<class T> void f(T);

template<> int f(int); // C2785
template<> void f(int); // OK
```