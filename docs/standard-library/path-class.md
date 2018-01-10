---
title: "Класс Path | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: filesystem/std::experimental::filesystem::path
dev_langs: C++
ms.assetid: 8a1227ca-aeb2-4e0e-84aa-86e34e4f4fe8
caps.latest.revision: "14"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 05acbc14af8daec265cf705ac4605e9606cb0696
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="path-class"></a>Класс path
Класс **path** хранит объект типа string\_type (называемый здесь myname в целях демонстрации), подходящий для использования в качестве пути. string\_type является синонимом basic\_string\<value_type>, где value\_type является синонимом типа char в Windows или wchar_t в Posix.  
  
 Дополнительные сведения и примеры кода см. в разделе [Навигация по файловой системе (C++)](../standard-library/file-system-navigation.md).  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
class path;  
```  
  
## <a name="pathappend"></a>path::append  
  
```cpp  
template <class Source>  
path& append(const Source& source);  
   
template <class InIt>  
path& append(InIt first, InIt last);
```  
  
 Функции-члены добавляют указанную последовательность в mypath, преобразуют ее и вставляют preferred_separator при необходимости.  
  
## <a name="pathassign"></a>path::assign  
  
```cpp  
template <class Source>  
path& assign(const Source& source);  
  
template <class InIt>  
path& assign(InIt first, InIt last);
```  
  
 Функции-члены заменяют mypath указанной последовательностью, преобразованной при необходимости.  
  
## <a name="pathbegin"></a>path::begin  
  
```cpp  
iterator begin() const;
```  
  
 Возвращает path::iterator, обозначающий первый элемент пути в имени пути (при наличии).  
  
## <a name="pathcstr"></a>path::c_str  
  
```cpp  
const value_type& *c_str() const noexcept;  
```  
  
 Возвращает указатель на первый символ в mypath.  
  
## <a name="pathclear"></a>path::clear  
  
```cpp  
void clear() noexcept;  
```  
  
 Функция-член выполняет mypath.clear()  
  
## <a name="pathcompare"></a>path::compare  
  
```cpp  
int compare(const path& pval) const noexcept;  
int compare(const string_type& str) const;
int compare(const value_type *ptr) const;
```  
  
 Первая функция возвращает mypath.compare(pval.native()). Вторая функция возвращает mypath.compare(str). Третья функция возвращает mypath.compare(ptr).  
  
## <a name="pathconcat"></a>path::concat  
  
```cpp  
template <class Source>  
path& concat(const Source& source);  
  
template <class InIt>  
path& concat(InIt first, InIt last);
```  
  
 Функции-члены добавляют указанную последовательность в mypath, преобразуют ее (но не вставляют разделитель) при необходимости.  
  
## <a name="pathconstiterator"></a>path::const_iterator  
  
```cpp  
typedef iterator const_iterator;  
```  
  
 Тип является синонимом для типа iterator.  
  
## <a name="pathempty"></a>path::empty  
  
```cpp  
bool empty() const noexcept;  
```  
  
 Возвращает mypath.empty().  
  
## <a name="pathend"></a>path::end  
  
```cpp  
iterator end() const;
```  
  
 Возвращает итератор конца последовательности типа iterator.  
  
## <a name="pathextension"></a>path::extension  
  
```cpp  
path extension() const;
```  
  
 Возвращает суффикс X filename() так, чтобы:  
  
 Если X == path(".") &#124;&#124; X == path("..") или X не содержит точки, суффикс будет пустым.  
  
 В противном случае суффикс начинается с самой крайней правой точки (и включает ее).  
  
## <a name="pathfilename"></a>path::filename  
  
```cpp  
path filename() const;
```  
  
 Возвращает компонент корневого каталога myname, а именно `empty()  path() : *--end()`. Компонент может быть пустым.  
  
## <a name="pathgenericstring"></a>path::generic_string  
  
```cpp  
template <class Elem,  
    class Traits = char_traits<Elem>,  
    class Alloc = allocator<Elem>>  
  basic_string<Elem, Traits, Alloc>  
    generic_string(const Alloc& al = Alloc()) const;
  
