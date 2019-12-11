---
title: Предупреждение средств компоновщика LNK4248
ms.date: 11/04/2016
f1_keywords:
- LNK4248
helpviewer_keywords:
- LNK4248
ms.assetid: e40523ff-e3cb-4ba6-ab79-23f0f339f6cf
ms.openlocfilehash: 4ba05ef067c539dc9c0aca6dc2a395748fd217a2
ms.sourcegitcommit: 573b36b52b0de7be5cae309d45b68ac7ecf9a6d8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2019
ms.locfileid: "74988097"
---
# <a name="linker-tools-warning-lnk4248"></a>Предупреждение средств компоновщика LNK4248

Неразрешенная лексема typeref (токен) для "тип"; образ не может быть запущен

Тип не имеет определения в метаданных MSIL.

LNK4248 может возникать, когда для типа в модуле MSIL (скомпилированном с помощью **/CLR**) имеется только прямая декларация, где на тип имеется ссылка в модуле MSIL и где модуль MSIL связан с собственным модулем, имеющим определение для типа.

В этом случае компоновщик предоставит определение собственного типа в метаданных MSIL, и это может обеспечить правильное поведение.

Однако если объявление прямого типа является типом CLR, определение собственного типа компоновщика может быть неправильным

Дополнительные сведения см. в разделе [/clr (компиляция CLR)](../../build/reference/clr-common-language-runtime-compilation.md).

### <a name="to-correct-this-error"></a>Исправление ошибки

1. Укажите определение типа в модуле MSIL.

## <a name="example"></a>Пример

Следующий пример приводит к возникновению ошибки LNK4248. Определите структуру A для разрешения.

```cpp
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

В следующем примере пересылается определение типа.

```cpp
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

```cpp
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
