---
title: Класс path
ms.date: 09/27/2018
f1_keywords:
- filesystem/std::experimental::filesystem::path
ms.assetid: 8a1227ca-aeb2-4e0e-84aa-86e34e4f4fe8
ms.openlocfilehash: 10c865aa2bc2431850c69e9dfedbef37414b2cb9
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/24/2019
ms.locfileid: "68455099"
---
# <a name="path-class"></a>Класс path

Класс **path** сохраняет объект типа `string_type`, который вызывается `myname` здесь в целях демонстрации, который можно использовать в качестве пути. `string_type`является синонимом для `basic_string<value_type>`, где `value_type` является синонимом для **wchar_t** в Windows или **char** в POSIX.

Дополнительные сведения и примеры кода см. в разделе [Навигация по файловой системе (C++)](../standard-library/file-system-navigation.md).

## <a name="syntax"></a>Синтаксис

```cpp
class path;
```

### <a name="constructors"></a>Конструкторы

|Конструктор|Описание|
|-|-|
|[path](#path)|Создает документ `path`.|

### <a name="typedefs"></a>Определения типов

|Имя типа|Описание|
|-|-|
|[const_iterator](#const_iterator)|Синоним для `iterator`.|
|[iterator](#iterator)|Итератор двунаправленной константы, обозначающий `path` `myname`компоненты.|
|[string_type](#string_type)|Тип является синонимом `basic_string<value_type>`.|

### <a name="member-functions"></a>Функции-члены

|Функция Member|Описание|
|-|-|
|[append](#append)|Добавляет указанную последовательность в `mypath`, преобразует и вставляет preferred_separator по мере необходимости.|
|[assign](#assign)|Заменяет `mypath` на указанную последовательность, преобразованную при необходимости.|
|[begin](#begin)|Возвращает значение `path::iterator` , обозначающее первый элемент пути в пути, если он есть.|
|[c_str](#c_str)|Возвращает указатель на первый символ в `mypath`.|
|[clear](#clear)|`mypath.clear()`Выполняется.|
|[compare](#compare)|Возвращает значения сравнения.|
|[сцеплен](#compare)|Добавляет указанную последовательность в `mypath`, преобразованную (но не вставляя разделитель) по мере необходимости.|
|[empty](#empty)|Возвращает `mypath.empty()`.|
|[end](#end)|Возвращает итератор конца последовательности типа `iterator`.|
|[продлен](#extension)|Возвращает суффикс `filename()`.|
|[filename](#filename)|Возвращает компонент корневого каталога myname, а именно `empty() path() : *--end()`. Компонент может быть пустым.|
|[generic_string](#generic_string)|Возвращает значение `this->string<Elem, Traits, Alloc>(al)` с (в Windows) любой обратной косой чертой, преобразованной в прямую косую черту.|
|[generic_u16string](#generic_u16string)|Возвращает значение `u16string()` с (в Windows) любой обратной косой чертой, преобразованной в прямую косую черту.|
|[generic_u32string](#generic_u32string)|Возвращает значение `u32string()` с (в Windows) любой обратной косой чертой, преобразованной в прямую косую черту.|
|[generic_u8string](#generic_u8string)|Возвращает значение `u8string()` с (в Windows) любой обратной косой чертой, преобразованной в прямую косую черту.|
|[generic_wstring](#generic_wstring)|Возвращает значение `wstring()` с (в Windows) любой обратной косой чертой, преобразованной в прямую косую черту.|
|[has_extension](#has_extension)|Возвращает `!extension().empty()`.|
|[has_filename](#has_filename)|Возвращает `!filename().empty()`.|
|[has_parent_path](#has_parent_path)|Возвращает `!parent_path().empty()`.|
|[has_relative_path](#has_relative_path)|Возвращает `!relative_path().empty()`.|
|[has_root_directory](#has_root_directory)|Возвращает `!root_directory().empty()`.|
|[has_root_name](#has_root_name)|Возвращает `!root_name().empty()`.|
|[has_root_path](#has_root_path)|Возвращает `!root_path().empty()`.|
|[has_stem](#has_stem)|Возвращает `!stem().empty()`.|
|[is_absolute](#is_absolute)|Для Windows функция возвращает `has_root_name() && has_root_directory()`. Для POSIX функция возвращает `has_root_directory()`.|
|[is_relative](#is_relative)|Возвращает `!is_absolute()`.|
|[make_preferred](#make_preferred)|При необходимости преобразует каждый разделитель в preferred_separator.|
|[native](#native)|Возвращает `myname`.|
|[parent_path](#parent_path)|Возвращает компонент `myname`родительского пути.|
|[preferred_separator](#preferred_separator)|Постоянный объект предоставляет предпочтительный символ для разделения компонентов пути в зависимости от операционной системы размещения. |
|[relative_path](#relative_path)|Возвращает компонент `myname`относительного пути. |
|[remove_filename](#remove_filename)|Удаляет имя файла.|
|[replace_extension](#replace_extension)|Заменяет расширение `myname`. |
|[replace_filename](#replace_filename)|Рреплацес имя файла.|
|[root_directory](#root_directory)|Возвращает компонент `myname`корневого каталога. |
|[root_name](#root_name)|Возвращает компонент `myname`корневого имени. |
|[root_path](#root_path)|Возвращает компонент `myname`корневого пути.|
|[слов](#stem)|`stem` Возвращает`myname`компонент.|
|[string](#string)|Преобразует последовательность, хранящуюся `mypath`в.|
|[swap](#swap)|`swap(mypath, right.mypath)`Выполняется.|
|[u16string](#u16string)|Преобразует последовательность, хранимую `mypath` в, в кодировку UTF-16 и возвращает ее, хранящуюся в объекте типа. `u16string`|
|[u32string](#u32string)|Преобразует последовательность, хранимую `mypath` в, в кодировку UTF-32 и возвращает ее, хранящуюся в объекте типа. `u32string`|
|[u8string](#u8string)|Преобразует последовательность, хранимую `mypath` в, в кодировку UTF-8 и возвращает ее, хранящуюся в объекте типа. `u8string`|
|[value_type](#value_type)|Тип описывает элементы пути, предпочитаемые в системе размещения.|
|[wstring](#wstring)|Преобразует последовательность, хранящуюся `mypath` в, в кодировку, предпочтительную хост- `wchar_t` системой для последовательности и возвращает ее, хранящуюся в объекте `wstring`типа.|

### <a name="operators"></a>Операторы

|Оператор|Описание|
|-|-|
|[оператор=](#op_as)|Заменяет элементы пути копией другого пути.|
|[оператор+=](#op_add)|Различные `concat` выражения.|
|[оператор/=](#op_divide)|Различные `append` выражения.|
|[Оператор string_type](#op_string)|Возвращает `myname`.|

## <a name="requirements"></a>Требования

**Заголовок:** \<> FileSystem

**Пространство имен:** std::experimental::filesystem

## <a name="append"></a>путь:: Append

Добавляет указанную последовательность в `mypath`, преобразует и `preferred_separator` вставляет при необходимости.

```cpp
template <class Source>
path& append(const Source& source);

template <class InIt>
path& append(InIt first, InIt last);
```

### <a name="parameters"></a>Параметры

*источника*\
Указанная последовательность.

*началь*\
Начало указанной последовательности.

*Последняя*\
Конец указанной последовательности.

## <a name="assign"></a>путь:: Assign

Заменяет `mypath` на указанную последовательность, преобразованную при необходимости.

```cpp
template <class Source>
path& assign(const Source& source);

template <class InIt>
path& assign(InIt first, InIt last);
```

### <a name="parameters"></a>Параметры

*источника*\
Указанная последовательность.

*началь*\
Начало указанной последовательности.

*Последняя*\
Конец указанной последовательности.

## <a name="begin"></a>путь:: начало

Возвращает значение `path::iterator` , обозначающее первый элемент пути в пути, если он есть.

```cpp
iterator begin() const;
```

## <a name="c_str"></a>путь:: c_str

Возвращает указатель на первый символ в `mypath`.

```cpp
const value_type& *c_str() const noexcept;
```

## <a name="clear"></a>путь:: Clear

`mypath.clear()`Выполняется.

```cpp
void clear() noexcept;
```

## <a name="compare"></a>путь:: Compare

Первая функция возвращает `mypath.compare(pval.native())`. Вторая функция возвращает `mypath.compare(str)`. Третья функция возвращает `mypath.compare(ptr)`.

```cpp
int compare(const path& pval) const noexcept;
int compare(const string_type& str) const;
int compare(const value_type *ptr) const;
```

### <a name="parameters"></a>Параметры

*Pval*\
Путь для сравнения.

*str*\
Сравниваемая строка.

*указатель*\
Указатель на сравниваемый.

## <a name="concat"></a>путь:: Concat

Добавляет указанную последовательность в `mypath`, преобразованную (но не вставляя разделитель) по мере необходимости.

```cpp
template <class Source>
path& concat(const Source& source);

template <class InIt>
path& concat(InIt first, InIt last);
```

### <a name="parameters"></a>Параметры

*источника*\
Указанная последовательность.

*началь*\
Начало указанной последовательности.

*Последняя*\
Конец указанной последовательности.

## <a name="const_iterator"></a>путь:: const_iterator

Синоним для `iterator`.

```cpp
typedef iterator const_iterator;
```

## <a name="empty"></a>путь:: Empty

Возвращает `mypath.empty()`.

```cpp
bool empty() const noexcept;
```

## <a name="end"></a>путь:: конец

Возвращает итератор конца последовательности типа `iterator`.

```cpp
iterator end() const;
```

## <a name="extension"></a>путь:: расширение

Возвращает суффикс `filename()`.

```cpp
path extension() const;
```

### <a name="remarks"></a>Примечания

Возвращает суффикс `filename() X` таким образом, что:

`X == path(".") || X == path("..")` Если`X` или не содержит точку, суффикс пуст.

В противном случае суффикс начинается с самой крайней правой точки (и включает ее).

## <a name="filename"></a>путь:: имя файла

Возвращает компонент корневого каталога myname, а именно `empty() path() : *--end()`. Компонент может быть пустым.

```cpp
path filename() const;
```

## <a name="generic_string"></a>путь:: generic_string

Возвращает значение `this->string<Elem, Traits, Alloc>(al)` с (в Windows) любой обратной косой чертой, преобразованной в прямую косую черту.

```cpp
template <class Elem,
    class Traits = char_traits<Elem>,
    class Alloc = allocator<Elem>>
  basic_string<Elem, Traits, Alloc>
    generic_string(const Alloc& al = Alloc()) const;

string generic_string() const;
```

## <a name="generic_u16string"></a>путь:: generic_u16string

Возвращает значение `u16string()` с (в Windows) любой обратной косой чертой, преобразованной в прямую косую черту.

```cpp
u16string generic_u16string() const;
```

## <a name="generic_u32string"></a>путь:: generic_u32string

Возвращает значение `u32string()` с (в Windows) любой обратной косой чертой, преобразованной в прямую косую черту.

```cpp
u32string generic_u32string() const;
```

## <a name="generic_u8string"></a>путь:: generic_u8string

Возвращает значение `u8string()` с (в Windows) любой обратной косой чертой, преобразованной в прямую косую черту.

```cpp
string generic_u8string() const;
```

## <a name="generic_wstring"></a>путь:: generic_wstring

Возвращает значение `wstring()` с (в Windows) любой обратной косой чертой, преобразованной в прямую косую черту.

```cpp
wstring generic_wstring() const;
```

## <a name="has_extension"></a>путь:: has_extension

Возвращает `!extension().empty()`.

```cpp
bool has_extension() const;
```

## <a name="has_filename"></a>путь:: has_filename

Возвращает `!filename().empty()`.

```cpp
bool has_filename() const;
```

## <a name="has_parent_path"></a> path::has_parent_path

Возвращает `!parent_path().empty()`.

```cpp
bool has_parent_path() const;
```

## <a name="has_relative_path"></a> path::has_relative_path

Возвращает `!relative_path().empty()`.

```cpp
bool has_relative_path() const;
```

## <a name="has_root_directory"></a>путь:: has_root_directory

Возвращает `!root_directory().empty()`.

```cpp
bool has_root_directory() const;
```

## <a name="has_root_name"></a>путь:: has_root_name

Возвращает `!root_name().empty()`.

```cpp
bool has_root_name() const;
```

## <a name="has_root_path"></a>путь:: has_root_path

Возвращает `!root_path().empty()`.

```cpp
bool has_root_path() const;
```

## <a name="has_stem"></a>путь:: has_stem

Возвращает `!stem().empty()`.

```cpp
bool has_stem() const;
```

## <a name="is_absolute"></a>путь:: is_absolute

Для Windows функция возвращает `has_root_name() && has_root_directory()`. Для POSIX функция возвращает `has_root_directory()`.

```cpp
bool is_absolute() const;
```

## <a name="is_relative"></a>путь:: is_relative

Возвращает `!is_absolute()`.

```cpp
bool is_relative() const;
```

## <a name="iterator"></a>путь:: итератор

Итератор двунаправленной константы, обозначающий компоненты `myname`пути.

```cpp
class iterator
   {
   // bidirectional iterator for path
   typedef bidirectional_iterator_tag iterator_category;
   typedef path_type value_type;
   typedef ptrdiff_t difference_type;
   typedef const value_type *pointer;
   typedef const value_type& reference;
   // ...
   };
```

### <a name="remarks"></a>Примечания

Класс описывает двунаправленный константный итератор, указывающий `path` `myname` компоненты в последовательности:

1. корневое имя (при наличии);

1. корневой каталог (при наличии);

1. остальные элементы каталога родителя `path`, если они есть, заканчивая именем файла, если оно есть

Для `pval` объекта типа `path`:

1. `path::iterator X = pval.begin()`обозначает первый `path` элемент в пути, если он есть.

1. `X == pval.end()`имеет значение true `X` , если точки сразу после конца последовательности компонентов.

3. `*X`Возвращает строку, соответствующую текущему компоненту

1. `++X` указывает на следующий компонент в последовательности, если он имеется.

1. `--X` указывает на предыдущий компонент в последовательности, если он имеется.

1. Изменение делает недействительными все итераторы, обозначающие `myname`элементы в. `myname`

## <a name="make_preferred"></a>путь:: make_preferred

Преобразует каждый разделитель в `preferred_separator` при необходимости.

```cpp
path& make_preferred();
```

## <a name="native"></a>путь:: собственный

Возвращает `myname`.

```cpp
const string_type& native() const noexcept;
```

## <a name="op_as"></a>путь:: оператор =

Заменяет элементы пути копией другого пути.

```cpp
path& operator=(const path& right);
path& operator=(path&& right) noexcept;

template <class Source>
path& operator=(const Source& source);
```

### <a name="parameters"></a>Параметры

*Правильно*\
[Путь](../standard-library/path-class.md) , который копируется в `path`.

*источника*\
Исходный путь.

### <a name="remarks"></a>Примечания

Первый оператор члена копирует `right.myname` в. `myname` Второй оператор члена `right.myname` перемещается `myname`в. Третий оператор члена ведет себя так же, как `*this = path(source)`.

## <a name="op_add"></a>путь:: operator + =

Различные `concat` выражения.

```cpp
path& operator+=(const path& right);
path& operator+=(const string_type& str);
path& operator+=(const value_type *ptr);
path& operator+=(value_type elem);

template <class Source>
path& operator+=(const Source& source);

template <class Elem>
path& operator+=(Elem elem);
```

### <a name="parameters"></a>Параметры

*Правильно*\
Добавленный путь.

*str*\
Добавленная строка.

*указатель*\
Добавленный указатель.

*Elem*\
Добавленный `value_type` или `Elem`.

*источника*\
Добавленный источник.

### <a name="remarks"></a>Примечания

Функции-члены работают так же, как следующие соответствующие выражения:

1. `concat(right);`

1. `concat(path(str));`

1. `concat(ptr);`

1. `concat(string_type(1, elem));`

1. `concat(source);`

1. `concat(path(basic_string<Elem>(1, elem)));`

## <a name="op_divide"></a>путь:: оператор/=

Различные `append` выражения.

```cpp
path& operator/=(const path& right);

template <class Source>
path& operator/=(const Source& source);
```

### <a name="parameters"></a>Параметры

*Правильно*\
Добавленный путь.

*источника*\
Добавленный источник.

### <a name="remarks"></a>Примечания

Функции-члены работают так же, как следующие соответствующие выражения:

1. `append(right);`

1. `append(source);`

## <a name="op_string"></a>путь:: operator string_type

Возвращает `myname`.

```cpp
operator string_type() const;
```

## <a name="parent_path"></a> path::parent_path

Возвращает компонент `myname`родительского пути.

```cpp
path parent_path() const;
```

### <a name="remarks"></a>Примечания

Возвращает компонент `myname`родительского пути, в частности `myname` префикс после удаления `filename().native()` и все непосредственно предшествующие разделители каталогов. (Аналогично, `begin() != end()`если это объединение всех элементов в диапазоне `[begin(), --end())` путем последовательного применения `operator/=`.) Компонент может быть пустым.

## <a name="path"></a>путь::p ь

`path` Создание различных способов.

```cpp
path();

path(const path& right);
path(path&& right) noexcept;

template <class Source>
path(const Source& source);

template <class Source>
path(const Source& source, const locale& loc);

template <class InIt>
path(InIt first, InIt last);

template <class InIt>
path(InIt first, InIt last, const locale& loc);
```

### <a name="parameters"></a>Параметры

*Правильно*\
Путь, по которому сконструированный путь должен быть копией.

*источника*\
Источник, для которого сконструированный путь должен быть копией.

*Loc*\
Указанный языковой стандарт.

*началь*\
Позиция первого элемента, который следует скопировать.

*Последняя*\
Расположение последнего элемента для копирования.

### <a name="remarks"></a>Примечания

Конструкторы всех конструкций создаются `myname` различными способами:

Для `path()` этого — `myname()`.

Для `path(const path& right` )`myname(right.myname)`это.

Для `path(path&& right)` этого — `myname(right.myname)`.

Для `template<class Source> path(const Source& source)` этого — `myname(source)`.

Для `template<class Source> path(const Source& source, const locale& loc)` `loc`этого нужнополучитьвсенеобходимыеcodecvtаспектыиз.`myname(source)`

Для `template<class InIt> path(InIt first, InIt last)` этого — `myname(first, last)`.

Для `template<class InIt> path(InIt first, InIt last, const locale& loc)` `loc`этого нужнополучитьвсенеобходимыеcodecvtаспектыиз.`myname(first, last)`

## <a name="preferred_separator"></a> path::preferred_separator

Постоянный объект предоставляет предпочтительный символ для разделения компонентов пути в зависимости от операционной системы размещения.

```cpp
#if _WIN32_C_LIB
static constexpr value_type preferred_separator == L'\\';
#else // assume Posix
static constexpr value_type preferred_separator == '/';
#endif // filesystem model now defined
```

### <a name="remarks"></a>Примечания

Обратите внимание, что в большинстве контекстов в Windows в равной мере допускается использование соответствующего символа L"/".

## <a name="relative_path"></a> path::relative_path

Возвращает компонент `myname`относительного пути.

```cpp
path relative_path() const;
```

### <a name="remarks"></a>Примечания

Возвращает компонент `myname`относительного пути, в частности `myname` суффикс после удаления `root_path().native()` , и все последующие избыточные разделители каталогов. Компонент может быть пустым.

## <a name="remove_filename"></a>путь:: remove_filename

Удаляет имя файла.

```cpp
path& remove_filename();
```

## <a name="replace_extension"></a> path::replace_extension

Заменяет расширение `myname`.

```cpp
path& replace_extension(const path& newext = path());
```

### <a name="parameters"></a>Параметры

*newext*\
Новое расширение.

### <a name="remarks"></a>Примечания

Сначала удаляет суффикс `extension().native()` из `myname`. Затем, `!newext.empty() && newext[0] != dot` если ( `dot` где `*path(".").c_str()`равно), `dot` добавляется к `myname`. Затем *newext* добавляется к `myname`.

## <a name="replace_filename"></a>путь:: replace_filename

Заменяет имя файла.

```cpp
path& replace_filename(const path& pval);
```

### <a name="parameters"></a>Параметры

*Pval*\
Путь к имени файла.

### <a name="remarks"></a>Примечания

Функция-член выполняет:

```cpp
remove_filename();

*this /= pval;
return (*this);
```

## <a name="root_directory"></a>путь:: root_directory

Возвращает компонент `myname`корневого каталога.

```cpp
path root_directory() const;
```

### <a name="remarks"></a>Примечания

Компонент может быть пустым.

## <a name="root_name"></a>путь:: root_name

Возвращает компонент `myname`корневого имени.

```cpp
path root_name() const;
```

### <a name="remarks"></a>Примечания

Компонент может быть пустым.

## <a name="root_path"></a> path::root_path

Возвращает компонент `myname`корневого пути.

```cpp
path root_path() const;
```

### <a name="remarks"></a>Примечания

Возвращает компонент `myname`корневого пути, в частности `root_name()`  / . `root_directory` Компонент может быть пустым.

## <a name="stem"></a>путь:: ресурс

`stem` Возвращает`myname`компонент.

```cpp
path stem() const;
```

### <a name="remarks"></a>Примечания

Возвращает `stem` `filename().native()` компонент, в частности, с любым удаленнымконечнымметодом.`extension().native()` `myname` Компонент может быть пустым.

## <a name="string"></a>путь:: строка

Преобразует последовательность, хранящуюся `mypath`в.

```cpp
template \<class Elem, class Traits = char_traits\<Elem>, class Alloc = allocator\<Elem>>
basic_string\<Elem, Traits, Alloc> string(const Alloc& al = Alloc()) const;
string string() const;
```

### <a name="remarks"></a>Примечания

Первая функция-член (шаблон) преобразует последовательность `mypath` , хранимую таким же образом, как:

1. `string()` для `string<char, Traits, Alloc>()`

1. `wstring()` для `string<wchar_t, Traits, Alloc>()`

1. `u16string()` для `string<char16_t, Traits, Alloc>()`

1. `u32string()` для `string<char32_t, Traits, Alloc>()`

Вторая функция-член преобразует последовательность, хранящуюся `mypath` в, в кодировку, отпользующая хост-систему для последовательности **символов** и возвращает ее, хранящуюся в `string`объекте типа.

## <a name="string_type"></a> path::string_type

Тип является синонимом `basic_string<value_type>`.

```cpp
typedef basic_string<value_type> string_type;
```

## <a name="swap"></a>путь:: swap

`swap(mypath, right.mypath)`Выполняется.

```cpp
void swap(path& right) noexcept;
```

## <a name="u16string"></a>путь:: u16string

Преобразует последовательность, хранимую `mypath` в, в кодировку UTF-16 и возвращает ее, хранящуюся в объекте типа. `u16string`

```cpp
u16string u16string() const;
```

## <a name="u32string"></a>путь:: u32string

Преобразует последовательность, хранимую `mypath` в, в кодировку UTF-32 и возвращает ее, хранящуюся в объекте типа. `u32string`

```cpp
u32string u32string() const;
```

## <a name="u8string"></a>путь:: u8string

Преобразует последовательность, хранимую `mypath` в, в кодировку UTF-8 и возвращает ее, хранящуюся в объекте типа. `u8string`

```cpp
string u8string() const;
```

## <a name="value_type"></a>путь:: value_type

Тип описывает `path` элементы, которые используются операционной системой узла.

```cpp
#if _WIN32_C_LIB
typedef wchar_t value_type;
#else // assume Posix
typedef char value_type;
#endif // filesystem model now defined
```

## <a name="wstring"></a>путь:: wstring

Преобразует последовательность, хранящуюся `mypath` в, в кодировку, предпочитаемую хост-системой для последовательности **wchar_t** , и возвращает ее, хранящуюся в `wstring`объекте типа.

```cpp
wstring wstring() const;
```

## <a name="see-also"></a>См. также

[Справочник по файлам заголовков](../standard-library/cpp-standard-library-header-files.md)
