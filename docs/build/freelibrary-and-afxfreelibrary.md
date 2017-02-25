---
title: "Функции FreeLibrary и AfxFreeLibrary | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "FreeLibrary"
  - "AfxFreeLibrary"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "библиотеки DLL расширения [C++], выгрузка"
  - "Метод AfxFreeLibrary"
  - "выгрузка библиотек DLL"
  - "Метод FreeLibrary"
  - "библиотеки DLL [C++], связывание"
  - "явное связывание [C++]"
  - "библиотеки DLL [C++], выгрузка"
ms.assetid: 4a48d290-3971-43e9-8e97-ba656cd0c8f8
caps.latest.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 11
---
# Функции FreeLibrary и AfxFreeLibrary
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Процессы, явно связанные с библиотекой DLL, вызывают функцию [FreeLibrary](http://go.microsoft.com/fwlink/p/?LinkID=259188), когда модуль DLL не требуется.  Эта функция уменьшает значение счетчика ссылок модуля и, если результат оказывается равным нулю, удаляет его из адресного пространства процесса.  
  
 В приложении MFC, используйте [AfxFreeLibrary](../Topic/AfxFreeLibrary.md) вместо `FreeLibrary` для выгрузки DLL расширения.  Интерфейс \(прототип функции\) `AfxFreeLibrary` такой же, как у функции `FreeLibrary`.  
  
## Выберите действие.  
  
-   [Неявное связывание](../Topic/Linking%20Implicitly.md)  
  
-   [Определение подходящего метода связывания](../build/determining-which-linking-method-to-use.md)  
  
## Дополнительные сведения  
  
-   [Функции LoadLibrary и AfxLoadLibrary](../build/loadlibrary-and-afxloadlibrary.md)  
  
-   [GetProcAddress](../build/getprocaddress.md)  
  
## См. также  
 [DLL в Visual C\+\+](../build/dlls-in-visual-cpp.md)   
 [О функции FreeLibrary](http://go.microsoft.com/fwlink/p/?LinkID=259188)   
 [AfxFreeLibrary](../Topic/AfxFreeLibrary.md)