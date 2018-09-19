---
title: Предупреждение компилятора (уровень 4) C4564 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4564
dev_langs:
- C++
helpviewer_keywords:
- C4564
ms.assetid: 555b301b-313e-4262-9f81-eb878674be60
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ea8d392251c8168490d7841ad590731b5a08e7f5
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46031838"
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