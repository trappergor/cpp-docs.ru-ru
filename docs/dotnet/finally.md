---
title: Наконец | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- finally keyword [C++]
ms.assetid: b55f3c8e-1af0-43e8-bcfb-99c3685d2578
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 70057cad8ff5bca0606f06dd43eaa485834d2c70
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33111475"
---
# <a name="finally"></a>finally
В дополнение к `try` и `catch` предложений, поддержка обработки исключений CLR `finally` предложения. Семантика идентична `__finally` блока в структурированную обработку исключений (SEH). Объект `__finally` блок можно выполнить `try` или `catch` блока.  
  
## <a name="remarks"></a>Примечания  
 Назначение `finally` блок — Чтобы очистить все ресурсы, после возникновения исключения. Обратите внимание, что `finally` блок выполняется всегда, даже если не возникло исключение. `catch` Блок выполняется только в том случае, если управляемое исключение возникает в пределах связанного `try` блока.  
  
 `finally` — Контекстно-зависимое ключевое слово; в разделе [контекстно-зависимые ключевые слова](../windows/context-sensitive-keywords-cpp-component-extensions.md) для получения дополнительной информации.  
  
## <a name="example"></a>Пример  
 В следующем примере демонстрируется простой `finally` блока:  
  
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