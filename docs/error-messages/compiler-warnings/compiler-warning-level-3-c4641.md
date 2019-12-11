---
title: Предупреждение компилятора (уровень 3) C4641
ms.date: 11/04/2016
f1_keywords:
- C4641
helpviewer_keywords:
- C4641
ms.assetid: 28fe5c3e-6039-42da-9100-1312b5b15aea
ms.openlocfilehash: 1e3eab6e96e829e3c3fd9304e757ba653e8f19b4
ms.sourcegitcommit: 573b36b52b0de7be5cae309d45b68ac7ecf9a6d8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2019
ms.locfileid: "74991816"
---
# <a name="compiler-warning-level-3-c4641"></a>Предупреждение компилятора (уровень 3) C4641

в документирующем комментарии XML присутствует неоднозначная перекрестная ссылка

Компилятору не удалось однозначно разрешить ссылку. Чтобы устранить это предупреждение, укажите сведения о параметрах, необходимые для однозначного создания ссылки.

Дополнительные сведения см. в разделе [XML Documentation](../../build/reference/xml-documentation-visual-cpp.md).

## <a name="example"></a>Пример

Следующий пример приводит к возникновению ошибки C4641.

```cpp
// C4641.cpp
// compile with: /W3 /doc /clr /c

/// <see cref="f" />   // C4641
// try the following line instead
// /// <see cref="f(int)" />
public ref class GR {
public:
   void f( int ) {}
   void f( char ) {}
};
```
