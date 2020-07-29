---
title: Правила и ограничения для функций с атрибутом naked
ms.date: 11/04/2016
helpviewer_keywords:
- naked functions [C++]
ms.assetid: ff203858-2dd3-4a76-8a57-d0d06817adef
ms.openlocfilehash: 3dd089e13323e1811cf9d7c7717612313f2cef7d
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87225856"
---
# <a name="rules-and-limitations-for-naked-functions"></a>Правила и ограничения для функций с атрибутом naked

**Блок, относящийся только к системам Microsoft**

Для функций с атрибутом naked действуют следующие правила и ограничения:

- **`return`** Инструкция не разрешена.

- Конструкции структурированной обработки исключений и обработки исключений C++ не допускаются, потому что они должны выполнять очистку в кадре стека.

- По этой же причине запрещена любая форма `setjmp`.

- Использование функции `_alloca` запрещено.

- Чтобы перед последовательностью пролога гарантировано не было никакого кода инициализации локальных переменных, инициализируемые локальные переменные в области функции не допускаются. В частности, в области функции не допускается объявление объектов C++. Однако допускаются инициализируемые данные во вложенной области.

- Оптимизация указателя кадра (параметр компилятора /Oy) не рекомендуется, но для функций с атрибутом naked она автоматически подавляется.

- Не допускается объявление объектов класса C++ в лексической области функции. Однако можно объявлять объекты во вложенном блоке.

- **`naked`** При компиляции с [параметром/CLR](../build/reference/clr-common-language-runtime-compilation.md)ключевое слово игнорируется.

- Для функций [__fastcall](../cpp/fastcall.md) с атрибутом naked при наличии ссылки в коде C/C++ на один из аргументов регистра код пролога должен хранить значения этой регистрации в стеке для этой переменной. Пример:

```cpp
// nkdfastcl.cpp
// compile with: /c
// processor: x86
__declspec(naked) int __fastcall  power(int i, int j) {
   // calculates i^j, assumes that j >= 0

   // prolog
   __asm {
      push ebp
      mov ebp, esp
      sub esp, __LOCAL_SIZE
     // store ECX and EDX into stack locations allocated for i and j
     mov i, ecx
     mov j, edx
   }

   {
      int k = 1;   // return value
      while (j-- > 0)
         k *= i;
      __asm {
         mov eax, k
      };
   }

   // epilog
   __asm {
      mov esp, ebp
      pop ebp
      ret
   }
}
```

**Завершение блока, относящегося только к системам Майкрософт**

## <a name="see-also"></a>См. также

[Вызовы функций с атрибутом naked](../cpp/naked-function-calls.md)
