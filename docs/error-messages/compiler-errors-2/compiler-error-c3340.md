---
title: Ошибка компилятора C3340 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3340
dev_langs:
- C++
helpviewer_keywords:
- C3340
ms.assetid: 23b12298-b92a-4717-8380-f165c998cb8a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d7630e8fb647e52a1b6e355d413c8fb666277e82
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46066094"
---
# <a name="compiler-error-c3340"></a>Ошибка компилятора C3340

"интерфейс": интерфейс не может одновременно быть "restricted" и "default" в компонентном классе "класс"

Атрибут [restricted](../../windows/restricted.md) и атрибут [default](../../windows/default-cpp.md) являются взаимоисключающими.

Следующий пример приводит к возникновению ошибки C3340:

```
// C3340.cpp
#include <windows.h>
[module(name="MyModule")];

[ object, uuid(373a1a4c-469b-11d3-a6b0-00c04f79ae8f) ]
__interface IMyIface
{
   HRESULT f1();
};

[ coclass, uuid(373a1a4d-469b-11d3-a6b0-00c04f79ae8f),
default(IMyIface),
source(IMyIface),restricted(IMyIface) ]
class CmyClass // C3340
{
};

int main()
{
}
```