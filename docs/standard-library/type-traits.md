---
title: "&lt;type_traits&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "<type_traits>"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "typetrait - заголовок [TR1]"
  - "type_traits"
ms.assetid: 2260b51f-8160-4c66-a82f-00b534cb60d4
caps.latest.revision: 35
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 35
---
# &lt;type_traits&gt;
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Определяет шаблоны, содержащие константы времени компиляции, которые предоставляют сведения о свойствах аргументов их типа или создают преобразования типов.  
  
## Синтаксис  
  
```  
#include <type_traits>  
```  
  
## Заметки  
 Классы и шаблоны в `<type_traits>` используются для поддержки вывода типа, классификации и преобразование во время компиляции для обнаружения ошибок, связанных с типом и оптимизировать универсального кода. Эти классы и шаблоны включают унарный признаки типов, описывающие свойство типа двоичного типа признаки, описывающие связь между типами и характеристик преобразования, изменяющие свойства типа.  
  
 Для поддержки признаки типов, вспомогательный класс, `integral_constant`, определяется. Он имеет специализации шаблона `true_type` и `false_type` формируют базовые классы для типов предикатов. Объект *предиката типа* — это шаблон, который принимает один или несколько аргументов. Если значение предиката типа равно *true*, он является открыто производным \(явно или косвенно\) от [true\_type](../Topic/true_type%20Typedef.md). Если значение предиката типа равно *false*, он является открыто производным \(явно или косвенно\) от [false\_type](../Topic/false_type%20Typedef.md).  
  
 Объект *модификатор типа* или *признака преобразования* — это шаблон, который принимает один или несколько аргументов шаблона и имеет один элемент `type`, являющийся синонимом для измененного типа.  
  
### Шаблоны псевдонимов  
 Для упрощения выражения типа признаков, [Шаблоны псевдонимов](../cpp/aliases-and-typedefs-cpp.md) для `typename some_trait<T>::type` указано, где « `some_trait`» — это имя класса шаблона. Например [add\_const](../Topic/add_const%20Class.md) содержит шаблон псевдонима для типа, `add_const_t`, определенный как:  
  
```cpp  
template<class T>  
    using add_const_t = typename add_const<T>::type;  
```  
  
|||||  
|-|-|-|-|  
|add\_const\_t|aligned\_storage\_t|make\_signed\_t|remove\_pointer\_t|  
|add\_cv\_t|aligned\_union\_t|make\_unsigned\_t|remove\_reference\_t|  
|add\_lvalue\_reference\_t|common\_type\_t|remove\_all\_extents\_t|remove\_volatile\_t|  
|add\_pointer\_t|conditional\_t|remove\_const\_t|result\_of\_t|  
|add\_rvalue\_reference\_t|decay\_t|remove\_cv\_t|underlying\_type\_t|  
|add\_volatile\_t|enable\_if\_t|remove\_extent\_t||  
  
### Классы  
 Вспомогательный класс и определения типов  
  
|||  
|-|-|  
|[integral\_constant](../standard-library/integral-constant-class-bool-constant-class.md)|Делает постоянным целым из типа и значения.|  
|[true\_type](../Topic/true_type%20Typedef.md)|Содержит целочисленную константу со значением true.|  
|[false\_type](../Topic/false_type%20Typedef.md)|Содержит целочисленную константу со значением false.|  
  
 Основной тип категории  
  
