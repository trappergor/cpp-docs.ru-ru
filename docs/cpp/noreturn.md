---
title: noreturn
ms.date: 11/04/2016
f1_keywords:
- noreturn_cpp
helpviewer_keywords:
- __declspec keyword [C++], noreturn
- noreturn __declspec keyword
ms.assetid: 9c6517e5-22d7-4051-9974-3d2200ae4d1d
ms.openlocfilehash: f37ce13e27f9b141eab928b88102813a5b6d65f8
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80177889"
---
# <a name="noreturn"></a>noreturn

**Блок, относящийся только к системам Microsoft**

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

## <a name="see-also"></a>См. также раздел

[__declspec](../cpp/declspec.md)<br/>
[Ключевые слова](../cpp/keywords-cpp.md)
