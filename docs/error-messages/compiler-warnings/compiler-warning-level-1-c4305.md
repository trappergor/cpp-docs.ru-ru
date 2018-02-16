---
title: "Предупреждение (уровень 1) C4305 компилятора | Документы Microsoft"
ms.custom: 
ms.date: 1/17/2018
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4305
dev_langs:
- C++
helpviewer_keywords:
- C4305
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 8fe4b2b420c44584fdd5b4d48b4264bbc7a51bee
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/14/2018
---
# <a name="compiler-warning-level-1-c4305"></a>Предупреждение компилятора (уровень 1) C4305

> "*контекста*": усечение из "*тип1*«to»*тип2*"  

## <a name="remarks"></a>Примечания

Это предупреждение выдается в том случае, если значение преобразуется к типу меньшего размера в инициализации или в качестве аргумента конструктора приведет к потере данных.

## <a name="example"></a>Пример

В этом примере отображаются двумя способами, может появиться это предупреждение:

```cpp
// C4305.cpp
// Compile by using: cl /EHsc /W4 C4305.cpp

struct item
{
    item(float) {}
};

int main()
{
    float f = 2.71828;          // C4305 'initializing'
    item i(3.14159);            // C4305 'argument'
    return static_cast<int>(f);
}
```

Чтобы устранить эту проблему, инициализировать с помощью значения правильного типа, или использовать явное приведение к правильному типу. Использовать, например, **float** литерал, например 2.71828f вместо **двойные** (тип по умолчанию литералы с плавающей запятой) для инициализации **float** переменной, или для передачи конструктор, принимающий **float** аргумент.
