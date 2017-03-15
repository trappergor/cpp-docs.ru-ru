---
title: "Импорт в приложение с помощью __declspec(dllimport) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "__declspec"
  - "dllimport"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__declspec(dllimport) - ключевое слово [C++]"
  - "импорт библиотек DLL [C++], __declspec(dllimport)"
ms.assetid: edb4da4e-f83a-44cf-a668-9239d49dbe42
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Импорт в приложение с помощью __declspec(dllimport)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

О программе, которая использует открытые символы, определенные библиотекой DLL, говорят, что она импортирует их.  При создании файлов заголовка для приложений, использующих библиотеки DLL, используйте **\_\_declspec\(dllimport\)** для объявления открытых символов.  Ключевое слово **\_\_declspec\(dllimport\)**работает вне зависимости осуществлен ли экспорт с помощью DEF\-файлов, или с помощью ключевого слова **\_\_declspec\(dllexport\)**.  
  
 Чтобы сделать код более читаемым, следует определить макрос для **\_\_declspec\(dllimport\)**, а затем использовать макрос для объявления каждого импортируемого символа:  
  
```  
#define DllImport   __declspec( dllimport )  
  
DllImport int  j;  
DllImport void func();  
```  
  
 Использование **\_\_declspec\(dllimport\)** является необязательным при объявлении функций, хотя компилятор выдает более эффективный код, когда данное ключевое слово используется.  Вместе с тем, следует использовать **\_\_declspec\(dllimport\)**, чтобы исполняемый файл, получил доступ к открытым символам и объектам библиотеки DLL.  Обратите внимание на то, что пользователям библиотеки DLL также необходимо связаться с библиотекой импорта.  
  
 Можно пользоваться одним и тем же файлом заголовка как для библиотеки DLL, так и для клиентского приложения.  Чтобы это сделать, используйте специальный символ препроцессора, который указывает, что строится библиотека DLL или клиентское приложение.  Примеры.  
  
```  
#ifdef _EXPORTING  
   #define CLASS_DECLSPEC    __declspec(dllexport)  
#else  
   #define CLASS_DECLSPEC    __declspec(dllimport)  
#endif  
  
class CLASS_DECLSPEC CExampleA : public CObject  
{ ... class definition ... };  
```  
  
## Выберите действие.  
  
-   [Инициализацию DLL](../build/initializing-a-dll.md)  
  
## Дополнительные сведения  
  
-   [Импорт и экспорт встроенных функций](../Topic/Importing%20and%20Exporting%20Inline%20Functions.md)  
  
-   [Взаимный импорт](../Topic/Mutual%20Imports.md)  
  
## См. также  
 [Импорт в приложение](../build/importing-into-an-application.md)