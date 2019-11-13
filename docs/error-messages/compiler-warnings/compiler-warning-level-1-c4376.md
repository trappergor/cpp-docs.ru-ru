---
title: Предупреждение компилятора (уровень 1) C4376
ms.date: 11/04/2016
f1_keywords:
- C4376
helpviewer_keywords:
- C4376
ms.assetid: 5f202c74-9489-48fe-b36f-19cd882b1589
ms.openlocfilehash: 73143e38b66471a41cc61f818f7618b9ddafcaa1
ms.sourcegitcommit: e5192a25c084eda9eabfa37626f3274507e026b3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/12/2019
ms.locfileid: "73966472"
---
# <a name="compiler-warning-level-1-c4376"></a>Предупреждение компилятора (уровень 1) C4376

спецификатор доступа "old_specifier:" больше не поддерживается: вместо этого используйте "new_specifier:"

Дополнительные сведения об указании доступа к типам и членам в метаданных см. в разделе [видимость типов](../../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Type_visibility) и [видимость элементов](../../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Member_visibility) в статье [как определить и использовать классы и структурыC++(/CLI)](../../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md).

## <a name="example"></a>Пример

Следующий пример приводит к возникновению ошибки C4376.

```cpp
// C4376.cpp
// compile with: /clr /W1 /c
public ref class G {
public public:   // C4376
   void m2();
};

public ref class H {
public:   // OK
   void m2();
};
```