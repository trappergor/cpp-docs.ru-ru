---
title: "marshal_as | Microsoft Docs"
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
  - "marshal_as"
  - "msclr.interop.marshal_as"
  - "msclr::interop::marshal_as"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "marshal_as - шаблон [C++]"
ms.assetid: 2ed717da-2b11-41e5-981d-47d251771989
caps.latest.revision: 17
caps.handback.revision: 17
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# marshal_as
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Этот метод преобразует данные размещения между управляемыми и сред.  
  
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
 Этот метод упрощенный способ преобразования данных между размещения и управляемыми типами.  Чтобы определить, какие типы данных поддерживаются см. в разделе [Общие сведения о маршалировании в C\+\+](../dotnet/overview-of-marshaling-in-cpp.md).  Преобразование некоторых данных требуют контекста.  Можно преобразовать эти типы данных с помощью [Класс marshal\_context](../dotnet/marshal-context-class.md).  
  
 При попытке маршалинг парой типов данных, которые не поддерживаются [Предупреждение C4996](../error-messages/compiler-warnings/compiler-warning-level-3-c4996.md), `marshal_as` вызовет ошибку во время компиляции.  Чтение сообщения, заданное с ошибкой дополнительные сведения.  Ошибка `C4996` можно создать дополнительные не только выступанных сопоставления функций.  Примером этого пытается маршалинг парой типов данных, которые не поддерживаются.  
  
 Библиотека маршалинга состоит из нескольких файлов заголовков.  Любое преобразование требует только одного файла, но можно включить дополнительные файлы при необходимости для других преобразований.  Чтобы увидеть, какие преобразования, с которыми связаны файлы, найденные в таблице `Marshaling Overview`.  Независимо от того, что для выполнения преобразования, требования к пространству имен всегда применяется.  
  
## Пример  
 Маршалы данного образца из `const char*` в тип переменной `System::String`.  
  
```  
// marshal_as_test.cpp  
// compile with: /clr  
#include <stdlib.h>  
#include <string.h>  
#include <msclr\marshal.h>  
  
using namespace System;  
using namespace msclr::interop;  
  
int main() {  
   const char* message = "Test String to Marshal";  
   String^ result;  
   result = marshal_as<String^>( message );  
   return 0;  
}  
```  
  
## Требования  
 **Файл заголовка.** \<msclr\\marshal.h\>, \<msclr\\marshal\_windows.h\>или \<msclr\\marshal\_cppstd.h\>\<msclr\\marshal\_atl.h\>  
  
 **Пространство имен:** msclr::interop  
  
## См. также  
 [Общие сведения о маршалировании в C\+\+](../dotnet/overview-of-marshaling-in-cpp.md)   
 [Класс marshal\_context](../dotnet/marshal-context-class.md)