string generic_string() const;
```  
  
 Возвращает значение `this->string<Elem, Traits, Alloc>(al)` с (в Windows) любой обратной косой чертой, преобразованной в прямую косую черту.  
  
## <a name="pathgenericu16string"></a>path::generic_u16string  
  
```cpp  
u16string generic_u16string() const;
```  
  
 Возвращает значение u16string() с (в Windows) любой обратной косой чертой, преобразованной в прямую косую черту.  
  
## <a name="pathgenericu32string"></a>path::generic_u32string  
  
```cpp  
u32string generic_u32string() const;
```  
  
 Возвращает значение u32string() с (в Windows) любой обратной косой чертой, преобразованной в прямую косую черту.  
  
## <a name="pathgenericu8string"></a>path::generic_u8string  
  
```cpp  
string generic_u8string() const;
```  
  
 Возвращает значение u8string() с (в Windows) любой обратной косой чертой, преобразованной в прямую косую черту.  
  
## <a name="pathgenericwstring"></a>path::generic_wstring  
  
```cpp  
wstring generic_wstring() const;
```  
  
 Возвращает значение wstring() с (в Windows) любой обратной косой чертой, преобразованной в прямую косую черту.  
  
## <a name="pathhasextension"></a>path::has_extension  
  
```cpp  
bool has_extension() const;
```  
  
 Возвращает !extension().empty().  
  
## <a name="pathhasfilename"></a>path::has_filename  
  
```cpp  
bool has_filename() const;
```  
  
 Возвращает !filename().empty().  
  
## <a name="pathhasparentpath"></a>path::has_parent_path  
  
```cpp  
bool has_parent_path() const;
```  
  
 Возвращает !parent_path().empty().  
  
## <a name="pathhasrelativepath"></a>path::has_relative_path  
  
```cpp  
bool has_relative_path() const;
```  
  
 Возвращает !relative_path().empty().  
  
## <a name="pathhasrootdirectory"></a>path::has_root_directory  
  
```cpp  
bool has_root_directory() const;
```  
  
 Возвращает !root_directory().empty().  
  
## <a name="pathhasrootname"></a>path::has_root_name  
  
```cpp  
bool has_root_name() const;
```  
  
 Возвращает !root_name().empty().  
  
## <a name="pathhasrootpath"></a>path::has_root_path  
  
```cpp  
bool has_root_path() const;
```  
  
 Возвращает !root_path().empty().  
  
## <a name="pathhasstem"></a>path::has_stem  
  
```cpp  
bool has_stem() const;
```  
  
 Возвращает !stem().empty().  
  
## <a name="pathisabsolute"></a>path::is_absolute  
  
```cpp  
bool is_absolute() const;
```  
  
 Для Windows функция возвращает has_root_name() && has_root_directory(). Для Posix функция возвращает has_root_directory().  
  
## <a name="pathisrelative"></a>path::is_relative  
  
```cpp  
bool is_relative() const;
```  
  
 Возвращает !is_absolute().  
  
## <a name="pathiterator"></a>path::iterator  
  
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
  
 Этот класс описывает двунаправленный постоянный итератор, указывающий компоненты пути myname в последовательности:  
  
1.  корневое имя (при наличии);  
  
2.  корневой каталог (при наличии);  
  
3.  остальные элементы каталога родительского пути (при наличии), заканчивая именем файла, если оно есть.    
  
 Для pval объект типа path:  
  
1.  path::iterator X = pval.begin() указывает первый элемент пути в имени пути (при наличии).  
  
2.  X == pval.end() имеет значение true, если точки X следуют непосредственно за концом последовательности компонентов.  
  
3. *X возвращает строку, совпадающую с текущим компонентом.  
  
4.  ++X указывает следующий компонент в последовательности (при наличии).  
  
5.  --X указывает предыдущий компонент в последовательности (при наличии).  
  
6.  Изменение myname делает недействительными все итераторы, указывающие элементы в myname.  
  
## <a name="pathmakepreferred"></a>path::make_preferred  
  
```cpp  
path& make_preferred();
```  
  
 Функция-член преобразует каждый разделитель в preferred_separator при необходимости.  
  
## <a name="pathnative"></a>path::native  
  
```cpp  
const string_type& native() const noexcept;  
```  
  
 Возвращает myname.  
  
## <a name="pathoperator"></a>path::operator=  
  
```cpp  
path& operator=(const path& right);
path& operator=(path&& right) noexcept;  
  
