---
title: Предупреждение компилятора (уровень 4) C4564
ms.date: 11/04/2016
f1_keywords:
- C4564
helpviewer_keywords:
- C4564
ms.assetid: 555b301b-313e-4262-9f81-eb878674be60
ms.openlocfilehash: 042eab1c125f2b98fd36257dfd8971262015ab92
ms.sourcegitcommit: 573b36b52b0de7be5cae309d45b68ac7ecf9a6d8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2019
ms.locfileid: "74990674"
---
# <a name="compiler-warning-level-4-c4564"></a>Предупреждение компилятора (уровень 4) C4564

метод "метод" класса "класс" определяет неподдерживаемый параметр по умолчанию "параметр"

Компилятор обнаружил метод с одним или несколькими параметрами со значениями по умолчанию. Значения по умолчанию для параметров будут игнорироваться при вызове метода. явно укажите значения для этих параметров. Если не указать явно значения для этих параметров, C++ компилятор выдаст ошибку.

При наличии следующей DLL-библиотеки, созданной с помощью Visual Basic, которая допускает параметры по умолчанию для аргументов метода:

```vb
' C4564.vb
' compile with: vbc /t:library C4564.vb
Public class TestClass
   Public Sub MyMethod (a as Integer, _
                        Optional c as Integer=1)
   End Sub
End class
```

И следующий C++ пример, в котором используется DLL-файл, созданный с помощью Visual Basic,

```cpp
// C4564.cpp
// compile with: /clr /W4 /WX
#using <C4564.dll>

int main() {
   TestClass ^ myx = gcnew TestClass();   // C4564
   myx->MyMethod(9);
   // try the following line instead, to avoid an error
   // myx->MyMethod(9, 1);
}
```
