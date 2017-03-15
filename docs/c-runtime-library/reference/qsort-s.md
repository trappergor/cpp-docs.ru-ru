---
title: "qsort_s | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "qsort_s"
apilocation: 
  - "msvcrt.dll"
  - "msvcr80.dll"
  - "msvcr90.dll"
  - "msvcr100.dll"
  - "msvcr100_clr0400.dll"
  - "msvcr110.dll"
  - "msvcr110_clr0400.dll"
  - "msvcr120.dll"
  - "msvcr120_clr0400.dll"
  - "ucrtbase.dll"
  - "api-ms-win-crt-utility-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "qsort_s"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "массивы [C++], сортировка"
  - "qsort_s - функция"
  - "алгоритм быстрой сортировки"
  - "сортировка массивов"
ms.assetid: 6ee817b0-4408-4355-a5d4-6605e419ab91
caps.latest.revision: 20
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 20
---
# qsort_s
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Выполняет быструю сортировку.  Это версия [qsort](../../c-runtime-library/reference/qsort.md) с усовершенствованиями безопасности, как описано в [Функции безопасности в CRT](../Topic/Security%20Features%20in%20the%20CRT.md).  
  
## Синтаксис  
  
```  
void qsort_s(  
   void *base,  
   size_t num,  
   size_t width,  
   int (__cdecl *compare )(void *, const void *, const void *),  
   void * context  
);  
```  
  
#### Параметры  
 `base`  
 Начало целевого массива.  
  
 `num`  
 Размер массива в элементах.  
  
 `width`  
 Размер элементов в байтах.  
  
 `compare`  
 Функция сравнения.  Первый аргумент \- это указатель `context`.  Второй аргумент \- указатель на `key` для поиска.  Третий аргумент \- указатель на элемент массива, который будет сравниваться с `key`.  
  
 `context`  
 Указатель на контекст, который может быть любым объектом, к которому необходим доступ процедуре `compare`.  
  
## Заметки  
 Функция `qsort_s` реализует алгоритм быстрой сортировки для сортировки массива из `num` элементов, каждый из которых имеет размер в `width` байт.  Аргумент `base` является указателем на начало массива для сортировки.  `qsort_s` перезапишет этот массив отсортированными элементами.  Аргумент `compare` является указателем на пользовательскую процедуру, которая сравнивает два элемента массива и возвращает значение, которое показывает, как соотносятся их значения.  `qsort_s` вызывает процедуру `compare` один или несколько раз во время сортировки, передавая указатели на два элемента массива при каждом вызове:  
  
```  
compare( context, (void *) & elem1, (void *) & elem2 );  
```  
  
 Процедура должна сравнивать элементы, а затем возвращать одно из следующих значений:  
  
|Возвращаемое значение|Описание|  
|---------------------------|--------------|  
|\< 0|`elem1` меньше чем `elem2`.|  
|0|`elem1` равен `elem2`|  
|\> 0|`elem1` больше чем `elem2`.|  
  
 Массив сортируется по возрастанию, как определено функцией сравнения.  Для сортировки массива по убыванию, измените смысл значений "больше" и "меньше" на противоположный в функции сравнения.  
  
 Если функции переданы недопустимые параметры, вызывается обработчик недопустимых параметров, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md).  Если продолжение выполнения разрешено, функция возвращает управление и устанавливает для `errno` значение `EINVAL`.  Дополнительные сведения см. в разделе [errno, \_doserrno, \_sys\_errlist, and \_sys\_nerr](../Topic/errno,%20_doserrno,%20_sys_errlist,%20and%20_sys_nerr.md).  
  
### Условия возникновения ошибки  
  
|key|base|compare|num|width|errno|  
|---------|----------|-------------|---------|-----------|-----------|  
|`NULL`|any|any|any|any|`EINVAL`|  
|any|`NULL`|any|\!\= 0|any|`EINVAL`|  
|any|any|any|any|\<\= 0|`EINVAL`|  
|any|any|`NULL`|any|any|`EINVAL`|  
  
 `qsort_s` действует так же, как и `qsort`, но имеет параметр `context` и задает значение `errno`.  Передача параметра `context` позволяет функции сравнения использовать указатель на объект для использования функциональных возможностей объекта или другой информации, которая не доступна через указатель элемента.  Добавление параметра `context` делает `qsort_s`более безопасной, поскольку `context` можно использовать, чтобы избежать ошибок повторного входа, связанных с использованием статических переменных для того, чтобы сделать общую информацию доступной для функции `compare`.  
  
## Требования  
  
|Подпрограмма|Обязательный заголовок|  
|------------------|----------------------------|  
|`qsort_s`|\<stdlib.h\> и \<search.h\>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md) во введении.  
  
 **Библиотеки:** Все версии [Особенности библиотеки CRT](../../c-runtime-library/crt-library-features.md).  
  
## Пример  
 В следующем примере показано, как использовать параметр `context` в функции `qsort_s` `` .  Параметр `context` делает легче выполнение потокобезопасных сортировок.  Вместо статических переменных, которые должны синхронизироваться, чтобы гарантировать потокобезопасность, можно передать разные параметры `context` в каждой сортировке.  В этом примере объект языкового стандарта используется в качестве параметра `context`.  
  
