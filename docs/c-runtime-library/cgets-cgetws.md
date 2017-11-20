---
title: "_cgets _cgetws | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _cgetws
- _cgets
apilocation:
- msvcr100.dll
- msvcr110.dll
- msvcr80.dll
- msvcr120.dll
- msvcr90.dll
- msvcrt.dll
- msvcr110_clr0400.dll
apitype: DLLExport
f1_keywords:
- cgetws
- _cgetws
- _cgets
dev_langs: C++
helpviewer_keywords:
- _cgetws function
- strings [C++], getting from console
- console, getting strings from
- _cgets function
- cgetws function
- cgets function
ms.assetid: 4d5e134a-58c3-4f62-befd-5d235b0212f4
caps.latest.revision: "32"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: ced8ca3ec392caf29cd3cbc41fe462bd24546f26
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="cgets-cgetws"></a>_cgets, _cgetws
Возвращает строку символов из консоли. Существуют более безопасные версии этих функций; см. статью [_cgets_s, _cgetws_s](../c-runtime-library/reference/cgets-s-cgetws-s.md).  
  
> [!IMPORTANT]
>  Эти функции устарели. Начиная с Visual Studio 2015 они недоступны в CRT. Безопасные версии этих функций, _cgets_s и _cgetws_s, по-прежнему доступны. Сведения об этих альтернативных функциях см. в статье [_cgets_s, _cgetws_s](../c-runtime-library/reference/cgets-s-cgetws-s.md).  
  
> [!IMPORTANT]
>  Этот API нельзя использовать в приложениях, выполняемых в среде выполнения Windows. Дополнительные сведения см. в статье [Функции CRT, которые не поддерживаются с ключом /ZW](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx).  
  
## <a name="syntax"></a>Синтаксис  
  
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
  
#### <a name="parameters"></a>Параметры  
 `buffer`  
 Место хранения данных.  
  
## <a name="return-value"></a>Возвращаемое значение  
 `_cgets` и `_cgetws` возвращают указатель на начало строки, `buffer[2]`. Если параметр `buffer` имеет значение `NULL`, вызывается обработчик недопустимых параметров, как описано в статье [Parameter Validation](../c-runtime-library/parameter-validation.md). Если выполнение может быть продолжено, они возвращают `NULL` и устанавливают для `errno` значение `EINVAL`.  
  
## <a name="remarks"></a>Примечания  
 Эти функции считывают строку символов из консоли и хранят строку и ее длину в расположении, указанном `buffer`. Параметр `buffer` должен указывать на массив символов. Первый элемент массива, `buffer[0]`, должен содержать максимальную длину (в символах) строки для считывания. Массив должен содержать достаточно элементов для хранения строки, завершающий нуль-символ ("\0") и 2 дополнительных байта. Функция читает символы до считывания сочетания возврата каретки и перевода строки (CR-LF) или до считывания указанного числа символов. Строка сохраняется начиная с `buffer[2]`. Когда функция считывает CR-LF, они сохраняет нуль-символ ("\0"). Затем функция сохраняет фактическую длину строки во втором элементе массива, `buffer[1]`.  
  
 Так как все клавиши редактирования активны при вызове `_cgets` или `_cgetws` в окне консоли, нажатие клавиши F3 повторяет последнюю введенную запись.  
  
 В C++ эти функции имеют шаблонные перегрузки, которые вызывают более новые и безопасные аналоги этих функций. Дополнительные сведения см. в разделе [Secure Template Overloads](../c-runtime-library/secure-template-overloads.md).  
  
### <a name="generic-text-routine-mappings"></a>Универсальное текстовое сопоставление функций  
  
|Подпрограмма Tchar.h|_UNICODE и _MBCS не определены|_MBCS определено|_UNICODE определено|  
|---------------------|--------------------------------------|--------------------|-----------------------|  
|`_cgetts`|`_cgets`|`_cgets`|`_cgetws`|  
  
## <a name="requirements"></a>Требования  
  
|Подпрограмма|Обязательный заголовок|  
|-------------|---------------------|  
|`_cgets`|\<conio.h>|  
|`_cgetws`|\<conio.h> или \<wchar.h>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../c-runtime-library/compatibility.md).  
  
## <a name="example"></a>Пример  
  
```  
// crt_cgets.c  
// compile with: /c /W3  
// This program creates a buffer and initializes  
// the first byte to the size of the buffer. Next, the  
// program accepts an input string using _cgets and displays  
// the size and text of that string.  
  
#include <conio.h>  
#include <stdio.h>  
#include <errno.h>  
  
int main( void )  
{  
   char buffer[83] = { 80 };  // Maximum characters in 1st byte  
   char *result;  
  
   printf( "Input line of text, followed by carriage return:\n");  
  
   // Input a line of text:  
   result = _cgets( buffer ); // C4996  
   // Note: _cgets is deprecated; consider using _cgets_s  
   if (!result)  
   {  
      printf( "An error occurred reading from the console:"  
              " error code %d\n", errno);  
   }  
   else  
   {     
      printf( "\nLine length = %d\nText = %s\n",  
              buffer[1], result );  
   }  
}  
```  
  
```Output  
  
      A line of input.Input line of text, followed by carriage return:  
Line Length = 16  
Text = A line of input.  
```  
  
## <a name="see-also"></a>См. также  
 [Ввод-вывод на консоль и порт](../c-runtime-library/console-and-port-i-o.md)   
 [_getch, _getwch](../c-runtime-library/reference/getch-getwch.md)