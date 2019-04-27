---
title: Неустранимая ошибка C1197
ms.date: 11/04/2016
f1_keywords:
- C1197
helpviewer_keywords:
- C1197
ms.assetid: 22b801b7-e792-41f6-a461-973c03c69f25
ms.openlocfilehash: e1c00a001c807b0cc6a5946b61ca4e9d5dc0167a
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62229126"
---
# <a name="fatal-error-c1197"></a>Неустранимая ошибка C1197

не может ссылаться на «mscorlib.dll_1», так как программой был уже адресован «mscorlib.dll_2»

Компилятор соответствует версии среды CLR.  Однако была предпринята попытка сослаться на версию файле среды CLR из предыдущей версии.

Чтобы устранить эту ошибку, только ссылки на файлы из версии общеязыковой среды выполнения, которая поставлялась с версией при компиляции с помощью Visual C++.

## <a name="example"></a>Пример

Следующий пример приводит к возникновению ошибки C1197:

```
// C1197.cpp
// compile with: /clr /c
// processor: x86
#using "C:\Windows\Microsoft.NET\Framework\v1.1.4322\mscorlib.dll"   // C1197
// try the following line instead
// #using "mscorlib.dll"
```