---
title: Ошибка компилятора C3839
ms.date: 11/04/2016
f1_keywords:
- C3839
helpviewer_keywords:
- C3839
ms.assetid: 0957faff-1e9f-439b-876b-85bd8d2c578d
ms.openlocfilehash: b8382213fbe7cc953dafd9610bfb993ba7837947
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50613020"
---
# <a name="compiler-error-c3839"></a>Ошибка компилятора C3839

нельзя изменять выравнивание в управляемом типе или типе WinRT

Выравнивание переменных в управляемых типах или типах среды выполнения Windows управляется средой CLR или среды выполнения Windows и не может быть изменен с [выровнять](../../cpp/align-cpp.md).

Следующий пример приводит к возникновению ошибки C3839:

```
// C3839a.cpp
// compile with: /clr
ref class C
{
public:
   __declspec(align(32)) int m_j; // C3839
};

int main()
{
}
```