---
title: Ошибка компилятора C3293
ms.date: 07/21/2017
f1_keywords:
- C3293
helpviewer_keywords:
- C3293
ms.assetid: b772cf98-52e0-4e24-be23-1f5d87d999ac
ms.openlocfilehash: 84d539722474d5f5dfffe1f6fe121bb7349ba131
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62222591"
---
# <a name="compiler-error-c3293"></a>Ошибка компилятора C3293

"метод_доступа": используйте default для доступа к свойству по умолчанию (индексатору) для класса "тип"

Неправильный доступ к индексируемому свойству.  См. практическое руководство по [ Использование свойств C++выполняет](../../dotnet/how-to-use-properties-in-cpp-cli.md) Дополнительные сведения.

**Visual Studio 2017 и более поздних версий**: В Visual Studio 2015 и более ранних версиях в некоторых случаях компилятор неправильно определял свойство по умолчанию как индексатор по умолчанию. Эту проблему удалось решить с использованием значения по умолчанию идентификатора для доступа к свойству. Возможное решение само по себе стало создавать проблемы после того, как значение умолчанию было представлено как ключевое слово в C++ 11. Поэтому в Visual Studio 2017 были исправлены ошибки, требующие обходного решения. Теперь компилятор выдает ошибку, когда значение по умолчанию используется для доступа к свойству по умолчанию для класса.

## <a name="example"></a>Пример

Следующий пример приводит к возникновению ошибки C3293 в Visual Studio 2015 и более ранних версий.

```
// C3293.cpp
// compile with: /clr /c
using namespace System;
ref class IndexerClass {
public:
   // default indexer
   property int default[int] {
      int get(int index) { return 0; }
      void set(int index, int value) {}
   }
};

int main() {
   IndexerClass ^ ic = gcnew IndexerClass;
   ic->Item[0] = 21;   // C3293 in VS2015 OK in VS2017
   ic->default[0] = 21;   // OK in VS2015 and earlier

   String ^s = "Hello";
   wchar_t wc = s->Chars[0];   // C3293 in VS2015 OK in VS2017
   wchar_t wc2 = s->default[0];   // OK in VS2015 and earlier
   Console::WriteLine(wc2);
}
```