---
title: "_set_com_error_handler | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_set_com_error_handler - функция"
ms.assetid: 49fe4fca-5e37-4d83-abaf-15be5ce37f94
caps.latest.revision: 11
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# _set_com_error_handler
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Блок, относящийся только к системам Microsoft**  
  
 Заменяет функцию по умолчанию, используемую для обработки ошибок COM.  
  
## Синтаксис  
  
```  
void __stdcall _set_com_error_handler(  
   void (__stdcall *pHandler)(  
      HRESULT hr,   
      IErrorInfo* perrinfo  
   )  
);  
```  
  
#### Параметры  
 `pHandler`  
 Указатель на функцию замены.  
  
 `hr`  
 Информация о значении `HRESULT`.  
  
 `perrinfo`  
 Объект `IErrorInfo`.  
  
## Заметки  
 По умолчанию [\_com\_raise\_error](../cpp/com-raise-error.md) обрабатывает все ошибки COM.  Это поведение можно изменить с помощью `_set_com_error_handler` для вызова собственной функции обработки ошибок.  
  
 Функция замены должна иметь сигнатуру, эквивалентную сигнатуре `_com_raise_error`.  
  
## Пример  
  
```  
// _set_com_error_handler.cpp  
// compile with /EHsc  
#include <stdio.h>  
#include <comdef.h>  
#include <comutil.h>  
  
// Importing ado dll to attempt to establish an ado connection.  
// Not related to _set_com_error_handler   
#import "C:\Program Files\Common Files\System\ado\msado15.dll" no_namespace rename("EOF", "adoEOF")  
  
void __stdcall _My_com_raise_error(HRESULT hr, IErrorInfo* perrinfo)  
{  
   throw "Unable to establish the connection!";  
}  
  
int main()  
{  
   _set_com_error_handler(_My_com_raise_error);  
   _bstr_t bstrEmpty(L"");  
   _ConnectionPtr Connection = NULL;  
   try  
   {  
      Connection.CreateInstance(__uuidof(Connection));  
      Connection->Open(bstrEmpty, bstrEmpty, bstrEmpty, 0);   
   }  
   catch(char* errorMessage)  
   {  
      printf("Exception raised: %s\n", errorMessage);  
   }  
  
   return 0;  
}  
```  
  
  **Возникает исключение: "Не удалось установить подключение\!"**   
## Требования  
 **Заголовок:** comdef.h  
  
 **Lib.** Если параметр компилятора "wchar\_t — собственный тип" включен, используйте comsuppw.lib или comsuppwd.lib.  Если этот параметр отключен, используйте comsupp.lib.  Дополнительные сведения см. в разделе [\/Zc:wchar\_t \(wchar\_t – это собственный тип\)](../build/reference/zc-wchar-t-wchar-t-is-native-type.md).  
  
## См. также  
 [Глобальные функции компилятора COM](../cpp/compiler-com-global-functions.md)