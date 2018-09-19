---
title: Предупреждение (уровень 2) C4156 компилятора | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4156
dev_langs:
- C++
helpviewer_keywords:
- C4156
ms.assetid: 9adf3acb-c0fe-42a8-a4db-5822b1493f77
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: eddce0944152fe95aa4ef2fd98ec30a793a90978
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46084501"
---
# <a name="compiler-warning-level-2-c4156"></a>Компилятор предупреждение (уровень 2) C4156

Удаление выражения массива без использования формы оператора «delete»; подставлена форма

Не являющиеся массивами виде **удалить** не удается удалить массив. Компилятор преобразует **удалить** форму для массивов.

Это предупреждение возникает только в расширениях Майкрософт (/Ze).

## <a name="example"></a>Пример

```
// C4156.cpp
// compile with: /W2
int main()
{
   int (*array)[ 10 ] = new int[ 5 ][ 10 ];
   delete array; // C4156, changed by compiler to "delete [] array;"
}
```