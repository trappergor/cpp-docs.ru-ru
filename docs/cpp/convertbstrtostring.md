---
title: "ConvertBSTRToString | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "ConvertBSTRToString"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ConvertBSTRToString - функция"
ms.assetid: ab6ce555-3d75-4e9c-9cb8-ada6d8ce43b1
caps.latest.revision: 11
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# ConvertBSTRToString
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Блок, относящийся только к системам Microsoft**  
  
 Преобразует значение `BSTR` в **char \***.  
  
## Синтаксис  
  
```  
  
      char* __stdcall ConvertBSTRToString(  
   BSTR pSrc  
);  
```  
  
#### Параметры  
 `pSrc`  
 Переменная BSTR.  
  
## Заметки  
 `ConvertBSTRToString` выделяет строку для удаления.  
  
## Пример  
  
```  
// ConvertBSTRToString.cpp  
#include <comutil.h>  
#include <stdio.h>  
  
#pragma comment(lib, "comsuppw.lib")  
  
int main() {  
   BSTR bstrText = ::SysAllocString(L"Test");  
   wprintf_s(L"BSTR text: %s\n", bstrText);  
  
   char* lpszText2 = _com_util::ConvertBSTRToString(bstrText);  
   printf_s("char * text: %s\n", lpszText2);  
  
   SysFreeString(bstrText);  
   delete[] lpszText2;  
}  
```  
  
  **BSTR text: Test**  
**char \* text: Test**   
## Завершение блока, относящегося только к системам Microsoft  
  
## Требования  
 **Заголовок:** comutil.h.  
  
 **Библиотека:** comsuppw.lib или comsuppwd.lib \(дополнительные сведения см. в разделе [\/Zc:wchar\_t \(wchar\_t – это собственный тип\)](../build/reference/zc-wchar-t-wchar-t-is-native-type.md)\)  
  
## См. также  
 [Глобальные функции компилятора COM](../cpp/compiler-com-global-functions.md)