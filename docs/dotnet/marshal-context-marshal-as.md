---
title: "marshal_context::marshal_as | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "marshal_context::marshal_as"
  - "marshal_context.marshal_as"
  - "msclr.interop.marshal_context.marshal_as"
  - "msclr::interop::marshal_context::marshal_as"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "marshal_context - класс [C++], операции"
ms.assetid: 24a1afee-51c0-497c-948c-f77fe43635c8
caps.latest.revision: 14
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 14
---
# marshal_context::marshal_as
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Выполняет маршалинг в определенном объекте данных для преобразования его между управляемым и собственным типом данных.  
  
## Синтаксис  
  
```  
To_Type marshal_as<To_Type>(  
   From_Type input   
);  
```  
  
#### Параметры  
 \[входящий\] `input`  
 Значение, которое необходимо, чтобы маршалировать в `To_Type` переменная.  
  
## Возвращаемое значение  
 Переменная типа `To_Type`, преобразованное значение `input`.  
  
## Заметки  
 Эта функция выполняет маршалинг в определенном объекте данных.  Используйте эту функцию только с таблицей преобразования, показанные в [Общие сведения о маршалировании в C\+\+](../dotnet/overview-of-marshaling-in-cpp.md).  
  
 При попытке маршалинг парой типов данных, которые не поддерживаются [Предупреждение C4996](../error-messages/compiler-warnings/compiler-warning-level-3-c4996.md), `marshal_as` вызовет ошибку во время компиляции.  Чтение сообщения, заданное с ошибкой дополнительные сведения.  Ошибка `C4996` можно создать дополнительные не только выступанных сопоставления функций.  2 Условия создают эту ошибку, когда маршалинг парой типов данных, которые не поддерживаются и пытается использовать `marshal_as` для преобразования, для которого требуется контекст.  
  
 Библиотека маршалинга состоит из нескольких файлов заголовков.  Любое преобразование требует только одного файла, но можно включить дополнительные файлы при необходимости для других преобразований.  В таблице `Marshaling Overview in C++` показан файл маршалинга, должен быть включен для каждого преобразования.  
  
## Пример  
 В этом примере создается контекст для маршалинга из `System::String` в тип переменной `const char *`.  Преобразованные данные не будут допустимыми после линии, которая удаляет контекст.  
  
```  
// marshal_context_test.cpp  
// compile with: /clr  
#include <stdlib.h>  
#include <string.h>  
#include <msclr\marshal.h>  
  
using namespace System;  
using namespace msclr::interop;  
  
int main() {  
   marshal_context^ context = gcnew marshal_context();  
   String^ message = gcnew String("Test String to Marshal");  
   const char* result;  
   result = context->marshal_as<const char*>( message );  
   delete context;  
   return 0;  
}  
```  
  
## Требования  
 **Файл заголовка.** \<msclr\\marshal.h\>, \<msclr\\marshal\_windows.h\>или \<msclr\\marshal\_cppstd.h\>\<msclr\\marshal\_atl.h\>  
  
 **Пространство имен:** msclr::interop  
  
## См. также  
 [Общие сведения о маршалировании в C\+\+](../dotnet/overview-of-marshaling-in-cpp.md)   
 [marshal\_as](../dotnet/marshal-as.md)   
 [Класс marshal\_context](../dotnet/marshal-context-class.md)