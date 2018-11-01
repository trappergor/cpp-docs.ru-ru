---
title: noreturn
ms.date: 11/04/2016
f1_keywords:
- noreturn_cpp
helpviewer_keywords:
- __declspec keyword [C++], noreturn
- noreturn __declspec keyword
ms.assetid: 9c6517e5-22d7-4051-9974-3d2200ae4d1d
ms.openlocfilehash: 1d78e8f5116eabf9073205b938156197bf1001a9
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50611865"
---
# <a name="noreturn"></a>noreturn

## <a name="microsoft-specific"></a>Блок, относящийся только к системам Microsoft

Это **__declspec** атрибут сообщает компилятору, что функция не возвращает. Как следствие, компилятор знает, что код, следующий вызов **__declspec(noreturn)** функция недоступен.

Если компилятор обнаруживает функцию с путем элемента управления, которая не возвращает значение, он создает предупреждение (C4715) или сообщение об ошибке (C2202). Если путь управления становится недоступным из-за функции, которая никогда не возвращает, можно использовать **__declspec(noreturn)** во избежание этого предупреждения или ошибки.

> [!NOTE]
>  Добавление **__declspec(noreturn)** на функцию, которая возвращает может привести к неопределенному поведению.

## <a name="example"></a>Пример

В следующем примере **else** предложение не содержит оператор return.  Объявление `fatal` как **__declspec(noreturn)** позволяет избежать ошибки или предупреждения.

```cpp
// noreturn2.cpp
__declspec(noreturn) extern void fatal () {}

int main() {
   if(1)
     return 1;
   else if(0)
     return 0;
   else
     fatal();
}
```

## <a name="see-also"></a>См. также

[__declspec](../cpp/declspec.md)<br/>
[Ключевые слова](../cpp/keywords-cpp.md)