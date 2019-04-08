---
title: Предупреждение компилятора (уровень 3) C4580
ms.date: 11/04/2016
f1_keywords:
- C4580
helpviewer_keywords:
- C4580
ms.assetid: fef6e8e0-0d6a-44fa-b22a-2fe7ba2ef379
ms.openlocfilehash: bd2ecff5adc6538f75c61772b785acbfc89092ae
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/05/2019
ms.locfileid: "58781774"
---
# <a name="compiler-warning-level-3-c4580"></a>Предупреждение компилятора (уровень 3) C4580

использовать [attribute] не рекомендуется; вместо этого в качестве базового класса укажите System::Attribute или Platform::Metadata

[[атрибут](../../windows/attributes/attribute.md)] больше не является предпочтительным синтаксисом для создания пользовательских атрибутов. Дополнительные сведения см. в разделе [User-Defined Attributes](../../extensions/user-defined-attributes-cpp-component-extensions.md). Для кода CLR атрибуты должны быть производными от `System::Attribute`. Для кода среды выполнения Windows атрибуты должны быть производными от `Platform::Metadata`.

## <a name="example"></a>Пример

В следующем примере показано возникновение ошибки C3454 и приводятся сведения по ее устранению.

```cpp
// C4580.cpp
// compile with: /W3 /c /clr
[attribute]   // C4580
public ref class Attr {
public:
   int m_t;
};

public ref class Attr2 : System::Attribute {
public:
   int m_t;
};
```