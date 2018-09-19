---
title: Ошибка компилятора C2383 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2383
dev_langs:
- C++
helpviewer_keywords:
- C2383
ms.assetid: 6696221d-879c-477a-a0f3-a6edc15fd3d7
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 9c529c22636f112291fa53b852899cad78dac589
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46113231"
---
# <a name="compiler-error-c2383"></a>Ошибка компилятора C2383

"*символ*": аргументы по умолчанию не разрешены для этого символа

Компилятор C++ не поддерживает аргументы по умолчанию в указателях на функции.

Этот код был принят компилятором Visual C++ в версиях до Visual Studio 2005, но теперь выдает ошибку. Для кода, который работает во всех версиях Visual C++ не назначайте значение по умолчанию аргумент указателя на функцию.

## <a name="example"></a>Пример

Следующий пример приводит к возникновению ошибки C2383 и показано возможное решение:

```cpp
// C2383.cpp
// compile with: /c
void (*pf)(int = 0);   // C2383
void (*pf)(int);   // OK
```