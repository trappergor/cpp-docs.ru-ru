---
title: "char, wchar_t, char16_t, char32_t | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "char_cpp"
  - "char16_t_cpp"
  - "whchar_t_cpp"
  - "char32_t_cpp"
dev_langs: 
  - "C++"
ms.assetid: 6b33e9f5-455b-4e49-8f12-a150cbfe2e5b
caps.latest.revision: 2
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 2
---
# char, wchar_t, char16_t, char32_t
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

char, wchar\_t, char16\_t и char32\_t — это встроенные типы, выражающие буквенно\-цифровые символы, а также глифы и непечатаемые знаки.  Под переменную с данными типа char в памяти отводится 8 бит, типов wchar\_t и char16\_t — 16 бит, а типа char32\_t — 32 бита.  
  
## Синтаксис  
  
```vb  
char     ch1{ 'a' };  
wchar_t  ch2{ 'a' }; // or {L'a'}  
char16_t ch3{ L'a' };// or {L'a'}  
char32_t ch4{ L'a' };// or {L'a'}  
```  
  
## Заметки  
 Тип `char` был исходным символьным типом в C и C\+\+.  Он может использоваться для хранения символов из набора символов ASCII, а также из любого набора символов ISO\-8859 и UTF\-8.  Тип `unsigned char` часто используется для представления данных типа *byte*, не являющегося встроенным в C\+\+.  Тип char не подходит для текста во многих языках.  В современных программах для текста обычно используется один из типов с расширенными символами.  Юникод — это  
  
 В стандартной библиотеке C\+\+ тип basic\_string предназначен для строк, состоящих как из обычных, так и расширенных символов.  Используйте тип std::string для символов типа char и std::wstring для символов типа wchar\_t.  Другие типы, представляющие текст, включая std::stringstream и std::cout, предназначены для строк с обычными и расширенными символами.  
  
## Требования