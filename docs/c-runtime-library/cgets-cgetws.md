---
title: "_cgets, _cgetws | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_cgetws"
  - "_cgets"
apilocation: 
  - "msvcr100.dll"
  - "msvcr110.dll"
  - "msvcr80.dll"
  - "msvcr120.dll"
  - "msvcr90.dll"
  - "msvcrt.dll"
  - "msvcr110_clr0400.dll"
apitype: "DLLExport"
f1_keywords: 
  - "cgetws"
  - "_cgetws"
  - "_cgets"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_cgets - функция"
  - "_cgetws - функция"
  - "cgets - функция"
  - "cgetws - функция"
  - "консоль, получение строк из"
  - "строки [C++], получение из консоли"
ms.assetid: 4d5e134a-58c3-4f62-befd-5d235b0212f4
caps.latest.revision: 32
caps.handback.revision: 32
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _cgets, _cgetws
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Возвращает строку символов из консоли. Существуют более безопасные версии этих функций; см. статью [\_cgets\_s, \_cgetws\_s](../Topic/_cgets_s,%20_cgetws_s.md).  
  
> [!IMPORTANT]
>  Эти функции устарели. Начиная с Visual Studio 2015 они недоступны в CRT. Безопасные версии этих функций, \_cgets\_s и \_cgetws\_s, по\-прежнему доступны. Сведения об этих альтернативных функциях см. в статье [\_cgets\_s, \_cgetws\_s](../Topic/_cgets_s,%20_cgetws_s.md).  
  
> [!IMPORTANT]
>  Этот API нельзя использовать в приложениях, выполняемых в среде выполнения Windows. Дополнительные сведения см. в статье [Функции CRT, которые не поддерживаются с ключом \/ZW](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx).  
  
## Синтаксис  
  
```  
char *_cgets(   
   char *buffer   
);  
wchar_t *_cgetws(  
   wchar_t *buffer  
);  
template <size_t size>  
char *_cgets(   
   char (&buffer)[size]  
); // C++ only  
template <size_t size>  
wchar_t *_cgetws(  
   wchar_t (&buffer)[size]  
); // C++ only  
```  
  
#### Параметры  
 `buffer`  
 Место хранения данных.  
  
## Возвращаемое значение  
 `_cgets` и `_cgetws` возвращают указатель на начало строки, `buffer[2]`. Если параметр `buffer` имеет значение `NULL`, вызывается обработчик недопустимых параметров, как описано в статье [Проверка параметров](../c-runtime-library/parameter-validation.md). Если выполнение может быть продолжено, они возвращают `NULL` и устанавливают для `errno` значение `EINVAL`.  
  
## Заметки  
 Эти функции считывают строку символов из консоли и хранят строку и ее длину в расположении, указанном `buffer`. Параметр `buffer` должен указывать на массив символов. Первый элемент массива, `buffer[0]`, должен содержать максимальную длину \(в символах\) строки для считывания. Массив должен содержать достаточно элементов для хранения строки, завершающий нуль\-символ \("\\0"\) и 2 дополнительных байта. Функция читает символы до считывания сочетания возврата каретки и перевода строки \(CR\-LF\) или до считывания указанного числа символов. Строка сохраняется начиная с `buffer[2]`. Когда функция считывает CR\-LF, они сохраняет нуль\-символ \("\\0"\). Затем функция сохраняет фактическую длину строки во втором элементе массива, `buffer[1]`.  
  
 Так как все клавиши редактирования активны при вызове `_cgets` или `_cgetws` в окне консоли, нажатие клавиши F3 повторяет последнюю введенную запись.  
  
 В C\+\+ эти функции имеют шаблонные перегрузки, которые вызывают более новые и безопасные аналоги этих функций. Дополнительные сведения см. в разделе [Безопасные перегрузки шаблонов](../Topic/Secure%20Template%20Overloads.md).  
  
### Универсальное текстовое сопоставление функций  
  
|Подпрограмма Tchar.h|\_UNICODE и \_MBCS не определены|\_MBCS определено|\_UNICODE определено|  
|--------------------------|--------------------------------------|-----------------------|--------------------------|  
|`_cgetts`|`_cgets`|`_cgets`|`_cgetws`|  
  
## Требования  
  
|Подпрограмма|Обязательный заголовок|  
|------------------|----------------------------|  
|`_cgets`|\<conio.h\>|  
|`_cgetws`|\<conio.h\> или \<wchar.h\>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../c-runtime-library/compatibility.md).  
  
## Пример  
  
```  
// crt_cgets.c // compile with: /c /W3 // This program creates a buffer and initializes // the first byte to the size of the buffer. Next, the // program accepts an input string using _cgets and displays // the size and text of that string. #include <conio.h> #include <stdio.h> #include <errno.h> int main( void ) { char buffer[83] = { 80 };  // Maximum characters in 1st byte char *result; printf( "Input line of text, followed by carriage return:\n"); // Input a line of text: result = _cgets( buffer ); // C4996 // Note: _cgets is deprecated; consider using _cgets_s if (!result) { printf( "An error occurred reading from the console:" " error code %d\n", errno); } else { printf( "\nLine length = %d\nText = %s\n", buffer[1], result ); } }  
```  
  
```Output  
  
A line of input.Ввод строки текста, после которого следует возврат каретки: длина строки — 16, текст — A line of input (Строка ввода).  
```  
  
## См. также  
 [Ввод\-вывод на консоль и порт](../c-runtime-library/console-and-port-i-o.md)   
 [\_getch, \_getwch](../Topic/_getch,%20_getwch.md)