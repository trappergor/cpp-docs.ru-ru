---
title: Ошибка компилятора C3388
ms.date: 11/04/2016
f1_keywords:
- C3388
helpviewer_keywords:
- C3388
ms.assetid: 34336545-ed13-4d81-ab5f-f869799fe4c2
ms.openlocfilehash: bb2a847c24b2a0b7829008793f311459e76587f4
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/03/2019
ms.locfileid: "74758350"
---
# <a name="compiler-error-c3388"></a>Ошибка компилятора C3388

"тип": не допускается в качестве ограничения; предполагается, что "класс ref" продолжит синтаксический разбор

Ограничение для универсального типа указано неправильно. Дополнительные сведения см. [в разделе ограниченияC++для параметров универсального типа (/CLI)](../../extensions/constraints-on-generic-type-parameters-cpp-cli.md) .

## <a name="example"></a>Пример

Следующий пример приводит к возникновению ошибки C3388:

```cpp
// C3388.cpp
// compile with: /clr /c
interface class AA {};

generic <class T>
where T : interface class   // C3388
ref class C {};

// OK
generic <class T>
where T : AA
ref class D {};
```
