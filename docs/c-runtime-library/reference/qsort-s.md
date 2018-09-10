---
title: qsort_s | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- qsort_s
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
- api-ms-win-crt-utility-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- qsort_s
dev_langs:
- C++
helpviewer_keywords:
- arrays [C++], sorting
- quick-sort algorithm
- qsort_s function
- sorting arrays
ms.assetid: 6ee817b0-4408-4355-a5d4-6605e419ab91
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b136dc29431164de195eeebf9085c2377664f869
ms.sourcegitcommit: 761c5f7c506915f5a62ef3847714f43e9b815352
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2018
ms.locfileid: "44105683"
---
# <a name="qsorts"></a>qsort_s

Выполняет быструю сортировку. Версия функции [qsort](qsort.md) с усовершенствованиями системы безопасности, описанными в разделе [Функции безопасности в CRT](../../c-runtime-library/security-features-in-the-crt.md).

## <a name="syntax"></a>Синтаксис

```C
void qsort_s(
   void *base,
   size_t num,
   size_t width,
   int (__cdecl *compare )(void *, const void *, const void *),
   void * context
);
```

### <a name="parameters"></a>Параметры

*base*<br/>
Начало целевого массива.

*номер*<br/>
Размер массива в элементах.

*width*<br/>
Размер элементов в байтах.

*compare*<br/>
Функция сравнения. Первым аргументом является *контекст* указатель. Второй аргумент — указатель на *ключ* для поиска. Третий аргумент — указатель на элемент массива, который требуется сравнить с *ключ*.

*context*<br/>
Указатель на контекст, который может быть любой объект, который *сравнения* требуется доступ к подпрограммы.

## <a name="remarks"></a>Примечания

**Qsort_s** функция реализует алгоритм быстрой сортировки для сортировки массива *номер* элементов, каждый из которых *ширины* байт. Аргумент *базового* является указателем на базовый массив был отсортирован. **qsort_s** перезаписывает этот массив отсортированными элементами. Аргумент *сравнения* — это указатель на предоставляемую пользователем подпрограмму, которая сравнивает два элемента массива и возвращает значение, указывающее их связь. **qsort_s** вызовы *сравнения* рутинных один или несколько раз во время сортировки, передавая указатели на два элемента массива при каждом вызове:

```C
compare( context, (void *) & elem1, (void *) & elem2 );
```

Подпрограмма должна сравнивать элементы, а затем возвращать одно из следующих значений:

|Возвращаемое значение|Описание|
|------------------|-----------------|
|< 0|**elem1** меньше, чем **elem2**|
|0|**elem1** эквивалентно **elem2**|
|> 0|**elem1** больше, чем **elem2**|

Массив сортируется по возрастанию, как определено функцией сравнения. Для сортировки массива по убыванию измените смысл значений "больше" и "меньше" на противоположный в функции сравнения.

Если функции переданы недопустимые параметры, вызывается обработчик недопустимого параметра, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md). Если выполнение может быть продолжено, то функция возвращает и **errno** присваивается **EINVAL**. Дополнительные сведения см. в разделе [errno, _doserrno, _sys_errlist и _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

### <a name="error-conditions"></a>Условия ошибок

|клавиша|базовые|compare|num|ширина|errno|
|---------|----------|-------------|---------|-----------|-----------|
|**NULL**|any|any|any|any|**EINVAL**|
|any|**NULL**|any|!= 0|any|**EINVAL**|
|any|any|any|any|<= 0|**EINVAL**|
|any|any|**NULL**|any|any|**EINVAL**|

**qsort_s** действует так же, как **qsort** , но имеет *контекст* параметр и наборы **errno**. Путем передачи *контекст* параметра функции сравнения использовать указатель объекта для доступа к функции объекта или другие сведения, которые не доступны через указатель элемента. Добавление *контекст* делает **qsort_s** более безопасной, поскольку *контекст* позволяют избежать ошибок повторного входа с использованием статических переменных для предоставления Общие сведения, доступные для *сравнения* функции.

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**qsort_s**|\<stdlib.h> и \<search.h>|

Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

**Библиотеки:** все версии [функций библиотеки CRT](../../c-runtime-library/crt-library-features.md).

## <a name="example"></a>Пример

Следующий пример демонстрирует, как использовать *контекст* параметр в **qsort_s** функции. *Контекст* параметр облегчает выполнение потокобезопасных сортировок. Вместо того чтобы использовать статические переменные, которые должны быть синхронизированы для обеспечения потокобезопасности, можно передавать разные *контекст* параметр каждой сортировки. В этом примере используется объект языкового стандарта в качестве *контекст* параметра.

```cpp
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

### <a name="sample-output"></a>Пример результатов выполнения

```Output
Unsorted input:
weiß weis annehmen weizen Zeit weit
Español España espantado
table tableux tablet
Sorted output:
annehmen weiß weis weit weizen Zeit
España Español espantado
table tablet tableux
```

## <a name="see-also"></a>См. также

[Сортировка и поиск](../../c-runtime-library/searching-and-sorting.md)<br/>
[bsearch_s](bsearch-s.md)<br/>
[_lsearch_s](lsearch-s.md)<br/>
[qsort](qsort.md)<br/>
