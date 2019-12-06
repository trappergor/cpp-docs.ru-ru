---
title: noreturn
ms.date: 11/04/2016
f1_keywords:
- noreturn_cpp
helpviewer_keywords:
- __declspec keyword [C++], noreturn
- noreturn __declspec keyword
ms.assetid: 9c6517e5-22d7-4051-9974-3d2200ae4d1d
ms.openlocfilehash: f9ca61c9d734ccdd6b8d8374ed3a7c4128ee3d5e
ms.sourcegitcommit: a6d63c07ab9ec251c48bc003ab2933cf01263f19
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/05/2019
ms.locfileid: "74857376"
---
# <a name="noreturn"></a>noreturn

**Блок, относящийся только к системам Майкрософт**

Этот атрибут **__declspec** указывает компилятору, что функция не возвращает значение. Как следствие, компилятор знает, что код, следующий за вызовом функции **__declspec (Return)** , недоступен.

Если компилятор обнаруживает функцию с путем элемента управления, которая не возвращает значение, он создает предупреждение (C4715) или сообщение об ошибке (C2202). Если путь к элементу управления недоступен из-за функции, которая никогда не возвращает, можно использовать **__declspec (noreturn)** , чтобы предотвратить это предупреждение или ошибку.

> [!NOTE]
>  Добавление **__declspec (Return)** в функцию, которая должна возвращать значение, может привести к неопределенному поведению.

## <a name="example"></a>Пример

В следующем примере предложение **else** не содержит оператор return.  Объявление `fatal` как **__declspec (noreturn)** позволяет избежать сообщения об ошибке или предупреждения.

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

**Завершение блока, относящегося только к системам Майкрософт**

## <a name="see-also"></a>См. также:

[__declspec](../cpp/declspec.md)<br/>
[Ключевые слова](../cpp/keywords-cpp.md)