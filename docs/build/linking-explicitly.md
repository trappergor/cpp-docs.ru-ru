---
title: "Явное связывание | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "явное связывание [C++]"
ms.assetid: 1e13d960-a195-4e6d-9864-7d8f3a701f4b
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Явное связывание
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

При явном связывании приложения должны выполнять вызов функции для явной загрузки библиотеки DLL во время выполнения.  Чтобы выполнить явное связывание с библиотекой DLL, приложение должно выполнить следующие действия.  
  
-   Вызвать функцию **LoadLibrary** \(или аналогичную функцию\) для загрузки библиотеки DLL и получения дескриптора модуля.  
  
-   Вызвать функцию **GetProcAddress**, чтобы получить указатель для каждой экспортируемой функции, вызываемой приложением.  Поскольку приложения вызывают функции библиотек DLL с помощью указателя, компилятор не создает внешних ссылок, поэтому нет необходимости выполнять связывание с библиотекой импорта.  
  
-   Вызвать функцию **FreeLibrary** по завершении всех действий с библиотекой DLL.  
  
 Примеры.  
  
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
  
## Выберите действие.  
  
-   [Неявное связывание](../Topic/Linking%20Implicitly.md)  
  
-   [Определение подходящего метода связывания](../build/determining-which-linking-method-to-use.md)  
  
## Дополнительные сведения  
  
-   [Функции LoadLibrary и AfxLoadLibrary](../build/loadlibrary-and-afxloadlibrary.md)  
  
-   [Функция GetProcAddress](../build/getprocaddress.md)  
  
-   [Функции FreeLibrary и AfxFreeLibrary](../build/freelibrary-and-afxfreelibrary.md)  
  
-   [Путь поиска, используемый Windows для поиска библиотеки DLL](../build/search-path-used-by-windows-to-locate-a-dll.md)  
  
## См. также  
 [Связывание исполняемого файла с библиотекой DLL](../build/linking-an-executable-to-a-dll.md)