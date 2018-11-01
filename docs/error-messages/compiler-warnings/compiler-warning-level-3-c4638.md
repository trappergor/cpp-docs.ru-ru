---
title: Предупреждение компилятора (уровень 3) C4638
ms.date: 08/27/2018
f1_keywords:
- C4638
helpviewer_keywords:
- C4638
ms.assetid: 2c07923a-e103-4e40-bd11-fdfed428a5ec
ms.openlocfilehash: 1bdd7541e16f5c02756678ae78a777094b5fe588
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50651533"
---
# <a name="compiler-warning-level-3-c4638"></a>Предупреждение компилятора (уровень 3) C4638

> Цель комментария XML-документа: ссылка на неизвестный символ "*символ*"

## <a name="remarks"></a>Примечания

Компилятору не удалось разрешить символ (*символ*). Символ должен быть допустимым при компиляции.

## <a name="example"></a>Пример

В следующем примере возникает ошибка C4638.

```cpp
// C4638.cpp
// compile with: /clr /doc /LD /W3
using namespace System;

/// Text for class MyClass.
public ref class MyClass {
public:
   /// <summary> Text </summary>
   /// <see cref="aSymbolThatAppearsNowhereInMyProject"/>
   // Try the following line instead:
   // /// <see cref="System::Console::WriteLine"/>
   void MyMethod() {}
};   // C4638
```