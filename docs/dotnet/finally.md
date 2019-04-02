---
title: finally
ms.date: 11/04/2016
helpviewer_keywords:
- finally keyword [C++]
ms.assetid: b55f3c8e-1af0-43e8-bcfb-99c3685d2578
ms.openlocfilehash: f7db4320cf901412e3a9e3de682d0cfbcc9f23bc
ms.sourcegitcommit: 5cecccba0a96c1b4ccea1f7a1cfd91f259cc5bde
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/01/2019
ms.locfileid: "58771517"
---
# <a name="finally"></a>finally

В дополнение к `try` и `catch` предложений, поддержка обработки исключений CLR `finally` предложение. Семантика идентична `__finally` блока в структурированной обработки исключений (SEH). Объект `__finally` можно выполнить блок `try` или `catch` блока.

## <a name="remarks"></a>Примечания

Цель `finally` блок должен освободить все ресурсы, после возникновения исключения. Обратите внимание, что `finally` блоке выполняется всегда, даже если исключение не создано. `catch` Блок выполняется только в том случае, если управляемое исключение возникает в пределах связанного `try` блока.

`finally` — контекстно-зависимые ключевое слово; см. в разделе [контекстные ключевые слова](../extensions/context-sensitive-keywords-cpp-component-extensions.md) Дополнительные сведения.

## <a name="example"></a>Пример

В следующем примере показано простое `finally` блок:

```
// keyword__finally.cpp
// compile with: /clr
using namespace System;

ref class MyException: public System::Exception{};

void ThrowMyException() {
   throw gcnew MyException;
}

int main() {
   try {
      ThrowMyException();
   }
   catch ( MyException^ e ) {
      Console::WriteLine(  "in catch" );
      Console::WriteLine( e->GetType() );
   }
   finally {
      Console::WriteLine(  "in finally" );
   }
}
```

```Output
in catch
MyException
in finally
```

## <a name="see-also"></a>См. также

[Обработка исключений](../extensions/exception-handling-cpp-component-extensions.md)