```  
// crt_qsort_s.cpp  
// compile with: /EHsc /MT  
#include <stdlib.h>  
#include <stdio.h>  
#include <search.h>  
#include <process.h>  
#include <locale.h>  
#include <locale>  
#include <windows.h>  
using namespace std;  
  
// The sort order is dependent on the code page.  Use 'chcp' at the  
// command line to change the codepage.  When executing this application,  
// the command prompt codepage must match the codepage used here:  
  
#define CODEPAGE_850  
  
#ifdef CODEPAGE_850  
// Codepage 850 is the OEM codepage used by the command line,  
// so \x00e1 is the German Sharp S in that codepage and \x00a4  
// is the n tilde.  
  
char *array1[] = { "wei\x00e1", "weis", "annehmen", "weizen", "Zeit",  
                   "weit" };  
char *array2[] = { "Espa\x00a4ol", "Espa\x00a4" "a", "espantado" };  
char *array3[] = { "table", "tableux", "tablet" };  
  
#define GERMAN_LOCALE "German_Germany.850"  
#define SPANISH_LOCALE "Spanish_Spain.850"  
#define ENGLISH_LOCALE "English_US.850"  
  
#endif  
  
#ifdef CODEPAGE_1252  
   // If using codepage 1252 (ISO 8859-1, Latin-1), use \x00df  
   // for the German Sharp S and \x001f for the n tilde.  
char *array1[] = { "wei\x00df", "weis", "annehmen", "weizen", "Zeit",  
                   "weit" };  
char *array2[] = { "Espa\x00f1ol", "Espa\x00f1" "a", "espantado" };  
char *array3[] = { "table", "tableux", "tablet" };  
  
#define GERMAN_LOCALE "German_Germany.1252"  
#define SPANISH_LOCALE "Spanish_Spain.1252"  
#define ENGLISH_LOCALE "English_US.1252"  
  
#endif  
  
// The context parameter lets you create a more generic compare.  
// Without this parameter, you would have stored the locale in a  
// static variable, thus making sort_array vulnerable to thread  
// conflicts.  
  
int compare( void *pvlocale, const void *str1, const void *str2)  
{  
    char s1[256];  
    char s2[256];  
    strcpy_s(s1, 256, *(char**)str1);  
    strcpy_s(s2, 256, *(char**)str2);  
    _strlwr_s( s1, sizeof(s1) );  
    _strlwr_s( s2, sizeof(s2) );  
  
    locale& loc = *( reinterpret_cast< locale * > ( pvlocale));  
  
    return use_facet< collate<char> >(loc).compare(s1,   
       &s1[strlen(s1)], s2, &s2[strlen(s2)]);  
  
}  
  
void sort_array(char *array[], int num, locale &loc)  
{  
    qsort_s(array, num, sizeof(char*), compare, &loc);  
}  
  
void print_array(char *a[], int c)  
{  
   for (int i = 0; i < c; i++)  
     printf("%s ", a[i]);  
   printf("\n");  
  
}  
  
void sort_german(void * Dummy)  
{  
   sort_array(array1, 6, locale(GERMAN_LOCALE));  
}  
  
void sort_spanish(void * Dummy)  
{     
   sort_array(array2, 3, locale(SPANISH_LOCALE));       
}  
  
void sort_english(void * Dummy)  
{     
   sort_array(array3, 3, locale(ENGLISH_LOCALE));     
}  
  
int main( )  
{  
  
   int i;  
   HANDLE threads[3];  
  
   printf("Unsorted input:\n");  
   print_array(array1, 6);  
   print_array(array2, 3);  
   print_array(array3, 3);  
  
   // Create several threads that perform sorts in different  
   // languages at the same time.   
  
   threads[0] = reinterpret_cast<HANDLE>(  
                 _beginthread( sort_german , 0, NULL));  
   threads[1] = reinterpret_cast<HANDLE>(  
                 _beginthread( sort_spanish, 0, NULL));  
   threads[2] = reinterpret_cast<HANDLE>(  
                 _beginthread( sort_english, 0, NULL));  
  
   for (i = 0; i < 3; i++)  
   {  
      if (threads[i] == reinterpret_cast<HANDLE>(-1))  
      {  
         printf("Error creating threads.\n");  
         exit(1);  
      }  
   }  
  
   // Wait until all threads have terminated.  
   WaitForMultipleObjects(3, threads, true, INFINITE);  
  
   printf("Sorted output: \n");  
  
   print_array(array1, 6);  
   print_array(array2, 3);  
   print_array(array3, 3);  
  
}  
```  
  
## Пример результатов выполнения  
  
```  
Unsorted input:  
weiß weis annehmen weizen Zeit weit   
Español España espantado   
table tableux tablet   
Sorted output:   
annehmen weiß weis weit weizen Zeit   
España Español espantado   
table tablet tableux  
```  
  
## Эквивалент в .NET Framework  
 <xref:System.Collections.ArrayList.Sort%2A>  
  
## См. также  
 [Сортировка и поиск](../../c-runtime-library/searching-and-sorting.md)   
 [bsearch\_s](../../c-runtime-library/reference/bsearch-s.md)   
 [\_lsearch\_s](../../c-runtime-library/reference/lsearch-s.md)   
 [qsort](../../c-runtime-library/reference/qsort.md)