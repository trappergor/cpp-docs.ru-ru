---
title: Предупреждение средств компоновщика LNK4248 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK4248
dev_langs:
- C++
helpviewer_keywords:
- LNK4248
ms.assetid: e40523ff-e3cb-4ba6-ab79-23f0f339f6cf
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 8ff2c3edd942eb0d38d16a6986044f90358c4e9f
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46062167"
---
# <a name="linker-tools-warning-lnk4248"></a>Предупреждение средств компоновщика LNK4248

неразрешенная лексема typeref (маркер) для «тип»; образ нельзя запустить

Тип не имеет определения в метаданных MSIL.

LNK4248 может произойти, если только опережающее объявление типа в модуле MSIL (скомпилированные с использованием **/CLR**), если эти типы есть ссылки в модуль MSIL и компонуется с собственным модулем, который содержит определение для модуля MSIL тип.

В этом случае компоновщик предоставит определение собственного типа в метаданных MSIL, а это может обеспечить для правильного поведения.

Тем не менее если объявлений перенаправления типа является типом CLR, то определение собственного типа компоновщика может не иметь правильный

Дополнительные сведения см. в разделе [/clr (компиляция CLR)](../../build/reference/clr-common-language-runtime-compilation.md).

### <a name="to-correct-this-error"></a>Исправление ошибки

1. Укажите определение типа в модуль MSIL.

## <a name="example"></a>Пример

Следующий пример приводит к возникновению ошибки LNK4248. Определение типа структуры для решения.

```
// LNK4248.cpp
// compile with: /clr /W1
// LNK4248 expected
struct A;
void Test(A*){}

int main() {
   Test(0);
}
```

## <a name="example"></a>Пример

В следующем примере приведено определение переадресации типа.

```
// LNK4248_2.cpp
// compile with: /clr /c
class A;   // provide a definition for A here to resolve
A * newA();
int valueA(A * a);

int main() {
   A * a = newA();
   return valueA(a);
}
```

## <a name="example"></a>Пример

Следующий пример приводит к возникновению ошибки LNK4248.

```
// LNK4248_3.cpp
// compile with: /c
// post-build command: link LNK4248_2.obj LNK4248_3.obj
class A {
public:
   int b;
};

A* newA() {
   return new A;
}

int valueA(A * a) {
   return (int)a;
}
```