---
title: "auto_handle::operator bool | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "auto_handle.operator bool"
  - "msclr.auto_handle.operator bool"
  - "operator bool"
  - "msclr::auto_handle::operator bool"
  - "auto_handle::operator bool"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "auto_handle::operator bool"
ms.assetid: 2e535e99-cf87-4008-b588-02c587d77453
caps.latest.revision: 12
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# auto_handle::operator bool
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Оператор для использования `auto_handle` в условном выражении.  
  
## Синтаксис  
  
```  
operator bool();  
```  
  
## Возвращаемое значение  
 `true` если от программу\-оболочку объект является допустимым; `false` в противном случае.  
  
## Заметки  
 Этот оператор не может быть преобразовано в значение `_detail_class::_safe_bool`, более безопасным, чем `bool`, поскольку он не может быть преобразован в целочисленный тип.  
  
## Пример  
  
```  
// msl_auto_handle_operator_bool.cpp  
// compile with: /clr  
#include <msclr\auto_handle.h>  
  
using namespace System;  
using namespace msclr;  
  
int main() {  
   auto_handle<String> s1;  
   auto_handle<String> s2 = "hi";  
   if ( s1 ) Console::WriteLine( "s1 is valid" );  
   if ( !s1 ) Console::WriteLine( "s1 is invalid" );  
   if ( s2 ) Console::WriteLine( "s2 is valid" );  
   if ( !s2 ) Console::WriteLine( "s2 is invalid" );  
   s2.reset();  
   if ( s2 ) Console::WriteLine( "s2 is now valid" );  
   if ( !s2 ) Console::WriteLine( "s2 is now invalid" );  
}  
```  
  
  **s1 недопустим**  
**допустимо s2**  
**теперь s2 недопустимо**   
## Требования  
 **Файл заголовка**\<msclr\\auto\_handle.h\>  
  
 **Пространство имен** msclr  
  
## См. также  
 [Члены auto\_handle](../dotnet/auto-handle-members.md)   
 [auto\_handle::operator\!](../dotnet/auto-handle-operator-logical-not.md)