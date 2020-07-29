---
title: Предупреждение компилятора (уровень 2) C4156
ms.date: 11/04/2016
f1_keywords:
- C4156
helpviewer_keywords:
- C4156
ms.assetid: 9adf3acb-c0fe-42a8-a4db-5822b1493f77
ms.openlocfilehash: 279ab5d9de738fb4e2aa6dece4bb16353eca031b
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87206488"
---
# <a name="compiler-warning-level-2-c4156"></a>Предупреждение компилятора (уровень 2) C4156

Удаление выражения массива без использования формы массива "Delete"; Форма массива заменена

Невозможно удалить массив, не являющийся массивом **`delete`** . Компилятор преобразуется **`delete`** в форму массива.

Это предупреждение возникает только в расширениях Майкрософт (/Ze).

## <a name="example"></a>Пример

```cpp
// C4156.cpp
// compile with: /W2
int main()
{
   int (*array)[ 10 ] = new int[ 5 ][ 10 ];
   delete array; // C4156, changed by compiler to "delete [] array;"
}
```
