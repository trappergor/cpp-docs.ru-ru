---
title: "char, wchar_t, char16_t, char32_t | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- char_cpp
- char16_t_cpp
- wchar_t_cpp
- char32_t_cpp
dev_langs: C++
ms.assetid: 6b33e9f5-455b-4e49-8f12-a150cbfe2e5b
caps.latest.revision: "2"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: c01d4718bbc1781ea4705945bb90874384e09058
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="char-wchart-char16t-char32t"></a>char, wchar_t, char16_t, char32_t
char, wchar_t, char16_t и char32_t — это встроенные типы, выражающие буквенно-цифровые символы, а также глифы и непечатаемые знаки. Под переменную с данными типа char в памяти отводится 8 бит, типов wchar_t и char16_t — 16 бит, а типа char32_t — 32 бита.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
char     ch1{ 'a' };    
wchar_t  ch2{ 'a' }; // or {L'a'}    
char16_t ch3{ L'a' };// or {L'a'}    
char32_t ch4{ L'a' };// or {L'a'}  
```  
  
## <a name="remarks"></a>Примечания  
 Тип `char` был исходным символьным типом в C и C++. Он может использоваться для хранения символов из набора символов ASCII, а также из любого набора символов ISO-8859 и UTF-8. Тип `unsigned char` часто используется для представления *байтов* которого не является типом, встроенные в C++. Тип char не подходит для текста во многих языках. В современных программах для текста обычно используется один из типов с расширенными символами. Юникод — это  
  
 В стандартной библиотеке C++ тип basic_string предназначен для строк, состоящих как из обычных, так и расширенных символов. Используйте тип std::string для символов типа char и std::wstring для символов типа wchar_t. Другие типы, представляющие текст, включая std::stringstream и std::cout, предназначены для строк с обычными и расширенными символами.  
  
