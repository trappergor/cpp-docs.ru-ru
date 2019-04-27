---
title: Предупреждение компилятора (уровень 4) C4564
ms.date: 11/04/2016
f1_keywords:
- C4564
helpviewer_keywords:
- C4564
ms.assetid: 555b301b-313e-4262-9f81-eb878674be60
ms.openlocfilehash: 1948bdec5367fa7943f5a0de4338fd4ecd6c6581
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62220511"
---
# <a name="compiler-warning-level-4-c4564"></a>Предупреждение компилятора (уровень 4) C4564

метод «метод» класс «класс» определяет неподдерживаемый параметр по умолчанию «параметр»

Компилятор обнаружил метод с одним или несколькими параметрами со значениями по умолчанию. Значения по умолчанию для параметров будут игнорироваться при вызове метода; явное указание значений для этих параметров. Если вы не укажете явным образом значения для этих параметров, компилятор C++ выдаст ошибку.

Учитывая следующие DLL-файлы, созданные с помощью Visual Basic, который допускает параметры по умолчанию аргументы метода:

```
' C4564.vb
' compile with: vbc /t:library C4564.vb
Public class TestClass
   Public Sub MyMethod (a as Integer, _
                        Optional c as Integer=1)
   End Sub
End class
```

И в следующем примере C++, использующий библиотеку DLL, созданные с помощью Visual Basic

```
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