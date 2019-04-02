---
title: __super
ms.date: 11/04/2016
f1_keywords:
- __super_cpp
helpviewer_keywords:
- __super keyword [C++]
ms.assetid: f0957c31-9256-405b-b402-cad182404b5f
ms.openlocfilehash: a69d177bb83ce404a18d50c8f966be5d81f5fa72
ms.sourcegitcommit: 5cecccba0a96c1b4ccea1f7a1cfd91f259cc5bde
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/01/2019
ms.locfileid: "58779655"
---
# <a name="super"></a>__super

**Блок, относящийся только к системам Microsoft**

Позволяет явно указать, что для переопределяемой функции вызывается реализация из базового класса.

## <a name="syntax"></a>Синтаксис

```
__super::member_function();
```

## <a name="remarks"></a>Примечания

На этапе разрешения перегрузки учитываются все доступные методы базового класса, и вызывается функция, которая обеспечивает наилучшее совпадение.

**__super** может использоваться только в теле функции-члена.

**__super** нельзя использовать с помощью объявления. См. в разделе [объявление using](../cpp/using-declaration.md) Дополнительные сведения.

С появлением [атрибуты](../windows/attributes/attributes-alphabetical-reference.md) , внедряющих код, код может содержать один или несколько базовых классов, имена которых вы можете не знать, но которые содержат методы, которые должны вызываться.

## <a name="example"></a>Пример

```cpp
// deriv_super.cpp
// compile with: /c
struct B1 {
   void mf(int) {}
};

struct B2 {
   void mf(short) {}

   void mf(char) {}
};

struct D : B1, B2 {
   void mf(short) {
      __super::mf(1);   // Calls B1::mf(int)
      __super::mf('s');   // Calls B2::mf(char)
   }
};
```

**Завершение блока, относящегося только к системам Майкрософт**

## <a name="see-also"></a>См. также

[Ключевые слова](../cpp/keywords-cpp.md)