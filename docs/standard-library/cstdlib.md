---
title: '&lt;cstdlib&gt;'
ms.date: 11/04/2016
f1_keywords:
- <cstdlib>
helpviewer_keywords:
- cstdlib header
ms.assetid: 0a6aaebf-84e9-4b60-ae90-17e11981cf54
ms.openlocfilehash: 70e05ad734fa49ba8cb96e4bf83bc05b99c5f55c
ms.sourcegitcommit: 3590dc146525807500c0477d6c9c17a4a8a2d658
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/16/2019
ms.locfileid: "68246530"
---
# <a name="ltcstdlibgt"></a>&lt;cstdlib&gt;

Включает C стандартный заголовок библиотеки \<stdlib.h > и добавляет связанные имена в `std` пространства имен. Включение этого заголовка гарантирует, что имена, объявленные с внешней компоновкой в заголовке стандартной библиотеки C, объявляются в `std` пространства имен.

> [!NOTE]
> \<STDLIB.h > не включает тип **wchar_t**.

## <a name="requirements"></a>Требования

**Заголовок**: \<cstdlib >

**Пространство имен:** std

## <a name="namespace-and-macros"></a>Пространство имен и макросы

```cpp
namespace std {
    using size_t = see definition;
    using div_t = see definition;
    using ldiv_t = see definition;
    using lldiv_t = see definition;
}

#define NULL
#define EXIT_FAILURE
#define EXIT_SUCCESS
#define RAND_MAX
#define MB_CUR_MAX
```

## <a name="exposition-only-functions"></a>Только функций надстройках

```cpp
extern "C" using c-atexit-handler = void();
extern "C++" using atexit-handler = void();
extern "C" using c-compare-pred = int(const void*, const void*);
extern "C++" using compare-pred = int(const void*, const void*);
```

## <a name="start-and-termination-functions"></a>Запуск и завершение функции

