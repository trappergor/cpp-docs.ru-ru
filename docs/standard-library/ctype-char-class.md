---
title: "CType &lt; char &gt; класса | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "ctype<char>"
  - "locale/std::ctype<char>"
  - "std::ctype<char>"
  - "std.ctype<char>"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Класс CType < char >"
ms.assetid: ee30acb4-a743-405e-b3d4-13602092da84
caps.latest.revision: 20
caps.handback.revision: 20
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# CType &lt; char &gt; класса
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Класс является явной специализации шаблона класса **ctype \< CharType**> ввода `char`, описывающий объект, который можно использовать как аспект языкового стандарта для характеристики различных свойств символа типа `char`.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
template <>  
class ctype<char>  
: public ctype_base  
{  
public:  
    typedef char _Elem;  
    typedef _Elem char_type;  
    bool is(
    mask _Maskval,  
    _Elem _Ch) const;

 
    const _Elem* is(
    const _Elem* first,  
    const _Elem* last,  
    mask* dest) const;

 
    const _Elem* scan_is(
    mask _Maskval,  
    const _Elem* first,  
    const _Elem* last) const;

 
    const _Elem* scan_not(
    mask _Maskval,  
    const _Elem* first,  
    const _Elem* last) const;

 
    _Elem tolower(
    _Elem _Ch) const;

 
    const _Elem* tolower(
    _Elem* first,  
    const _Elem* last) const;

 
    _Elem toupper(
    _Elem _Ch) const;

 
    const _Elem* toupper(
    _Elem* first,  
    const _Elem* last) const;

 
    _Elem widen(
    char _Byte) const;

 
    const _Elem* widen(
    const char* first,  
    const char* last,  
    _Elem* dest) const;

 
    const _Elem* _Widen_s(
    const char* first,  
    const char* last,  
    _Elem* dest,  
    size_t dest_size) const;

 
    _Elem narrow(
    _Elem _Ch,  
    char _Dflt = '\0') const;

 
    const _Elem* narrow(
    const _Elem* first,  
    const _Elem* last,  
    char _Dflt,  
    char* dest) const;

 
    const _Elem* _Narrow_s(
    const _Elem* first,  
    const _Elem* last,  
    char _Dflt,  
    char* dest,  
    size_t dest_size) const;

 
    static locale::id& id;  
    explicit ctype(
    const mask* _Table = 0,  
    bool _Deletetable = false,  
    size_t _Refs = 0);

protected:  
    virtual ~ctype();
//other protected members  
};  
```  
  
## <a name="remarks"></a>Заметки  
 Явная специализация отличается от шаблона класса несколькими способами:  
  
-   Объект класса ctype < `char`> сохраняет указатель на первый элемент Таблица маски ctype, массив UCHAR_MAX + 1 элементов типа **ctype_base::mask**. Он также хранит объект типа Boolean, указывающее, следует ли удалять массива (с помощью `operator delete[]`) при ctype \< **Elem**> объект уничтожается.  
  
-   Его единственный открытый конструктор позволяет указать **вкладке**, таблице маски ctype и **del**, объект Boolean, равное true, если массив должен быть удалены при ctype < `char`> объект уничтожается, а также refs параметра счетчик ссылок.  
  
-   Функция-член, защищенный **таблицы** возвращает таблицу хранимых ctype маски.  
  
-   Статический член объекта **table_size** указывает минимальное количество элементов в таблице ctype маски.  
  
-   Защищенные статическую функцию-член **classic_table**(таблица маски ctype возвращает соответствующий языковой стандарт «C».  
  
-   Нет функций защищенный виртуальный член [do_is](../standard-library/ctype-class.md#ctype__do_is), [do_scan_is](../standard-library/ctype-class.md#ctype__do_scan_is), или [do_scan_not](../standard-library/ctype-class.md#ctype__do_scan_not). Соответствующий открытый член функции выполнения эквивалентных операций самостоятельно.  
  
 Функции-члены [do_narrow](../standard-library/ctype-class.md#ctype__do_narrow) и [do_widen](../standard-library/ctype-class.md#ctype__do_widen) Копировать элементы без изменений.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** \< языкового стандарта>  
  
 **Пространство имен:** std  
  
## <a name="see-also"></a>См. также  
 [Класс Facet](../Topic/facet%20Class.md)   
 [Класс ctype_base](../standard-library/ctype-base-class.md)   
 [Потокобезопасность в стандартной библиотеке C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)

