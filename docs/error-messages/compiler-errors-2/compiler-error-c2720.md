---
title: Ошибка компилятора C2720
ms.date: 11/04/2016
f1_keywords:
- C2720
helpviewer_keywords:
- C2720
ms.assetid: 9ee3aab7-711b-4f5a-b2f1-cb62b130f1ce
ms.openlocfilehash: 24f4329ee631eafc7c2670d9ebf28609c22e7592
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80202142"
---
# <a name="compiler-error-c2720"></a>Ошибка компилятора C2720

> "*идентификатор*": спецификатор класса хранения "*спецификатор*" недопустим для членов

Класс хранения нельзя использовать для членов класса вне объявления. Чтобы устранить эту ошибку, удалите ненужный спецификатор [класса хранения](../../cpp/storage-classes-cpp.md) из определения члена за пределами объявления класса.

## <a name="example"></a>Пример

В следующем примере показано возникновение ошибки C2720 и приводятся сведения по ее устранению.

```cpp
// C2720.cpp
struct S {
   static int i;
};
static S::i;   // C2720 - remove the unneeded 'static' to fix it
```