|Функция|Описание|
|-|-|
|[_Exit](#_exit)|Завершает программу без использования деструкторов или зарегистрированных функций.|
|[abort](#abort)|Завершает программу без использования деструкторы.|
|[atexit](#atexit)|Функция регистры для завершения программы.|
|[exit](#exit)|Уничтожает объекты с помощью потока и статическое хранилище, затем возвращает управление.|
|[at_quick_exit](#at_quick_exit)|Функция регистры без аргументов для завершения программы.|
|[quick_exit](#quick_exit)|Функция регистры сохраняются объектами, для завершения программы.|
|[getenv](#getenv)|См. в разделе Справочник по стандартной библиотеке C.|
|[system](#system)|См. в разделе Справочник по стандартной библиотеке C.|

### <a name="_exit"></a> _Exit

```cpp
[[noreturn]] void _Exit(int status) noexcept;
```

#### <a name="remarks"></a>Примечания

Программа будет завершена без выполнения деструкторы для объектов автоматически, потока или статическую длительность хранения, так и без вызова функции, передаваемые `atexit()`. Функция `_Exit` сигнала с точки зрения.

### <a name="abort"></a> Abort

```cpp
[[noreturn]] void abort() noexcept;
```

#### <a name="remarks"></a>Примечания

Программа будет завершена без выполнения деструкторы для объектов автоматически, потока или статическую длительность хранения, так и без вызова функции, передаваемые `atexit()`. Функция `abort` сигнала с точки зрения.

### <a name="at_quick_exit"></a> at_quick_exit

```cpp
int at_quick_exit(c-atexit-handler * func) noexcept;
int at_quick_exit(atexit-handler * func) noexcept;
```

#### <a name="return-value"></a>Возвращаемое значение

Нуль, если регистрация выполняется успешно, ненулевое значение, если происходит сбой.

#### <a name="remarks"></a>Примечания

`at_quick_exit()` Функции зарегистрируйте эту функцию, на которые указывают *func* вызываться без аргументов при `quick_exit` вызывается. Он этот атрибут не задан ли вызов `at_quick_exit()` этого не произойдет до всех вызовов `quick_exit` завершится успешно и `at_quick_exit()` функции не добавляют состязание за данные. Порядок регистрации может быть неопределенным Если `at_quick_exit` был вызван из более чем одного потока, а поскольку `at_quick_exit` регистраций отличаются от `atexit` регистраций, приложения нужно вызывать обе функции регистрации с помощью того же аргумента. Реализация должна поддерживать регистрацию по крайней мере 32 функции.

### <a name="atexit"></a> AtExit

```cpp
int atexit(c-atexit-handler * func) noexcept;
int atexit(atexit-handler * func) noexcept;
```

#### <a name="remarks"></a>Примечания

`atexit()` Функции зарегистрируйте эту функцию, на которые указывают *func* вызываться без аргументов при завершении программы в обычном режиме. Он этот атрибут не задан ли вызов `atexit()` этого не произойдет до вызова `exit()` завершится успешно и `atexit()` функции не добавляют состязание за данные. Реализация должна поддерживать регистрацию по крайней мере 32 функции.

#### <a name="return-value"></a>Возвращаемое значение

Возвращает нуль, если регистрация выполняется успешно, ненулевое значение, если происходит сбой.

### <a name="exit"></a> Выход

```cpp
[[noreturn]] void exit(int status);
```

#### <a name="remarks"></a>Примечания

Во-первых, объекты с длительностью хранилища потока и связанный с текущим потоком, удаляются.

Затем объекты со статической длительностью хранения удаляются и функции, зарегистрированные путем вызова `atexit` вызываются. Автоматически создаваемые объекты не уничтожается в результате вызова `exit()`. Если передачи управления из зарегистрированных функцию, вызванную `exit` потому, что функция не предоставляет обработчик для исключения, `std::terminate()` должны вызываться. Функция вызывается для каждый раз, он зарегистрирован. Объекты с автоматическую длительность хранения удаляются в программе, основная функция не содержит автоматического объектов и выполняет вызов `exit()`. Элемент управления можно передать непосредственно в основной функции путем создания исключения, перехваченные в методе main.

После этого все открытые потоки C (как при посредничестве сигнатуры функций, объявленных в <cstdio>) с незаписанных буферизованные данные являются записанных на диск, то все открытые потоки C закрываются и всех файлов, созданных вызывающими `tmpfile()` удаляются.

Наконец контроль возвращается среде узла. Если состояние равно нулю и EXIT_SUCCESS, определяемое реализацией разновидность состояние успешного завершения возвращается. Если состояние EXIT_FAILURE, определяемое реализацией разновидность неудачного завершения состояние возвращается. В противном случае состояние, возвращаемое определяется реализацией.

### <a name="getenv"></a> getenv

```cpp
char* getenv(const char* name);
```

### <a name="quick_exit"></a> quick_exit

```cpp
[[noreturn]] void quick_exit(int status) noexcept;
```

#### <a name="remarks"></a>Примечания

Функции, регистрируемых при вызовах `at_quick_exit` вызываются в порядке, обратном порядку их регистрации, за исключением того, что функция должна вызываться после все ранее зарегистрированные функции, которые уже вызван во время, она была зарегистрирована. Объекты не должны быть уничтожается в результате вызова `quick_exit`. Если передачи управления из зарегистрированных функцию, вызванную `quick_exit` потому, что функция не предоставляет обработчик для исключения, `std::terminate()` должны вызываться. Функция, зарегистрированная с помощью `at_quick_exit` вызывается потоком, который вызывает `quick_exit`, который может быть другого потока, чем тот, который зарегистрирован, поэтому зарегистрированных функций не стоит полагаться на идентификации объектов с длительностью хранилища потока. После вызова зарегистрированных функций `quick_exit` вызвал `_Exit(status)`. Стандартный файл буферы не записаны на диск. Функция `quick_exit` безопасен сигнал при регистрации функции `at_quick_exit` являются.

### <a name="system"></a> Системы

```cpp
int system(const char* string);
```

## <a name="memory-allocation-functions"></a>Функции выделения памяти

```cpp
void* aligned_alloc(size_t alignment, size_t size);
void* calloc(size_t nmemb, size_t size);
void free(void* ptr);
void* malloc(size_t size);
void* realloc(void* ptr, size_t size);
double atof(const char* nptr);
int atoi(const char* nptr);
long int atol(const char* nptr);
long long int atoll(const char* nptr);
double strtod(const char* nptr, char** endptr);
float strtof(const char* nptr, char** endptr);
long double strtold(const char* nptr, char** endptr);
long int strtol(const char* nptr, char** endptr, int base);
long long int strtoll(const char* nptr, char** endptr, int base);
unsigned long int strtoul(const char* nptr, char** endptr, int base);
unsigned long long int strtoull(const char* nptr, char** endptr, int base);
```

#### <a name="remarks"></a>Примечания

Эти функции имеют семантики, определенной в стандартной библиотеке C.

##  <a name="multibyte--wide-string-and-character-conversion-functions"></a>Многобайтовый или расширенный строку и символ функции преобразования

```cpp
int mblen(const char* s, size_t n);
int mbtowc(wchar_t* pwc, const char* s, size_t n);
int wctomb(char* s, wchar_t wchar);
size_t mbstowcs(wchar_t* pwcs, const char* s, size_t n);
size_t wcstombs(char* s, const wchar_t* pwcs, size_t n);
```

### <a name="remarks"></a>Примечания

Эти функции имеют семантики, определенной в стандартной библиотеке C.

## <a name="algorithm-functions"></a>Функции алгоритма

```cpp
void* bsearch(const void* key, const void* base, size_t nmemb, size_t size, c-compare-pred * compar);
void* bsearch(const void* key, const void* base, size_t nmemb, size_t size, compare-pred * compar);
void qsort(void* base, size_t nmemb, size_t size, c-compare-pred * compar);
void qsort(void* base, size_t nmemb, size_t size, compare-pred * compar);
```

### <a name="remarks"></a>Примечания

Эти функции имеют семантики, определенной в стандартной библиотеке C.

## <a name="low-quality-random-number-generation-functions"></a>Низкое качество случайных чисел функции для создания

```cpp
int rand();
void srand(unsigned int seed);
```

### <a name="remarks"></a>Примечания

Эти функции имеют семантики, определенной в стандартной библиотеке C.

## <a name="absolute-values"></a>Абсолютные значения

```cpp
int abs(int j);
long int abs(long int j);
long long int abs(long long int j);
float abs(float j);
double abs(double j);
long double abs(long double j);
long int labs(long int j);
long long int llabs(long long int j);
div_t div(int numer, int denom);
ldiv_t div(long int numer, long int denom);
lldiv_t div(long long int numer, long long int denom);
ldiv_t ldiv(long int numer, long int denom);
lldiv_t lldiv(long long int numer, long long int denom);
```

### <a name="remarks"></a>Примечания

Эти функции имеют семантики, определенной в стандартной библиотеке C.

## <a name="functions"></a>Функции

```cpp
void* bsearch(const void* key, const void* base, size_t nmemb, size_t size,
c-compare-pred * compar);
void* bsearch(const void* key, const void* base, size_t nmemb, size_t size,
compare-pred * compar);
void qsort(void* base, size_t nmemb, size_t size, c-compare-pred * compar);
void qsort(void* base, size_t nmemb, size_t size, compare-pred * compar);
```

## <a name="see-also"></a>См. также

[Справочник по файлам заголовков](../standard-library/cpp-standard-library-header-files.md)<br/>
[Общие сведения о стандартной библиотеке C++](../standard-library/cpp-standard-library-overview.md)<br/>
[Потокобезопасность в стандартной библиотеке C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
