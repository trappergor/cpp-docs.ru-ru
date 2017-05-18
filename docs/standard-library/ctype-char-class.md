---
title: "Класс ctype&lt;char&gt; | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ctype<char>
- locale/std::ctype<char>
dev_langs:
- C++
helpviewer_keywords:
- ctype<char> class
ms.assetid: ee30acb4-a743-405e-b3d4-13602092da84
caps.latest.revision: 20
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 66798adc96121837b4ac2dd238b9887d3c5b7eef
ms.openlocfilehash: 28fc5cf88c6a50b5fcd9950b68d7c6ef3529ccee
ms.contentlocale: ru-ru
ms.lasthandoff: 04/29/2017

---
# <a name="ctypeltchargt-class"></a>Класс ctype&lt;char&gt;
Этот класс представляет собой явную специализацию класса шаблона **ctype\<CharType**> для типа `char`, описывающего объект, который может использоваться в качестве аспекта языкового стандарта для характеристики различных свойств символа, относящегося к типу `char`.  
  
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
  
## <a name="remarks"></a>Примечания  
 Явная специализация отличается от класса шаблона несколькими аспектами.  
  
-   Объект класса ctype< `char`> сохраняет указатель на первый элемент таблицы маски ctype, массив UCHAR_MAX + 1 элементов типа **ctype_base::mask**. Он также хранит объект логического типа, указывающий, следует ли удалять массив (с помощью `operator delete[]`), когда удаляется объект ctype\< **Elem**>.  
  
-   Его единственный открытый конструктор позволяет указать **tab**, таблицу маски ctype и **del**, логический объект, имеющий значение true, если массив должен удаляться при удалении объекта ctype< `char`>, настроек объект уничтожается, а также ссылки параметра reference-count.  
  
-   Защищенная функция-член **table** возвращает сохраненную таблицу маски ctype.  
  
-   Статический объект-член **table_size** указывает минимальное количество элементов в таблице маски ctype.  
  
-   Защищенная статическая функция-член **classic_table** (возвращает таблицу маски ctype, соответствующую языковому стандарту "C".  
  
-   Отсутствуют защищенные виртуальные функции-члены [do_is](../standard-library/ctype-class.md#do_is), [do_scan_is](../standard-library/ctype-class.md#do_scan_is) или [do_scan_not](../standard-library/ctype-class.md#do_scan_not). Соответствующие открытые функции-члены самостоятельно выполняют эквивалентные операции.  
  
 Функции-члены [do_narrow](../standard-library/ctype-class.md#do_narrow) и [do_widen](../standard-library/ctype-class.md#do_widen) копируют элементы без изменений.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** \<locale>  
  
 **Пространство имен:** std  
  
## <a name="see-also"></a>См. также  
 [Класс facet](http://msdn.microsoft.com/Library/dd4f12f5-cb1b-457f-af56-2fb204216ec1)   
 [Класс ctype_base](../standard-library/ctype-base-class.md)   
 [Потокобезопасность в стандартной библиотеке C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)


