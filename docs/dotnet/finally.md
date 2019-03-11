---
title: finally
ms.date: 11/04/2016
helpviewer_keywords:
- finally keyword [C++]
ms.assetid: b55f3c8e-1af0-43e8-bcfb-99c3685d2578
ms.openlocfilehash: cb2bbdb36a102c7ef8974a9ac210473f2306f5d6
ms.sourcegitcommit: dedd4c3cb28adec3793329018b9163ffddf890a4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/11/2019
ms.locfileid: "57746777"
---
# <a name="finally"></a>finally

В дополнение к `try` и `catch` предложений, поддержка обработки исключений CLR `finally` предложение. Семантика идентична `__finally` блока в структурированной обработки исключений (SEH). Объект `__finally` можно выполнить блок `try` или `catch` блока.

## <a name="remarks"></a>Примечания

Цель `finally` блок должен освободить все ресурсы, после возникновения исключения. Обратите внимание, что `finally` блоке выполняется всегда, даже если исключение не создано. `catch` Блок выполняется только в том случае, если управляемое исключение возникает в пределах связанного `try` блока.

`finally` — контекстно-зависимые ключевое слово; см. в разделе [контекстные ключевые слова](../windows/context-sensitive-keywords-cpp-component-extensions.md) Дополнительные сведения.

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

[Обработка исключений](../windows/exception-handling-cpp-component-extensions.md)
