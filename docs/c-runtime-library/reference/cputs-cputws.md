---
title: "_cputs _cputws | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _cputws
- _cputs
apilocation:
- msvcrt.dll
- msvcr80.dll
- msvcr90.dll
- msvcr100.dll
- msvcr100_clr0400.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr120_clr0400.dll
- ucrtbase.dll
- api-ms-win-crt-conio-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- cputws
- _cputs
- _cputws
dev_langs:
- C++
helpviewer_keywords:
- strings [C++], writing
- _cputs function
- _cputws function
- putting strings to the console
- cputs function
- console, sending strings to
- cputws function
ms.assetid: ec418484-0f8d-43ec-8d8b-198a556c659e
caps.latest.revision: 16
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: a937c9d083a7e4331af63323a19fb207142604a0
ms.openlocfilehash: ebce560074526dad2181363b4998a3ad3455736f
ms.lasthandoff: 02/24/2017

---
# <a name="cputs-cputws"></a>_cputs, _cputws
Переводит строку в консоль.  
  
> [!IMPORTANT]
>  Этот API не может использоваться в приложениях, выполняемых в [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)]. Дополнительные сведения см. в статье [Функции CRT, которые не поддерживаются с ключом /ZW](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx).  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
      int _cputs(   
const char *str   
);  
int _cputws(  
const wchar_t *str   
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `str`  
 Выходная строка.  
  
## <a name="return-value"></a>Возвращаемое значение  
 В случае успеха `_cputs` возвращает 0. Если функция завершается с ошибкой, возвращается ненулевое значение.  
  
## <a name="remarks"></a>Примечания  
 Функция `_cputs` записывает строку, заканчивающуюся нулевым байтом и определенную параметром `str`, непосредственно в консоль. Сочетание символов возврата каретки и перевода строки (CR-LF) не добавляется к такой строке автоматически.  
  
 Эта функция проверяет свои параметры. Если `str` имеет значение **NULL**, вызывается обработчик недопустимых параметров, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md). Если выполнение может быть продолжено, для `errno` задается значение `EINVAL` и возвращается значение -1.  
  
### <a name="generic-text-routine-mappings"></a>Универсальное текстовое сопоставление функций  
  
|Подпрограмма Tchar.h|_UNICODE и _MBCS не определены|_MBCS определено|_UNICODE определено|  
|---------------------|--------------------------------------|--------------------|-----------------------|  
|**_cputts**|`_cputs`|`_cputs`|`_cputws`|  
  
## <a name="requirements"></a>Требования  
  
|Подпрограмма|Обязательный заголовок|Необязательный заголовок|  
|-------------|---------------------|---------------------|  
|`_cputs`|\<conio.h>|\<errno.h>|  
|`_cputws`|\<conio.h>|\<errno.h>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).  
  
## <a name="libraries"></a>Библиотеки  
 Все версии [библиотек времени выполнения языка C](../../c-runtime-library/crt-library-features.md).  
  
## <a name="example"></a>Пример  
  
```  
  
      // crt_cputs.c  
// compile with: /c  
// This program first displays a string to the console.  
  
#include <conio.h>  
#include <errno.h>  
  
void print_to_console(char* buffer)  
{  
   int retval;  
   retval = _cputs( buffer );  
   if (retval)  
   {  
       if (errno == EINVAL)  
       {  
         _cputs( "Invalid buffer in print_to_console.\r\n");  
       }  
       else  
         _cputs( "Unexpected error in print_to_console.\r\n");  
   }  
}  
  
void wprint_to_console(wchar_t* wbuffer)  
{  
   int retval;  
   retval = _cputws( wbuffer );  
   if (retval)  
   {  
       if (errno == EINVAL)  
       {  
         _cputws( L"Invalid buffer in wprint_to_console.\r\n");  
       }  
       else  
         _cputws( L"Unexpected error in wprint_to_console.\r\n");  
   }  
}  
  
int main()  
{  
  
   // String to print at console.   
   // Notice the \r (return) character.   
   char* buffer = "Hello world (courtesy of _cputs)!\r\n";  
   wchar_t *wbuffer = L"Hello world (courtesy of _cputws)!\r\n";  
   print_to_console(buffer);  
   wprint_to_console( wbuffer );  
}  
```  
  
## <a name="output"></a>Вывод  
  
```  
Hello world (courtesy of _cputs)!  
Hello world (courtesy of _cputws)!  
```  
  
## <a name="see-also"></a>См. также  
 [Ввод-вывод на консоль и порт](../../c-runtime-library/console-and-port-i-o.md)   
 [_putch, _putwch](../../c-runtime-library/reference/putch-putwch.md)