template <class Source>  
path& operator=(const Source& source);
```  
  
 Первый оператор-член копирует right.myname в myname. Второй оператор-член перемещает right.myname в myname. Третий оператор-член работает так же, как *this = path(source).  
  
## <a name="pathoperator"></a>path::operator+=  
  
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
  
 Функции-члены работают так же, как следующие соответствующие выражения:  
  
1.  concat(right);  
  
2.  concat(path(str));  
  
3.  concat(ptr);  
  
4.  concat(string_type(1, elem));  
  
5.  concat(source);  
  
6.  concat(path(basic_string\<Elem>(1, elem)));  
  
## <a name="pathoperator"></a>path::operator/=  
  
```cpp  
path& operator/=(const path& right);  
  
template <class Source>  
path& operator/=(const Source& source);
```  
  
 Функции-члены работают так же, как следующие соответствующие выражения:  
  
1.  append(right);  
  
2.  append(source);  
  
## <a name="pathoperator-stringtype"></a>path::operator string_type  
  
```cpp  
operator string_type() const;
```  
  
 Оператор-член возвращает myname.  
  
## <a name="pathparentpath"></a>path::parent_path  
  
```cpp  
path parent_path() const;
```  
  
 Возвращает компонент родительского пути myname, а именно префикс myname, после удаления filename().native() и любых непосредственно предшествующих разделителей каталога. (Аналогично, если begin() != end(), это сочетание всех элементов в диапазоне [begin(), --end()) при успешном применении operator/=.) Компонент может быть пустым.  
  
## <a name="pathpath"></a>path::path  
  
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
  
 Все конструкторы создают myname различными способами.  
  
 Для path() — это myname().  
  
 Для path(const path& right) — это myname(right.myname).  
  
 Для path(path&& right) — это myname(right.myname).  
  
 Для template\<class Source> path(const Source& source) это будет myname(source).  
  
 Для template\<class Source> path(const Source& source, const locale& loc) это будет myname(source) с получением любых необходимых аспектов codecvt из loc.  
  
 Для template\<class InIt> path(InIt first, InIt last) это будет myname(first, last).  
  
 Для template\<class InIt> path(InIt first, InIt last, const locale& loc) это будет myname(first, last) с получением всех необходимых аспектов codecvt из loc.  
  
## <a name="pathpreferredseparator"></a>path::preferred_separator  
  
```cpp  
#if _WIN32_C_LIB  
static constexpr value_type preferred_separator == L'\\';  
#else // assume Posix  
static constexpr value_type preferred_separator == '/';  
#endif // filesystem model now defined  
```  
  
 Постоянный объект предоставляет предпочтительный символ для разделения компонентов пути в зависимости от операционной системы размещения. Обратите внимание, что в большинстве контекстов в Windows в равной мере допускается использование соответствующего символа L"/".  
  
## <a name="pathrelativepath"></a>path::relative_path  
  
```cpp  
path relative_path() const;
```  
  
 Возвращает компонент относительного пути myname, а именно суффикс myname, после удаления root_path().native() и любых непосредственно последующих избыточных разделителей каталога. Компонент может быть пустым.  
  
## <a name="pathremovefilename"></a>path::remove_filename  
  
```cpp  
path& remove_filename();
```  
  
## <a name="pathreplaceextension"></a>path::replace_extension  
  
```cpp  
path& replace_extension(const path& newext = path());
```  
  
 Функция-член сначала удаляет суффикс extension().native() из myname. Затем, если !newext.empty() && newext[0] != dot (где dot — *path(".").c_str()), то точка добавляется к myname. Затем к myname добавляется newext.  
  
## <a name="pathreplacefilename"></a>path::replace_filename  
  
```cpp  
path& replace_filename(const path& pval);
```  
  
 Функция-член выполняет:  
  
```cpp  
remove_filename();

