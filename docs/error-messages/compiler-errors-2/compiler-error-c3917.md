---
title: Ошибка компилятора C3917
ms.date: 11/04/2016
f1_keywords:
- C3917
helpviewer_keywords:
- C3917
ms.assetid: a24cd0c9-262f-46e5-9488-1c01f945933d
ms.openlocfilehash: 3d527f8447306ff74606a0aa733014d45f985dc0
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80165474"
---
# <a name="compiler-error-c3917"></a>Ошибка компилятора C3917

"*свойство*": устаревший стиль объявления конструкции

Определение свойства или события использовало синтаксис из версии до Visual Studio 2005.

Дополнительные сведения см. в разделе [property](../../extensions/property-cpp-component-extensions.md).

## <a name="example"></a>Пример

```cpp
// C3917.cpp
// compile with: /clr /c
public ref class  C {
private:
   int m_length;
public:
   C() {
      m_length = 0;
   }

   property int get_Length();   // C3917

   // The correct property definition:
   property int Length {
      int get() {
         return m_length;
      }

      void set( int i ) {
         m_length = i;
      }
   }
};
```
