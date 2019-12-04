---
title: Неустранимая ошибка C1197
ms.date: 11/04/2016
f1_keywords:
- C1197
helpviewer_keywords:
- C1197
ms.assetid: 22b801b7-e792-41f6-a461-973c03c69f25
ms.openlocfilehash: 7f698262c73f0b311a92a8940107b552430919bb
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/03/2019
ms.locfileid: "74747245"
---
# <a name="fatal-error-c1197"></a>Неустранимая ошибка C1197

невозможно сослаться на mscorlib. dll_1, так как программа уже ссылалась на mscorlib. dll_2

Компилятор соответствует версии среды CLR.  Однако была предпринята попытка сослаться на версию файла среды CLR, созданную из предыдущей версии.

Чтобы устранить эту ошибку, следует обращаться только к файлам из версии среды CLR, поставляемой с версией визуального C++ элемента, с которым выполняется компиляция.

## <a name="example"></a>Пример

Следующий пример приводит к возникновению ошибки C1197:

```cpp
// C1197.cpp
// compile with: /clr /c
// processor: x86
#using "C:\Windows\Microsoft.NET\Framework\v1.1.4322\mscorlib.dll"   // C1197
// try the following line instead
// #using "mscorlib.dll"
```
