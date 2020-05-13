---
title: Ошибка компилятора C2383
ms.date: 11/04/2016
f1_keywords:
- C2383
helpviewer_keywords:
- C2383
ms.assetid: 6696221d-879c-477a-a0f3-a6edc15fd3d7
ms.openlocfilehash: 2aa922ebeadb374a7eac73a0f452376472b00984
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80206032"
---
# <a name="compiler-error-c2383"></a>Ошибка компилятора C2383

"*символ*": аргументы по умолчанию не разрешены для этого символа

C++ Компилятор не разрешает использовать аргументы по умолчанию для указателей на функции.

Этот код был принят компилятором Майкрософт C++ в версиях до Visual Studio 2005, но теперь выдает ошибку. Для кода, который работает во всех версиях Visual C++, не присваивайте аргументу указателя на функцию значение по умолчанию.

## <a name="example"></a>Пример

В следующем примере создается C2383 и демонстрируется возможное решение:

```cpp
// C2383.cpp
// compile with: /c
void (*pf)(int = 0);   // C2383
void (*pf)(int);   // OK
```
