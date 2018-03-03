---
title: "GetProcAddress | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- GetProcAddress
dev_langs:
- C++
helpviewer_keywords:
- DLLs [C++], GetProcAddress
- ordinal exports [C++]
- GetProcAddress method
ms.assetid: 48d14ae0-47ea-4c5d-96b1-2c158f1a26af
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 2bc32c5f6b6ae4ee80c69dff028f05d2b334d920
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="getprocaddress"></a>GetProcAddress
Процессы, явно связанные до вызова функции DLL [GetProcAddress](http://msdn.microsoft.com/library/windows/desktop/ms683212) для получения адреса экспортированной функции в DLL. Используйте указатель возвращаемой вызов функции DLL. **GetProcAddress** принимает в качестве параметров дескриптор модуля DLL (возвращенных либо **LoadLibrary**, `AfxLoadLibrary`, или **GetModuleHandle**) и принимает имя функции вы необходимость в вызов функции экспорта порядковый номер.  
  
 Поскольку вы вызываете функции DLL через указатель и нет проверку типов во время компиляции, убедитесь, что правильность параметров в функцию, чтобы не превысить памяти, выделенной в стеке и вызывает нарушение прав доступа. Для просмотра прототипы экспортированных функций и создать соответствующие определения типов для указателей на функции — один из способов обеспечения безопасности типа. Пример:  
  
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
  
 Способ указания при вызове функции **GetProcAddress** зависит от того, как был построен библиотеки DLL.  
  
 Порядковый номер экспорта может получать только в случае, если создается ссылка на библиотеку DLL строится с помощью файла определения модуля (DEF) и если порядковые номера перечислены с помощью функций в **ЭКСПОРТОВ** раздел в DEF-файле библиотеки DLL. Вызов **GetProcAddress** с экспортом порядковый номер, имя функции, в отличие от немного быстрее, если библиотека DLL имеется много экспортированных функций, поскольку порядковые номера экспорта служат как индексы из DLL таблицы. С помощью порядкового номера экспорта **GetProcAddress** можно найти функцию непосредственно в отличие от сравнения указанного имени с именами функций в таблице экспорта библиотеки DLL. Тем не менее, необходимо вызвать **GetProcAddress** с порядковый номер экспорта только в том случае, если имеется контроль над присвоением порядковых номеров экспортированным функциям в DEF-файле.  
  
## <a name="what-do-you-want-to-do"></a>Выберите действие  
  
-   [Неявное связывание с библиотекой DLL](../build/linking-an-executable-to-a-dll.md#linking-implicitly)  
  
-   [Определение подходящего метода связывания](../build/linking-an-executable-to-a-dll.md#determining-which-linking-method-to-use)  
  
## <a name="what-do-you-want-to-know-more-about"></a>Дополнительные сведения  
  
-   [Функции LoadLibrary и AfxLoadLibrary](../build/loadlibrary-and-afxloadlibrary.md)  
  
-   [FreeLibrary](http://msdn.microsoft.com/library/windows/desktop/ms683152)  
  
-   [Экспорт из библиотеки DLL с использованием DEF-файлов](../build/exporting-from-a-dll-using-def-files.md)  
  
## <a name="see-also"></a>См. также  
 [DLL в Visual C++](../build/dlls-in-visual-cpp.md)