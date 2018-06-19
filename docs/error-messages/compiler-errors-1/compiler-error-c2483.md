---
title: Ошибка компилятора C2483 | Документы Microsoft
ms.custom: ''
ms.date: 09/15/2017
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2483
dev_langs:
- C++
helpviewer_keywords:
- C2483
ms.assetid: 5762b325-914b-442d-a604-e4617ba04038
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0a10fd33ebeef43904db964fc327fb749029f963
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33197979"
---
# <a name="compiler-error-c2483"></a>Ошибка компилятора C2483

>"*идентификатор*": объект с конструктором или деструктором не может объявляться как «thread»

Это сообщение об ошибке не используется в Visual Studio 2015 и более поздних версиях. В предыдущих версиях переменные объявлены с `thread` атрибут нельзя инициализировать с конструктором или другим выражением, которое необходимо оценить во время выполнения. Статическое выражение, необходимые для инициализации `thread` данных.

## <a name="example"></a>Пример

Следующий пример приводит к возникновению ошибки C2483 Visual Studio 2013 и более ранних версий.

```cpp
// C2483.cpp
// compile with: /c
__declspec(thread) struct A {
   A(){}
   ~A(){}
} aa;   // C2483 error  

__declspec(thread) struct B {} b;   // OK
```

## <a name="see-also"></a>См. также

[thread](../../cpp/thread.md)