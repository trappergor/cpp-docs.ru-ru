---
title: Ошибка компилятора C3917
ms.date: 11/04/2016
f1_keywords:
- C3917
helpviewer_keywords:
- C3917
ms.assetid: a24cd0c9-262f-46e5-9488-1c01f945933d
ms.openlocfilehash: 9cb6d594124d995d766df280da2584665ab6d7a2
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59776368"
---
# <a name="compiler-error-c3917"></a>Ошибка компилятора C3917

"*свойство*": устаревший стиль объявления конструкция

Определение свойства или события используется синтаксис из исходной версии перед установкой Visual Studio 2005.

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