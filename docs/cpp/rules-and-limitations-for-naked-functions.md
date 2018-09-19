---
title: Правила и ограничения при использовании функций Naked | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- naked functions [C++]
ms.assetid: ff203858-2dd3-4a76-8a57-d0d06817adef
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 944945c8a5660ef65621e022130a63a02b46761a
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46020476"
---
# <a name="rules-and-limitations-for-naked-functions"></a>Правила и ограничения для функций с атрибутом naked

## <a name="microsoft-specific"></a>Блок, относящийся только к системам Microsoft

Для функций с атрибутом naked действуют следующие правила и ограничения:

- **Возвращают** инструкции не допускается.

- Конструкции структурированной обработки исключений и обработки исключений C++ не допускаются, потому что они должны выполнять очистку в кадре стека.

- По этой же причине запрещена любая форма `setjmp`.

- Использование функции `_alloca` запрещено.

- Чтобы перед последовательностью пролога гарантировано не было никакого кода инициализации локальных переменных, инициализируемые локальные переменные в области функции не допускаются. В частности, в области функции не допускается объявление объектов C++. Однако допускаются инициализируемые данные во вложенной области.

- Оптимизация указателя кадра (параметр компилятора /Oy) не рекомендуется, но для функций с атрибутом naked она автоматически подавляется.

- Не допускается объявление объектов класса C++ в лексической области функции. Однако можно объявлять объекты во вложенном блоке.

- **С атрибутом naked** ключевого слова пропускается при компиляции с параметром [/CLR](../build/reference/clr-common-language-runtime-compilation.md).

- Для [__fastcall](../cpp/fastcall.md) функции с атрибутом naked, каждый раз, когда имеется ссылка в коде C/C++ на один из регистровых аргументов, код пролога должен сохранять значения этого регистра в расположении стека для этой переменной. Пример:

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