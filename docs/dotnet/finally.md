---
title: finally
ms.date: 11/04/2016
helpviewer_keywords:
- finally keyword [C++]
ms.assetid: b55f3c8e-1af0-43e8-bcfb-99c3685d2578
ms.openlocfilehash: 2574ba5a10bbf5eddc68d6e0265d5dfc99c6d8fc
ms.sourcegitcommit: 573b36b52b0de7be5cae309d45b68ac7ecf9a6d8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2019
ms.locfileid: "79545099"
---
# <a name="finally"></a>finally

В дополнение к предложениям `try` и `catch`, обработка исключений CLR поддерживает предложение `finally`. Семантика идентична блоку `__finally` в структурированной обработке исключений (SEH). Блок `__finally` может следовать за блоком `try` или `catch`.

## <a name="remarks"></a>Примечания

Целью блока `finally` является очистка всех ресурсов, оставшихся после возникновения исключения. Обратите внимание, что блок `finally` всегда выполняется, даже если исключение не было создано. Блок `catch` выполняется только в том случае, если управляемое исключение создается в связанном блоке `try`.

`finally` является контекстно-зависимым ключевым словом; Дополнительные сведения см. в разделе [контекстно-зависимые ключевые слова](../extensions/context-sensitive-keywords-cpp-component-extensions.md) .

## <a name="example"></a>Пример

В следующем примере показан простой блок `finally`.

```cpp
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

## <a name="see-also"></a>См. также:

[Обработка исключений](../extensions/exception-handling-cpp-component-extensions.md)