|||  
|-|-|  
|[is\_void](../standard-library/is-void-class.md)|Проверяет, является ли тип `void`.|  
|[is\_null\_pointer](../standard-library/is-null-pointer-class.md)|Проверяет, является ли тип `std::nullptr_t`.|  
|[is\_integral](../standard-library/is-integral-class.md)|Проверяет, является ли тип целочисленным.|  
|[is\_floating\_point](../standard-library/is-floating-point-class.md)|Проверяет, является ли тип вещественным \(с плавающей запятой\).|  
|[is\_array](../Topic/is_array%20Class.md)|Проверяет, является ли тип массивом.|  
|[is\_pointer](../standard-library/is-pointer-class.md)|Проверяет, является ли тип указателем.|  
|[is\_lvalue\_reference](../standard-library/is-lvalue-reference-class.md)|Проверяет, является ли тип ссылкой lvalue.|  
|[is\_rvalue\_reference](../Topic/is_rvalue_reference%20Class.md)|Проверяет, является ли тип ссылкой rvalue.|  
|[is\_member\_object\_pointer](../standard-library/is-member-object-pointer-class.md)|Проверяет, является ли тип указателем на объект\-член.|  
|[is\_member\_function\_pointer](../Topic/is_member_function_pointer%20Class.md)|Проверяет, является ли тип указателем на функцию\-член.|  
|[is\_enum](../standard-library/is-enum-class.md)|Проверяет, является ли тип перечислением.|  
|[is\_union](../standard-library/is-union-class.md)|Проверяет, является ли тип объединением.|  
|[is\_class](../standard-library/is-class-class.md)|Проверяет, является ли тип классом.|  
|[is\_function](../standard-library/is-function-class.md)|Проверяет, является ли тип типом функции.|  
  
 Составной тип категории  
  
|||  
|-|-|  
|[is\_reference](../Topic/is_reference%20Class.md)|Проверяет, является ли тип ссылкой.|  
|[is\_arithmetic](../Topic/is_arithmetic%20Class.md)|Проверяет, является ли тип арифметическим.|  
|[is\_fundamental](../standard-library/is-fundamental-class.md)|Проверяет, является ли тип `void` или арифметическим типом.|  
|[is\_object](../standard-library/is-object-class.md)|Проверяет, является ли тип типом объекта.|  
|[is\_scalar](../standard-library/is-scalar-class.md)|Проверяет, является ли тип скалярным.|  
|[is\_compound](../standard-library/is-compound-class.md)|Проверяет, является ли тип нескалярным.|  
|[is\_member\_pointer](../standard-library/is-member-pointer-class.md)|Проверяет, является ли тип указателем на член.|  
  
 Свойства типа  
  
