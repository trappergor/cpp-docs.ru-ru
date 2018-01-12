---
title: "va_arg, va_copy, va_end, va_start | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- va_arg
- va_end
- va_copy
- va_start
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
apitype: DLLExport
f1_keywords:
- va_arg
- va_start
- va_list
- va_alist
- va_dcl
- va_copy
- va_end
dev_langs: C++
helpviewer_keywords:
- variable argument lists, accessing
- va_start macro
- va_arg macro
- va_end macro
- arguments [C++], argument lists
- va_list macro
- va_dcl macro
- va_alist macro
- va_copy macro
ms.assetid: a700dbbd-bfe5-4077-87b6-3a07af74a907
caps.latest.revision: "20"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: d131a02caf931a7696076094372678741c7a897e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="vaarg-vacopy-vaend-vastart"></a>va_arg, va_copy, va_end, va_start
Обращается к списку с переменным количеством аргументов.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
type va_arg(  
   va_list arg_ptr,  
   type   
);
void va_copy(  
   va_list dest,  
   va_list src  
); // (ISO C99 and later)  
void va_end(  
   va_list arg_ptr   
);  
void va_start(  
   va_list arg_ptr,  
   prev_param   
); // (ANSI C89 and later)  
void va_start(  
   arg_ptr   
);  // (deprecated Pre-ANSI C89 standardization version)  
```  
  
#### <a name="parameters"></a>Параметры  
 `type`  
 Тип аргумента, который требуется извлечь.  
  
 `arg_ptr`  
 Указатель на список аргументов.  
  
 `dest`  
 Указатель на список аргументов, которые нужно инициализировать из параметра `src`  
  
 `src`  
 Указатель на инициализированный список аргументов, которые требуется скопировать в параметр `dest`.  
  
 `prev_param`  
 Параметр, который предшествует первому необязательному аргументу.  
  
## <a name="return-value"></a>Возвращаемое значение  
 `va_arg` возвращает текущий аргумент. `va_copy`, `va_start` и `va_end` не возвращают значений.  
  
## <a name="remarks"></a>Примечания  
 Макросы `va_arg`, `va_copy`, `va_end` и `va_start` предоставляют переносимый способ получения аргументов функции, которая принимает переменное число аргументов. Предусмотрены две версии макросов: макросы, определенные в STDARG.H, соответствуют стандарту ISO C99; макросы, определенные в VARARGS.H, не рекомендуется использовать, но они сохранены для обратной совместимости с кодом, написанным до появления стандарта ANSI C89.  
  
 Эти макросы предполагают, что функции принимают фиксированное число обязательных аргументов, за которыми следует переменное число необязательных аргументов. Обязательные аргументы объявляются как обычные параметры для функции и доступ к ним возможен через имена параметров. Доступ к необязательным аргументам осуществляется через макросы в STDARG.H (или VARARGS.H для кода, написанного до появления стандарта ANSI C89), которые задают указатель на первый необязательный аргумент в списке аргументов, извлекают аргументы из списка и сбрасывают указатель после завершения обработки аргументов.  
  
 Стандартные макросы языка C, которые определены в STDARG.H, используются следующим образом:  
  
-   `va_start` задает указатель `arg_ptr` на первый необязательный аргументу в списке аргументов, который передан функции. Аргумент `arg_ptr` должен иметь тип `va_list`. Аргумент `prev_param` — это имя обязательного параметра, который непосредственно предшествует первому необязательному аргументу в списке аргументов. Если параметр `prev_param` объявлен в классе регистрового хранения, поведение макроса не определено. `va_start` необходимо использовать до первого использования `va_arg`.  
  
-   `va_arg` извлекает значение `type` из расположения, которое задано параметром `arg_ptr`, и увеличивает значение указателя `arg_ptr`, чтобы он указывал на следующий аргумент в списке, используя размер `type` для определения места начала следующего аргумента. `va_arg` можно использовать в функции любое количество раз, чтобы получить аргументы из списка.  
  
-   `va_copy` делает копию списка аргументов в текущем состоянии. Параметр `src` должен быть уже инициализирован с помощью `va_start`; он может быть обновлен вызовами `va_arg`, но не должен быть сброшен с помощью `va_end`. Следующий аргумент, который извлекается `va_arg` из `dest`, совпадает со следующий аргументом, который извлекается из `src`.  
  
-   После извлечения всех аргументов `va_end` сбрасывает указатель в **NULL**. `va_end` должен вызываться для каждого списка аргументов, который инициализируется `va_start` или `va_copy`, до выполнения возврата функцией.  
  
> [!NOTE]
>  Макросы в VARARGS.H использовать не рекомендуется; они сохранены только для обратной совместимости с кодом, который написан до появления стандарта ANSI C89. Во всех остальных случаях используйте макросы из файла STDARGS.H.  
  
 При компилировании с параметром [/clr (компиляция CLR)](../../build/reference/clr-common-language-runtime-compilation.md) программы, использующие эти макросы, могут давать непредвиденный результат из-за различий между собственной системой типов и системой типов среды CLR. Рассмотрим следующую программу:  
  
```  
#include <stdio.h>  
#include <stdarg.h>  
  