*this /= pval;  
return (*this);
```  
  
## <a name="pathrootdirectory"></a>path::root_directory  
  
```cpp  
path root_directory() const;
```  
  
 Возвращает компонент корневого каталога myname. Компонент может быть пустым.  
  
## <a name="pathrootname"></a>path::root_name  
  
```cpp  
path root_name() const;
```  
  
 Возвращает компонент корневого имени myname. Компонент может быть пустым.  
  
## <a name="pathrootpath"></a>path::root_path  
  
```cpp  
path root_path() const;
```  
  
 Возвращает компонент корневого пути myname, а именно root_name() / root_directory. Компонент может быть пустым.  
  
## <a name="pathstem"></a>path::stem  
  
```cpp  
path stem() const;
```  
  
 Возвращает компонент основы myname, а именно filename().native(), удаляя все конечные суффиксы extension().native(). Компонент может быть пустым.  
  
## <a name="pathstring"></a>path::string  
  
```cpp  
template \<class Elem, class Traits = char_traits\<Elem>, class Alloc = allocator\<Elem>>  
basic_string\<Elem, Traits, Alloc> string(const Alloc& al = Alloc()) const; 
string string() const;
```  
  
 Первая функция-член (шаблон) преобразует последовательность, хранимую в mypath, так же, как:  
  
1.  string() для string\<char, Traits, Alloc>()  
  
2.  wstring() для string\<wchar_t, Traits, Alloc>()  
  
3.  u16string() для string\<char16_t, Traits, Alloc>()  
  
4.  u32string() для string\<char32_t, Traits, Alloc>()  
  
 Вторая функция-член преобразует последовательность, хранимую в mypath, в кодировку, предпочитаемую в системе размещения для последовательности char, и возвращает ее, сохранив в объекте типа string.  
  
## <a name="pathstringtype"></a>path::string_type  
  
```cpp  
typedef basic_string<value_type> string_type;  
```  
  
 Тип является синонимом basic_string<value_type>.  
  
## <a name="pathswap"></a>path::swap  
  
```cpp  
void swap(path& right) noexcept;  
```  
  
 Выполняет swap(mypath, right.mypath).  
  
## <a name="pathu16string"></a>path::u16string  
  
```cpp  
u16string u16string() const;
```  
  
 Функция-член преобразует последовательность, хранимую в mypath, в кодировку UTF-16 и возвращает ее, сохранив в объект типа u16string.  
  
## <a name="pathu32string"></a>path::u32string  
  
```cpp  
u32string u32string() const;
```  
  
 Функция-член преобразует последовательность, хранимую в mypath, в кодировку UTF-32 и возвращает ее, сохранив в объект типа u32string.  
  
## <a name="pathu8string"></a>path::u8string  
  
```cpp  
string u8string() const;
```  
  
 Функция-член преобразует последовательность, хранимую в mypath, в кодировку UTF-8 и возвращает ее, сохранив в объект типа u8string.  
  
## <a name="pathvaluetype"></a>path::value_type  
  
```cpp  
#if _WIN32_C_LIB  
typedef wchar_t value_type;  
#else // assume Posix  
typedef char value_type;  
#endif // filesystem model now defined  
```  
  
 Тип описывает элементы пути, предпочитаемые в системе размещения.  
  
## <a name="pathwstring"></a>path::wstring  
  
```cpp  
wstring wstring() const;
```  
  
 Преобразует последовательность, хранимую в mypath, в кодировку, предпочитаемую в системе размещения для последовательности wchar_t, и возвращает ее, сохранив в объекте типа wstring.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** \<filesystem >  
  
 **Пространство имен:** std::experimental::filesystem
  
## <a name="see-also"></a>См. также  
 [Справочник по файлам заголовков](../standard-library/cpp-standard-library-header-files.md)