|||  
|-|-|  
|[is\_const](../Topic/is_const%20Class.md)|Проверяет, является ли тип `const`.|  
|[is\_volatile](../standard-library/is-volatile-class.md)|Проверяет, является ли тип `volatile`.|  
|[is\_trivial](../Topic/is_trivial%20Class.md)|Проверяет, является ли тип тривиальным.|  
|[is\_trivially\_copyable](../standard-library/is-trivially-copyable-class.md)|Проверяет, является ли тип доступна для простого копирования.|  
|[is\_standard\_layout](../Topic/is_standard_layout%20Class.md)|Проверяет тип является стандартным макетом.|  
|[is\_pod](../standard-library/is-pod-class.md)|Проверяет, является ли тип типом POD.|  
|[is\_literal\_type](../standard-library/is-literal-type-class.md)|Проверяет, является ли тип может быть `constexpr` переменной, либо использоваться в `constexpr` функции.|  
|[is\_empty](../standard-library/is-empty-class.md)|Проверяет, является ли тип пустым классом.|  
|[is\_polymorphic](../Topic/is_polymorphic%20Class.md)|Проверяет, является ли тип полиморфный класс.|  
|[is\_abstract](../Topic/is_abstract%20Class.md)|Проверяет, является ли тип абстрактным классом.|  
|[is\_final](../standard-library/is-final-class.md)|Проверяет, является ли тип типом класса помечен `final`.|  
|[is\_signed](../Topic/is_signed%20Class.md)|Проверяет, является ли тип знаковым целочисленным типом.|  
|[is\_unsigned](../standard-library/is-unsigned-class.md)|Проверяет, является ли тип беззнаковым целочисленным типом.|  
|[is\_constructible](../standard-library/is-constructible-class.md)|Проверяет, является ли тип конструируемый с помощью указанным типам аргументов.|  
|[is\_default\_constructible](../Topic/is_default_constructible%20Class.md)|Проверяет, есть ли у типа конструктор по умолчанию.|  
|[is\_copy\_constructible](../standard-library/is-copy-constructible-class.md)|Проверяет, есть ли у типа конструктор копии.|  
|[is\_move\_constructible](../standard-library/is-move-constructible-class.md)|Проверяет, имеет ли тип конструктор перемещения.|  
|[is\_assignable](../standard-library/is-assignable-class.md)|Проверяет, является ли первый тип может быть присвоено значение второго типа.|  
|[is\_copy\_assignable](../standard-library/is-copy-assignable-class.md)|Проверяет, является ли тип можно назначить значение const ссылки типа.|  
|[is\_move\_assignable](../standard-library/is-move-assignable-class.md)|Проверяет, является ли ссылка rvalue типа можно назначить тип.|  
|[is\_destructible](../standard-library/is-destructible-class.md)|Проверяет, можно ли уничтожить тип.|  
|[is\_trivially\_constructible](../standard-library/is-trivially-constructible-class.md)|Проверяет, является ли тип использует нетривиального операций при создании с помощью указанных типов.|  
|[is\_trivially\_default\_constructible](../standard-library/is-trivially-default-constructible-class.md)|Проверяет, является ли тип использует нетривиального операций при создании по умолчанию.|  
|[is\_trivially\_copy\_constructible](../standard-library/is-trivially-copy-constructible-class.md)|Проверяет, является ли тип использует нетривиального операций при создании копии.|  
|[is\_trivially\_move\_constructible](../standard-library/is-trivially-move-constructible-class.md)|Проверяет, является ли тип использует нетривиального операций при создании перемещения.|  
|[is\_trivially\_assignable](../Topic/is_trivially_assignable%20Class.md)|Проверяет, является ли типы могут быть присвоены и без того нетривиальные операции не использует назначения.|  
|[is\_trivially\_copy\_assignable](../standard-library/is-trivially-copy-assignable-class.md)|Проверяет ли тип — может быть назначен копирования и присваивания использует не нетривиальные операции.|  
|[is\_trivially\_move\_assignable](../standard-library/is-trivially-move-assignable-class.md)|Проверяет ли тип — может быть назначен перемещения и присваивания использует не нетривиальные операции.|  
|[is\_trivially\_destructible](../standard-library/is-trivially-destructible-class.md)|Проверяет, является ли тип разрушаемых и деструктор использует не нетривиальные операции.|  
|[is\_nothrow\_constructible](../standard-library/is-nothrow-constructible-class.md)|Проверяет, является ли тип конструируемый, известны не будет выдавать при создании с помощью указанных типов.|  
|[is\_nothrow\_default\_constructible](../standard-library/is-nothrow-default-constructible-class.md)|Является ли тип тестов по умолчанию конструируемый и известные не будет выдавать при создании по умолчанию.|  
|[is\_nothrow\_copy\_constructible](../standard-library/is-nothrow-copy-constructible-class.md)|Проверяет, является ли тип является копией конструируемый и конструктор копии известен не исключение.|  
|[is\_nothrow\_move\_constructible](../standard-library/is-nothrow-move-constructible-class.md)|Проверяет, является ли тип является перемещение конструируемый и не будет выдавать известен конструктор перемещения.|  
|[is\_nothrow\_assignable](../standard-library/is-nothrow-assignable-class.md)|Проверяет, является ли тип назначается, используя указанный тип и не будет выдавать известен назначения.|  
|[is\_nothrow\_copy\_assignable](../Topic/is_nothrow_copy_assignable%20Class.md)|Проверяет, является ли тип — копирования может быть назначен и не будет выдавать известен назначения.|  
|[is\_nothrow\_move\_assignable](../standard-library/is-nothrow-move-assignable-class.md)|Проверяет, является ли типом является перемещение может быть назначен и не будет выдавать известен назначения.|  
|[is\_nothrow\_destructible](../standard-library/is-nothrow-destructible-class.md)|Проверяет, является ли тип разрушаемых и не будет выдавать известен деструктор.|  
|[has\_virtual\_destructor](http://msdn.microsoft.com/ru-ru/c0f85f0b-c63c-410d-a046-72eeaf44f7eb)|Проверяет, есть ли у типа виртуальный деструктор.|  
  
 Тип свойства запросов  
  
|||  
|-|-|  
|[alignment\_of](../standard-library/alignment-of-class.md)|Получает выравнивание типа.|  
|[rank](../Topic/rank%20Class.md)|Получает количество измерений массива.|  
|[extent](../standard-library/extent-class.md)|Возвращает количество элементов в измерении указанного массива.|  
  
 Тип отношений  
  
|||  
|-|-|  
|[is\_same](../standard-library/is-same-class.md)|Определяет, совпадают ли два типа.|  
|[is\_base\_of](../standard-library/is-base-of-class.md)|Проверяет, является ли один тип базовым для другого.|  
|[is\_convertible](../standard-library/is-convertible-class.md)|Проверяет, можно ли преобразовать один тип в другой.|  
  
 Изменения const или volatile  
  
|||  
|-|-|  
|[add\_const](../Topic/add_const%20Class.md)|Создает `const` тип из типа.|  
|[add\_volatile](../standard-library/add-volatile-class.md)|Создает `volatile` тип из типа.|  
|[add\_cv](../standard-library/add-cv-class.md)|Создает `const``volatile` тип из типа.|  
|[remove\_const](../standard-library/remove-const-class.md)|Создает неконстантный тип из типа.|  
|[remove\_volatile](../Topic/remove_volatile%20Class.md)|Создает долговременный тип из типа.|  
|[remove\_cv](../standard-library/remove-cv-class.md)|Создает неконстантный долговременный тип из типа.|  
  
 Изменения ссылок  
  
|||  
|-|-|  
|[add\_lvalue\_reference](../standard-library/add-lvalue-reference-class.md)|Создает ссылку на тип из типа.|  
|[add\_rvalue\_reference](../standard-library/add-rvalue-reference-class.md)|Создает ссылку rvalue на тип из типа|  
|[remove\_reference](../standard-library/remove-reference-class.md)|Создает из типа не ссылочный тип.|  
  
 Знак изменения  
  
|||  
|-|-|  
|[make\_signed](../standard-library/make-signed-class.md)|Создает тип, если подпись или наименьший тип данных со знаком больше или равна емкости для ввода.|  
|[make\_unsigned](../standard-library/make-unsigned-class.md)|Выводит случае тип или наименьший беззнаковый тип больше или равен размеру типа.|  
  
 Изменения массива  
  
|||  
|-|-|  
|[remove\_all\_extents](../standard-library/remove-all-extents-class.md)|Создает тип отличных от массива типа массива.|  
|[remove\_extent](../standard-library/remove-extent-class.md)|Создает тип элемента типа массива.|  
  
 Указатель изменения  
  
|||  
|-|-|  
|[add\_pointer](../standard-library/add-pointer-class.md)|Создает указатель на тип из типа.|  
|[remove\_pointer](../Topic/remove_pointer%20Class.md)|Создает тип из указателя на тип.|  
  
 Другие преобразования  
  
|||  
|-|-|  
|[aligned\_storage](../standard-library/aligned-storage-class.md)|Выделяет неинициализированную память для выровненного типа.|  
|[aligned\_union](../Topic/aligned_union%20Class.md)|Выделяет неинициализированную память для выровненного объединения с нетривиальным конструктором или деструктором.|  
|[common\_type](../standard-library/common-type-class.md)|Создает общий тип всех типов параметров пакета.|  
|[conditional](../standard-library/conditional-class.md)|Если условие истинно, выводятся первого указанного типа, в противном случае второго заданного типа.|  
|[decay](../standard-library/decay-class.md)|Создает тип, как передаются по значению. Создает нессылочный, неконстантный или долговременный тип либо указатель на тип.|  
|[enable\_if](../Topic/enable_if%20Class.md)|Если условие истинно, выводятся указанного типа, в противном случае нет типа.|  
|[result\_of](../standard-library/result-of-class1.md)|Определяет возвращаемый тип вызываемой типа, который принимает указанным типам аргументов.|  
|[underlying\_type](../standard-library/underlying-type-class.md)|Создает базового целочисленного типа для типа перечисления.|  
  
## См. также  
 [\<functional\>](../standard-library/functional.md)