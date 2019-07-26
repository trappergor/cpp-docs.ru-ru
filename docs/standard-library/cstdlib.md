---
title: '&lt;cstdlib&gt;'
ms.date: 11/04/2016
f1_keywords:
- <cstdlib>
helpviewer_keywords:
- cstdlib header
ms.assetid: 0a6aaebf-84e9-4b60-ae90-17e11981cf54
ms.openlocfilehash: 298d6a512b2863a326bda0670f33fe8f1bda0688
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/24/2019
ms.locfileid: "68449400"
---
# <a name="ltcstdlibgt"></a>&lt;cstdlib&gt;

Включает заголовок \<стандартной библиотеки C stdlib. h > и добавляет связанные имена `std` в пространство имен. Включение этого заголовка гарантирует, что имена, объявленные с помощью внешней компоновки в заголовке стандартной библиотеки C `std` , объявляются в пространстве имен.

> [!NOTE]
> \<stdlib. h > не включает тип **wchar_t**.

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

## <a name="exposition-only-functions"></a>Демонстрации только функции

```cpp
extern "C" using c-atexit-handler = void();
extern "C++" using atexit-handler = void();
extern "C" using c-compare-pred = int(const void*, const void*);
extern "C++" using compare-pred = int(const void*, const void*);
```

## <a name="start-and-termination-functions"></a>Функции запуска и завершения

