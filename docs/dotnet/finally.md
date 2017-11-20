---
title: "Наконец | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: finally keyword [C++]
ms.assetid: b55f3c8e-1af0-43e8-bcfb-99c3685d2578
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 55e2b77fbbcc607d802c4ea9e54d7ef56d473bd5
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="finally"></a>finally
В дополнение к `try` и `catch` предложений, поддержка обработки исключений CLR `finally` предложения. Семантика идентична `__finally` блока в структурированную обработку исключений (SEH). Объект `__finally` блок можно выполнить `try` или `catch` блока.  
  
## <a name="remarks"></a>Примечания  
 Назначение `finally` блок — Чтобы очистить все ресурсы, после возникновения исключения. Обратите внимание, что `finally` блок выполняется всегда, даже если не возникло исключение. `catch` Блок выполняется только в том случае, если управляемое исключение возникает в пределах связанного `try` блока.  
  
 `finally`— Контекстно-зависимое ключевое слово; в разделе [контекстно-зависимые ключевые слова](../windows/context-sensitive-keywords-cpp-component-extensions.md) для получения дополнительной информации.  
  
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