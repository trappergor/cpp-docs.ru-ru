---
title: Ошибка компилятора C3293 | Документы Microsoft
ms.custom: ''
ms.date: 07/21/2017
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3293
dev_langs:
- C++
helpviewer_keywords:
- C3293
ms.assetid: b772cf98-52e0-4e24-be23-1f5d87d999ac
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b195a91825b0f20445b29e330f67810329584db7
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33257732"
---
# <a name="compiler-error-c3293"></a>Ошибка компилятора C3293
"метод_доступа": используйте default для доступа к свойству по умолчанию (индексатору) для класса "тип"  
  
 Неправильный доступ к индексируемому свойству.  В разделе [как: используйте свойства в C + +/ CLI](../../dotnet/how-to-use-properties-in-cpp-cli.md) для получения дополнительной информации.  

 **Visual Studio 2017 и более поздние версии**: В Visual Studio 2015 и более ранних версий, в некоторых случаях компилятор misidentified свойство по умолчанию как индексатор по умолчанию. Эту проблему удалось решить с использованием значения по умолчанию идентификатора для доступа к свойству. Возможное решение само по себе стало создавать проблемы после того, как значение умолчанию было представлено как ключевое слово в C++ 11. Поэтому в Visual Studio 2017 были исправлены ошибки, требующие обходного решения. Теперь компилятор выдает ошибку, когда значение по умолчанию используется для доступа к свойству по умолчанию для класса.
  
## <a name="example"></a>Пример  
 В следующем примере возникает ошибка C3293 в Visual Studio 2015 и более ранних версий.  
  
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