|Функция|Описание|
|-|-|
|[_Exit](#_exit)|Завершает программу без использования деструкторов или зарегистрированных функций.|
|[abort](#abort)|Завершает программу без использования деструкторов.|
|[atexit](#atexit)|Регистрирует функцию для завершения программы.|
|[exit](#exit)|Уничтожает объекты с потоком и статическим хранилищем, а затем возвращает управление.|
|[at_quick_exit](#at_quick_exit)|Регистрирует функцию без аргументов для завершения программы.|
|[quick_exit](#quick_exit)|Регистрирует функцию с сохраненными объектами для завершения программы.|
|[getenv](#getenv)|См. Справочник по стандартной библиотеке C.|
|[system](#system)|См. Справочник по стандартной библиотеке C.|

### <a name="_exit"></a>_Exit

```cpp
[[noreturn]] void _Exit(int status) noexcept;
```

#### <a name="remarks"></a>Примечания

Программа завершается без выполнения деструкторов для объектов автоматической, потоковой или статической длительности хранения и без вызова функций, переданных в `atexit()`. Функция `_Exit` является сигнальной.

### <a name="abort"></a>рвал

```cpp
[[noreturn]] void abort() noexcept;
```

#### <a name="remarks"></a>Примечания

Программа завершается без выполнения деструкторов для объектов автоматической, потоковой или статической длительности хранения и без вызова функций, переданных в `atexit()`. Функция `abort` является сигнальной.

### <a name="at_quick_exit"></a>at_quick_exit

```cpp
int at_quick_exit(c-atexit-handler * func) noexcept;
int at_quick_exit(atexit-handler * func) noexcept;
```

#### <a name="return-value"></a>Возвращаемое значение

Нуль, если регистрация завершается успешно, а не равна нулю в случае сбоя.

#### <a name="remarks"></a>Примечания

Функции регистрируют функцию, на которую указывает функция *Func* , вызываемую без аргументов `quick_exit` при вызове метода. `at_quick_exit()` Он не указывается `at_quick_exit()` , `quick_exit` будет ли выполняться вызов, не выполняемый до тех `at_quick_exit()` пор, пока все вызовы не будут выполнены и функции не выдают состязание за данные. Порядок регистрации может быть неопределенным, если `at_quick_exit` был вызван из более чем одного потока и поскольку `at_quick_exit` регистрации отличаются от `atexit` регистраций, приложениям может потребоваться вызывать обе функции регистрации с помощью тот же аргумент. Реализация должна поддерживать регистрацию по крайней мере 32 функций.

### <a name="atexit"></a>atexit

```cpp
int atexit(c-atexit-handler * func) noexcept;
int atexit(atexit-handler * func) noexcept;
```

#### <a name="remarks"></a>Примечания

Функции регистрируют функцию, на которую указывает функция Func для вызова без аргументов при нормальном завершении программы.  `atexit()` Он не указывается `atexit()` , `exit()` будет ли выполняться вызов, который не происходит до того, как вызов завершится `atexit()` с ошибкой, и функции не будут представлять состязание с данными. Реализация должна поддерживать регистрацию по крайней мере 32 функций.

#### <a name="return-value"></a>Возвращаемое значение

Возвращает нуль, если регистрация завершается успешно, ненулевое значение в случае сбоя.

### <a name="exit"></a>выполняет

```cpp
[[noreturn]] void exit(int status);
```

#### <a name="remarks"></a>Примечания

Сначала уничтожаются объекты с длительностью хранилища потоков и связанные с текущим потоком.

Затем уничтожаются объекты со статической длительностью хранилища, а функции, регистрируемые `atexit` вызовом, вызываются. Автоматические объекты не уничтожаются в результате вызова `exit()`. Если элемент управления оставляет зарегистрированную функцию с `exit` именем, поскольку она не предоставляет обработчик для вызываемого исключения `std::terminate()` , то должно вызываться. Функция вызывается при каждой регистрации. Объекты с автоматическим сроком хранения уничтожаются в программе, Главная функция которой не содержит автоматических объектов, и выполняет вызов `exit()`. Элемент управления можно передать непосредственно в такую основную функцию, вызывая исключение, которое перехватывается в Main.

Затем все открытые потоки c (как исправленные сигнатуры функций, объявленные в <cstdio>) с незаписанными буферизованными данными сбрасываются, все открытые c-потоки закрываются, а все файлы, `tmpfile()` созданные при вызове, удаляются.

Наконец, управление возвращается в среду узла. Если Status имеет значение 0 или EXIT_SUCCESS, возвращается определенная реализацией форма состояния "успешно завершено". Если Status имеет значение EXIT_FAILURE, возвращается определенная в реализации форма состояния неудачного завершения. В противном случае возвращенное состояние определяется реализацией.

### <a name="getenv"></a>getenv

```cpp
char* getenv(const char* name);
```

### <a name="quick_exit"></a>quick_exit

```cpp
[[noreturn]] void quick_exit(int status) noexcept;
```

#### <a name="remarks"></a>Примечания

Функции, регистрируемые вызовами `at_quick_exit` метода, вызываются в обратную последовательность их регистрации, за исключением того, что функция должна вызываться после всех ранее зарегистрированных функций, которые уже были вызваны в момент регистрации. Объекты не должны уничтожаться в результате вызова метода `quick_exit`. Если элемент управления оставляет зарегистрированную функцию с `quick_exit` именем, поскольку она не предоставляет обработчик для вызываемого исключения `std::terminate()` , то должно вызываться. Функция, зарегистрированная `at_quick_exit` с помощью, вызывается потоком, который `quick_exit`вызывает метод, который может отличаться от потока, в котором он зарегистрирован, поэтому зарегистрированные функции не должны полагаться на удостоверение объектов с длительностью хранения потока. После вызова зарегистрированных функций `quick_exit` должен вызывать. `_Exit(status)` Стандартные буферы файлов не сбрасываются. Функция `quick_exit` является сигнальной, если функции, зарегистрированные в `at_quick_exit` , имеют значение.

### <a name="system"></a>системой

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

Эти функции имеют семантику, указанную в стандартной библиотеке C.

##  <a name="multibyte--wide-string-and-character-conversion-functions"></a>Функции преобразования многобайтовых строк и символов в расширенном виде

```cpp
int mblen(const char* s, size_t n);
int mbtowc(wchar_t* pwc, const char* s, size_t n);
int wctomb(char* s, wchar_t wchar);
size_t mbstowcs(wchar_t* pwcs, const char* s, size_t n);
size_t wcstombs(char* s, const wchar_t* pwcs, size_t n);
```

### <a name="remarks"></a>Примечания

Эти функции имеют семантику, указанную в стандартной библиотеке C.

## <a name="algorithm-functions"></a>Функции алгоритма

```cpp
void* bsearch(const void* key, const void* base, size_t nmemb, size_t size, c-compare-pred * compar);
void* bsearch(const void* key, const void* base, size_t nmemb, size_t size, compare-pred * compar);
void qsort(void* base, size_t nmemb, size_t size, c-compare-pred * compar);
void qsort(void* base, size_t nmemb, size_t size, compare-pred * compar);
```

### <a name="remarks"></a>Примечания

Эти функции имеют семантику, указанную в стандартной библиотеке C.

## <a name="low-quality-random-number-generation-functions"></a>Функции создания случайных чисел с низким качеством

```cpp
int rand();
void srand(unsigned int seed);
```

### <a name="remarks"></a>Примечания

Эти функции имеют семантику, указанную в стандартной библиотеке C.

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

Эти функции имеют семантику, указанную в стандартной библиотеке C.

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

[Справочник по файлам заголовков](../standard-library/cpp-standard-library-header-files.md)\
[Общие сведения о стандартной библиотеке C++](../standard-library/cpp-standard-library-overview.md)\
[Потокобезопасность в стандартной библиотеке C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)
