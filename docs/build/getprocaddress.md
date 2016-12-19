---
title: "GetProcAddress | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "GetProcAddress"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "DLL-библиотеки [C++], GetProcAddress"
  - "GetProcAddress - метод"
  - "порядковые номера экспортов [C++]"
ms.assetid: 48d14ae0-47ea-4c5d-96b1-2c158f1a26af
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# GetProcAddress
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Процессы, явно связанные с библиотекой DLL, вызывают функцию [GetProcAddress](http://msdn.microsoft.com/library/windows/desktop/ms683212), чтобы получить адрес экспортированной функции в DLL.  Для вызова функции DLL используется указатель возвращаемой функции.  Функция **GetProcAddress** принимает в качестве параметра дескриптор модуля DLL \(возвращаемый функцией **LoadLibrary**, `AfxLoadLibrary` или **GetModuleHandle**\), а также имя вызываемой функции или ее порядковый номер экспорта.  
  
 Поскольку функция DLL вызывается с помощью указателя и отсутствует проверка типов во время компиляции, следует убедиться, что в функции используются правильные параметры, чтобы не превысить размер выделенной в стеке памяти и не нарушить права доступа.  Безопасность типов можно обеспечить следующим образом: можно просмотреть прототипы экспортированных функций и создать соответствующие определения типов для указателей функций.  Примеры.  
  
```  
typedef UINT (CALLBACK* LPFNDLLFUNC1)(DWORD,UINT);  
...  
  
HINSTANCE hDLL;               // Handle to DLL  
LPFNDLLFUNC1 lpfnDllFunc1;    // Function pointer  
DWORD dwParam1;  
UINT  uParam2, uReturnVal;  
  
hDLL = LoadLibrary("MyDLL");  
if (hDLL != NULL)  
{  
   lpfnDllFunc1 = (LPFNDLLFUNC1)GetProcAddress(hDLL,  
                                           "DLLFunc1");  
   if (!lpfnDllFunc1)  
   {  
      // handle the error  
      FreeLibrary(hDLL);  
      return SOME_ERROR_CODE;  
   }  
   else  
   {  
      // call the function  
      uReturnVal = lpfnDllFunc1(dwParam1, uParam2);  
   }  
}  
```  
  
 Способ задания функции при вызове **GetProcAddress** зависит от способа построения библиотеки DLL.  
  
 Порядковый номер экспорта можно получить, только если библиотека DLL, с которой выполняется связывание, построена с помощью файла определения модуля \(DEF\) и если порядковые номера перечислены вместе с функциями в разделе **EXPORTS** DEF\-файла библиотеки DLL.  Вызов функции **GetProcAddress** по порядковому номеру экспорта \(в отличие от вызова по имени функции\) выполняется немного быстрее, если в библиотеке DLL имеется много экспортированных функций, поскольку порядковые номера экспорта служат в качестве индексов в таблице экспорта DLL.  По порядковому номеру экспорта функция **GetProcAddress** может непосредственно определить расположение функции, в отличие от сравнения указанного имени с именами функций в таблице экспорта DLL.  Однако следует вызывать функцию **GetProcAddress** по порядковому номеру, только если имеется контроль над присвоением порядковых номеров экспортированным функциям в DEF\-файле.  
  
## Выберите действие.  
  
-   [Неявное связывание](../Topic/Linking%20Implicitly.md)  
  
-   [Определение подходящего метода связывания](../build/determining-which-linking-method-to-use.md)  
  
## Дополнительные сведения  
  
-   [Функции LoadLibrary и AfxLoadLibrary](../build/loadlibrary-and-afxloadlibrary.md)  
  
-   [\<caps:sentence id\="tgt17" sentenceid\="8c920606bb67e2587dd3c3e5cf977593" class\="tgtSentence"\>О функции FreeLibrary\<\/caps:sentence\>](http://msdn.microsoft.com/library/windows/desktop/ms683152)  
  
-   [Экспорт из библиотеки DLL с использованием DEF\-файлов](../build/exporting-from-a-dll-using-def-files.md)  
  
## См. также  
 [DLL в Visual C\+\+](../build/dlls-in-visual-cpp.md)