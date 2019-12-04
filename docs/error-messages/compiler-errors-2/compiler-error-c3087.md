---
title: Ошибка компилятора C3087
ms.date: 11/04/2016
f1_keywords:
- C3087
helpviewer_keywords:
- C3087
ms.assetid: 4f5bdd52-a853-4f02-b160-6868e9190b9d
ms.openlocfilehash: 6b9ae71ebfbcfcd5936a2fc3ca666aa51e59bfb5
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/03/2019
ms.locfileid: "74751421"
---
# <a name="compiler-error-c3087"></a>Ошибка компилятора C3087

"именованный_аргумент": вызов атрибута "атрибут" уже инициализирует данный член

Именованный аргумент был указан в том же блоке атрибута, что и неименованный аргумент для того же значения. Укажите только именованный или неименованный аргумент.

## <a name="example"></a>Пример

В следующем примере возникает ошибка C3087:

```cpp
// C3087.cpp
// compile with: /c
[idl_quote("quote1", text="quote2")];   // C3087
[idl_quote(text="quote3")];   // OK
[idl_quote("quote4")];   // OK
```
