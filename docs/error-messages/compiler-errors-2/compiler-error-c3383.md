---
title: Ошибка компилятора C3383
ms.date: 11/04/2016
f1_keywords:
- C3383
helpviewer_keywords:
- C3383
ms.assetid: ceb7f725-f417-4dc3-8496-0f413bb76687
ms.openlocfilehash: 38aea188eeac90cd23d9203a53b4e630be2f115b
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50428019"
---
# <a name="compiler-error-c3383"></a>Ошибка компилятора C3383

operator new при использовании параметра /clr:safe не поддерживается

Строгая типизация в выходном файле, полученном при компиляции с параметром **/clr:safe** , поддается проверке, поэтому указатели не поддерживаются.

Дополнительные сведения см. в следующих разделах:

- [/clr (компиляция среды выполнения)](../../build/reference/clr-common-language-runtime-compilation.md)

- [Общие вопросы использования Visual C++ для 64-разрядных систем](../../build/common-visual-cpp-64-bit-migration-issues.md)

## <a name="example"></a>Пример

Следующий пример приводит к возникновению ошибки C3383:

```
// C3383.cpp
// compile with: /clr:safe
int main() {
   char* pCharArray = new char[256];  // C3383
}
```