---
title: Ошибка компилятора C2993 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2993
dev_langs:
- C++
helpviewer_keywords:
- C2993
ms.assetid: 4ffd2b78-654b-46aa-95a6-b62101cf91c8
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 09b3c789cc15d2e146f1c5031003fc74d783e827
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46081947"
---
# <a name="compiler-error-c2993"></a>Ошибка компилятора C2993

«Идентификатор»: недопустимый тип, не являющегося типом шаблона для параметра «параметр»

Не удается объявить шаблон с аргументом структуры или объединения. Использование указателей для передачи структур и объединений в качестве параметров шаблона.

Следующий пример приводит к возникновению ошибки C2993:

```
// C2993.cpp
// compile with: /c
// C2993 expected
struct MyStruct {
   int a;char b;
};

template <class T, struct MyStruct S>   // C2993

// try the following line instead
// template <class T, struct MyStruct * S>
class CMyClass {};
```

Эта ошибка может также возникать в результате изменений работы компилятора в Visual Studio .NET 2003: с плавающей точкой, не являющийся типом параметры больше не допускается. Стандарт C++ не допускает параметров шаблона, не являющегося типом чисел с плавающей запятой.

Если функции-шаблона, используйте аргумент функции для передачи в параметр с плавающей точки не являющийся типом параметра (этот код будет допустимым в версии Visual C++ в Visual Studio .NET 2003 и Visual Studio .NET). Если это класс шаблона, нет обходных путей, легко.

```
// C2993b.cpp
// compile with: /c
template<class T, float f> void func(T) {}   // C2993

// OK
template<class T>   void func2(T, float) {}
```