---
title: Предупреждение компилятора (уровень 3) C4580
ms.date: 11/04/2016
f1_keywords:
- C4580
helpviewer_keywords:
- C4580
ms.assetid: fef6e8e0-0d6a-44fa-b22a-2fe7ba2ef379
ms.openlocfilehash: 28d8534dad5fc1b234c180b879ad0645f05cfd65
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80198618"
---
# <a name="compiler-warning-level-3-c4580"></a>Предупреждение компилятора (уровень 3) C4580

использовать [attribute] не рекомендуется; вместо этого в качестве базового класса укажите System::Attribute или Platform::Metadata

[[Attribute](../../windows/attributes/attribute.md)] больше не является предпочтительным синтаксисом для создания определяемых пользователем атрибутов. Дополнительные сведения см. в разделе [User-Defined Attributes](../../extensions/user-defined-attributes-cpp-component-extensions.md). Для кода CLR атрибуты должны быть производными от `System::Attribute`. Для кода среды выполнения Windows атрибуты должны быть производными от `Platform::Metadata`.

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
