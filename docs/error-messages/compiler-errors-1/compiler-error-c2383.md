---
title: Ошибка компилятора C2383
ms.date: 11/04/2016
f1_keywords:
- C2383
helpviewer_keywords:
- C2383
ms.assetid: 6696221d-879c-477a-a0f3-a6edc15fd3d7
ms.openlocfilehash: e9c1774fe7cd4a6883aa79f384cc64521a57ed17
ms.sourcegitcommit: 7d64c5f226f925642a25e07498567df8bebb00d4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2019
ms.locfileid: "65448004"
---
# <a name="compiler-error-c2383"></a>Ошибка компилятора C2383

"*символ*": аргументы по умолчанию не разрешены для этого символа

Компилятор C++ не поддерживает аргументы по умолчанию в указателях на функции.

Этот код был принят для Microsoft C++ компилятора в версиях до Visual Studio 2005, но теперь выдает ошибку. Для кода, который работает во всех версиях Visual C++ не назначайте значение по умолчанию аргумент указателя на функцию.

## <a name="example"></a>Пример

Следующий пример приводит к возникновению ошибки C2383 и показано возможное решение:

```cpp
// C2383.cpp
// compile with: /c
void (*pf)(int = 0);   // C2383
void (*pf)(int);   // OK
```