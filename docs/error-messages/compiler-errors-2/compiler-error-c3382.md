---
title: Ошибка компилятора C3382
ms.date: 11/04/2016
f1_keywords:
- C3382
helpviewer_keywords:
- C3382
ms.assetid: a7603abd-ac4e-4ae6-a02b-3bdc6d1908a6
ms.openlocfilehash: c262ea963ae739fbb76211aae2622e98d5a9b6f7
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62328787"
---
# <a name="compiler-error-c3382"></a>Ошибка компилятора C3382

sizeof при использовании параметра /clr:safe не поддерживается

При выполнении компиляции с параметром **/clr:safe** выходной файл является проверяемым строго типизированным файлом, и параметр sizeof не поддерживается, так как он возвращает значение типа size_t, размер которого зависит от операционной системы.

Дополнительные сведения см. в следующих разделах:

- [Оператор sizeof](../../cpp/sizeof-operator.md)

- [/clr (компиляция среды выполнения)](../../build/reference/clr-common-language-runtime-compilation.md)

- [Общие вопросы использования Visual C++ для 64-разрядных систем](../../build/common-visual-cpp-64-bit-migration-issues.md)

## <a name="example"></a>Пример

Следующий пример приводит к возникновению ошибки C3382:

```
// C3382.cpp
// compile with: /clr:safe
int main() {
   sizeof( char );   // C3382
}
```