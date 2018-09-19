---
title: Ошибка компилятора C3012 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3012
dev_langs:
- C++
helpviewer_keywords:
- C3012
ms.assetid: cc7040b1-b3fb-4da6-a474-877914d30332
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 99bdac5ffb75978479ae7ef420a48b3d1b2f8e64
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46063675"
---
# <a name="compiler-error-c3012"></a>Ошибка компилятора C3012

> "*внутренние*": встроенная функция, не допускается непосредственно внутри параллельной области

Объект [Внутренняя функция компилятора](../../intrinsics/compiler-intrinsics.md) функция недопустима в `omp parallel` регион. Чтобы устранить эту проблему, встроенные функции можно вывести из области или замените невстроенный эквиваленты.

## <a name="example"></a>Пример

Следующий пример приводит к возникновению ошибки C3012 и показан один из способов ее устранения:

```cpp
// C3012.cpp
// compile with: /openmp
#ifdef __cplusplus
extern "C" {
#endif
void* _ReturnAddress();
#ifdef __cplusplus
}
#endif

int main()
{
   #pragma omp parallel
   {
      _ReturnAddress();   // C3012
   }
   _ReturnAddress();      // OK
}
```