void testit (int i, ...)  
{  
    va_list argptr;  
    va_start(argptr, i);  
  
    if (i == 0)  
    {  
        int n = va_arg(argptr, int);  
        printf("%d\n", n);  
    }  
    else  
    {  
        char *s = va_arg(argptr, char*);  
        printf("%s\n", s);  
    }  

    va_end(argptr);  
}  
  
int main()  
{  
    testit(0, 0xFFFFFFFF); // 1st problem: 0xffffffff is not an int  
    testit(1, NULL);       // 2nd problem: NULL is not a char*  
}  
```  
  
 Обратите внимание — функция `testit` ожидает, что второй параметр будет `int` или `char*`. Передаваемые аргументы имеют значение 0xffffffff (`unsigned int`, а не `int`) и `NULL` (фактически `int`, а не `char*`). Когда программа скомпилирована для неуправляемого кода, она дает следующий результат:  
  
```Output  
-1  
  
(null)  
```  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** \<stdio.h> и \<stdarg.h>  
  
 **Нерекомендуемый заголовок:** \<varargs.h>  
  
## <a name="libraries"></a>Библиотеки  
 Все версии [библиотек времени выполнения языка C](../../c-runtime-library/crt-library-features.md).  
  
## <a name="example"></a>Пример  
  
```  
// crt_va.c  
/* Compile with: cl /W3 /Tc crt_va.c  
 * The program below illustrates passing a variable  
 * number of arguments using the following macros:  
 *      va_start            va_arg              va_copy  
 *      va_end              va_list  
 */  
  
#include <stdio.h>  
#include <stdarg.h>  
#include <math.h>  
  
double deviation(int first, ...);  
  
int main( void )  
{  
    /* Call with 3 integers (-1 is used as terminator). */  
    printf("Deviation is: %f\n", deviation(2, 3, 4, -1 ));  
  
    /* Call with 4 integers. */  
    printf("Deviation is: %f\n", deviation(5, 7, 9, 11, -1));  
  
    /* Call with just -1 terminator. */  
    printf("Deviation is: %f\n", deviation(-1));  
}  
  
/* Returns the standard deviation of a variable list of integers. */  
double deviation(int first, ...)  
{  
    int count = 0, i = first;  
    double mean = 0.0, sum = 0.0;  
    va_list marker;  
    va_list copy;  
  
    va_start(marker, first);     /* Initialize variable arguments. */  
    va_copy(copy, marker);       /* Copy list for the second pass */  
    while (i != -1)  
    {  
        sum += i;  
        count++;  
        i = va_arg(marker, int);  
    }  
    va_end(marker);              /* Reset variable argument list. */  
    mean = sum ? (sum / count) : 0.0;  
  
    i = first;                  /* reset to calculate deviation */  
    sum = 0.0;  
    while (i != -1)  
    {  
        sum += (i - mean)*(i - mean);  
        i = va_arg(copy, int);  
    }  
    va_end(copy);               /* Reset copy of argument list. */  
    return count ? sqrt(sum / count) : 0.0;  
}  
  
```  
  
## <a name="output"></a>Вывод  
  
```Output  
Deviation is: 0.816497  
Deviation is: 2.236068  
Deviation is: 0.000000  
  
```  
  
## <a name="see-also"></a>См. также  
 [Доступ к аргументам](../../c-runtime-library/argument-access.md)   
 [vfprintf, _vfprintf_l, vfwprintf, _vfwprintf_l](../../c-runtime-library/reference/vfprintf-vfprintf-l-vfwprintf-vfwprintf-l.md)