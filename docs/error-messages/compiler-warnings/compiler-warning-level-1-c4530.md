---
title: Предупреждение компилятора (уровень 1) C4530
ms.date: 11/04/2016
f1_keywords:
- C4530
helpviewer_keywords:
- C4530
ms.assetid: a04dcdb2-84db-459d-9e5e-4e743887465f
ms.openlocfilehash: 3139d321bca64b9938badebdabccd3ca1eb96d11
ms.sourcegitcommit: e5192a25c084eda9eabfa37626f3274507e026b3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/12/2019
ms.locfileid: "73966265"
---
# <a name="compiler-warning-level-1-c4530"></a>Предупреждение компилятора (уровень 1) C4530

C++используется обработчик исключений, но семантика очистки не включена. Укажите/EHsc

C++была использована обработка исключений, но не выбрано [/EHsc](../../build/reference/eh-exception-handling-model.md) .

Если параметр/EHsc не включен, объект с автоматическим хранилищем в кадре между функцией, выполняющей вызываемую функцию, и функцией, которая перехватывать исключение, не будет уничтожена. Однако объект с автоматическим хранилищем, созданным в блоке **try** или **catch** , будет уничтожен.

Следующий пример приводит к возникновению ошибки C4530:

```cpp
// C4530.cpp
// compile with: /W1
int main() {
   try{} catch(int*) {}   // C4530
}
```

Скомпилируйте пример с параметром/EHsc, чтобы устранить предупреждение.