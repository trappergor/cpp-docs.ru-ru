---
title: "Класс codecvt | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- xlocale/std::codecvt
- xlocale/std::codecvt::extern_type
- xlocale/std::codecvt::intern_type
- xlocale/std::codecvt::state_type
- xlocale/std::codecvt::always_noconv
- xlocale/std::codecvt::do_always_noconv
- xlocale/std::codecvt::do_encoding
- xlocale/std::codecvt::do_in
- xlocale/std::codecvt::do_length
- xlocale/std::codecvt::do_max_length
- xlocale/std::codecvt::do_out
- xlocale/std::codecvt::do_unshift
- xlocale/std::codecvt::encoding
- xlocale/std::codecvt::in
- xlocale/std::codecvt::length
- xlocale/std::codecvt::max_length
- xlocale/std::codecvt::out
- xlocale/std::codecvt::unshift
dev_langs:
- C++
helpviewer_keywords:
- std::codecvt [C++]
- std::codecvt [C++], extern_type
- std::codecvt [C++], intern_type
- std::codecvt [C++], state_type
- std::codecvt [C++], always_noconv
- std::codecvt [C++], do_always_noconv
- std::codecvt [C++], do_encoding
- std::codecvt [C++], do_in
- std::codecvt [C++], do_length
- std::codecvt [C++], do_max_length
- std::codecvt [C++], do_out
- std::codecvt [C++], do_unshift
- std::codecvt [C++], encoding
- std::codecvt [C++], in
- std::codecvt [C++], length
- std::codecvt [C++], max_length
- std::codecvt [C++], out
- std::codecvt [C++], unshift
ms.assetid: 37d3efa1-2b7f-42b6-b04f-7a972c8c2c86
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: b456472fc28b473da29169acb899a1a8a142c095
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/23/2018
---
# <a name="codecvt-class"></a>Класс codecvt
Шаблонный класс, описывающий объект, который можно использовать как аспект языкового стандарта. Он может управлять преобразованиями между последовательностями значений, используемых для кодирования символов внутри программы, и последовательностями значений, используемых для кодирования символы вне программы.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
template <class CharType, class Byte, class StateType>  
class codecvt : public locale::facet, codecvt_base;  
```  
  
#### <a name="parameters"></a>Параметры  
 `CharType`  
 Тип, используемый внутри программы для кодирования символов.  
  
 `Byte`  
 Тип, используемый для кодирования символов вне программы.  
  
 `StateType`  
 Тип, который можно использовать для представления промежуточных состояний преобразования между внутренними и внешними типами представлений символов.  
  
## <a name="remarks"></a>Примечания  
 Класс шаблона, описывающий объект, который можно использовать как [аспект языкового стандарта](../standard-library/locale-class.md#facet_class) для управления преобразованиями между последовательностью значений типа `CharType` и последовательностью значений типа `Byte`. Класс `StateType` характеризует преобразование, а объект класса `StateType` сохраняет все необходимые сведения о состоянии во время преобразования.  
  
 Внутренняя кодировка использует представление с фиксированным числом байтов на один знак, обычно либо тип `char`, либо тип `wchar_t`.  
  
 Как и в случае любого другого аспекта языкового стандарта, начальное сохраненное значение статического `id` объекта равно нулю. Первая попытка получить доступ к сохраненному значению сохранит уникальное положительное значение в `id`.  
  
 Шаблонные версии [do_in](#do_in) и [do_out](#do_out) всегда возвращают `codecvt_base::noconv`.  
  
 Стандартная библиотека C++ определяет несколько явных специализаций:  
  
 `template<>`  
  
 `codecvt<wchar_t, char, mbstate_t>`  
  
 выполняет преобразование между последовательностями `wchar_t` и `char`.  
  
 `template<>`  
  
 `codecvt<char16_t, char, mbstate_t>`  
  
 выполняет преобразование между последовательностями `char16_t` в кодировке UTF-16 и последовательностями `char` в кодировке UTF-8.  
  
 `template<>`  
  
 `codecvt<char32_t, char, mbstate_t>`  
  
 выполняет преобразование между последовательностями `char32_t` в кодировке UTF-32 (UCS-4) и последовательностями `char` в кодировке UTF-8.  
  
### <a name="constructors"></a>Конструкторы  
  
|||  
|-|-|  
|[codecvt](#codecvt)|Конструктор для объектов класса `codecvt`, который служит в качестве аспекта языкового стандарта для обработки преобразований.|  
  
### <a name="typedefs"></a>Определения типов  
  
|||  
|-|-|  
|[extern_type](#extern_type)|Тип символа, используемый для внешних представлений.|  
|[intern_type](#intern_type)|Тип символа, используемый для внутренних представлений.|  
|[state_type](#state_type)|Тип символа, который используется для представления промежуточных состояний во время преобразований между внутренними и внешними представлениями.|  
  
### <a name="member-functions"></a>Функции-члены  
  
|||  
|-|-|  
|[always_noconv](#always_noconv)|Проверяет, не требуется ли выполнит преобразования.|  
|[do_always_noconv](#do_always_noconv)|Виртуальная функция, вызываемая проверки того, не требуется ли выполнить преобразования.|  
|[do_encoding](#do_encoding)|Виртуальная функция, проверяющая, зависит ли кодировка потока `Byte` от состояния, является ли соотношение между использованными объектами `Byte` и полученными объектами `CharType` константой, и, если это так, определяет значение этого соотношения.|  
|[do_in](#do_in)|Виртуальная функция, вызываемая для преобразования последовательности внутренних `Byte` в последовательность внешних `CharType`.|  
|[do_length](#do_length)|Виртуальная функция, которая определяет, сколько объектов `Byte` из заданной последовательности внешних объектов `Byte` создают не более указанного количества внутренних объектов `CharType`, и возвращает это число объектов `Byte`.|  
|[do_max_length](#do_max_length)|Виртуальная функция, возвращающая максимальное число внешних байтов, необходимых для создания одного внутреннего `CharType`.|  
|[do_out](#do_out)|Виртуальная функция, вызываемая для преобразования последовательности внутренних `CharType` в последовательность внешних байтов.|  
|[do_unshift](#do_unshift)|Виртуальная функция, вызываемая для предоставления объектов `Byte`, необходимых при зависимом от состояния преобразовании для завершения последнего символа в последовательности объектов `Byte`.|  
|[encoding](#encoding)|Проверяет, зависит ли кодировка потока `Byte` от состояния, является ли соотношение между использованными объектами `Byte` и полученными объектами `CharType` константой, и, если это так, определяет значение этого соотношения.|  
|[in](#in)|Преобразует внешнее представление последовательности объектов `Byte` во внутреннее представление последовательности объектов `CharType`.|  
|[length](#length)|Определяет, сколько объектов `Byte` из заданной последовательности внешних объектов `Byte` создают не более указанного количества внутренних объектов `CharType`, и возвращает это число объектов `Byte`.|  
|[max_length](#max_length)|Возвращает максимальное число внешних объектов `Byte`, необходимых для создания одного внутреннего `CharType`.|  
|[out](#out)|Преобразует последовательность внутренних объектов `CharType` в последовательность внешних объектов `Byte`.|  
|[unshift](#unshift)|Предоставляет внешние `Byte`, необходимые при зависимом от состояния преобразовании для завершения последнего символа в последовательности объектов `Byte`.|  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** \<locale>  
  
 **Пространство имен:** std  
  
##  <a name="always_noconv"></a>  codecvt::always_noconv  
 Проверяет, не требуется ли выполнит преобразования.  
  
```  
bool always_noconv() const throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Логическое значение, равное **true**, если не требуется никаких преобразований, или **false**, если нужно выполнить хотя бы одно преобразование.  
  
### <a name="remarks"></a>Примечания  
 Функция-член возвращает [do_always_noconv](#do_always_noconv).  
  
### <a name="example"></a>Пример  
  
```cpp  
// codecvt_always_noconv.cpp  
// compile with: /EHsc  
#include <locale>  
#include <iostream>  
using namespace std;  
  
int main( )     
{  
   locale loc ( "German_Germany" );  
   bool result1 = use_facet<codecvt<char, char, mbstate_t> >   
      ( loc ).always_noconv( );  
  
   if ( result1 )  
      cout << "No conversion is needed." << endl;  
   else  
      cout << "At least one conversion is required." << endl;  
  
   bool result2 = use_facet<codecvt<wchar_t, char, mbstate_t> >   
      ( loc ).always_noconv( );  
  
   if ( result2 )  
      cout << "No conversion is needed." << endl;  
   else  
      cout << "At least one conversion is required." << endl;  
}  
```  
  
```Output  
No conversion is needed.  
At least one conversion is required.  
```  
  
##  <a name="codecvt"></a>  codecvt::codecvt  
 Конструктор для объектов класса codecvt, который служит в качестве аспекта языкового стандарта для обработки преобразований.  
  
```  
explicit codecvt(size_t _Refs = 0);
```  
  
### <a name="parameters"></a>Параметры  
 `_Refs`  
 Целочисленное значение, используемое для указания типа управления памятью для объекта.  
  
### <a name="remarks"></a>Примечания  
 Возможные значения параметра `_Refs` и их важность:  
  
-   0: время существования объекта управляется языковыми стандартами, которые его содержат.  
  
-   1: время существования объекта должно управляться вручную.  
  
-   \> 1: эти значения не определены.  
  
 Конструктор инициализирует его `locale::facet` базовый объект с **locale::**[аспекта](../standard-library/locale-class.md#facet_class)(`_Refs`).  
  
##  <a name="do_always_noconv"></a>  codecvt::do_always_noconv  
 Виртуальная функция, вызываемая проверки того, не требуется ли выполнить преобразования.  
  
```  
virtual bool do_always_noconv() const throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Защищенная виртуальная функция-член возвращает **true** только тогда, когда каждый вызов [do_in](#do_in) или [do_out](#do_out) возвращает **noconv**.  
  
 Версия шаблона всегда возвращает **true**.  
  
### <a name="example"></a>Пример  
  См. пример для [always_noconv](#always_noconv), в котором вызывается `do_always_noconv`.  
  
##  <a name="do_encoding"></a>  codecvt::do_encoding  
 Виртуальная функция, проверяющая, зависит ли кодировка потока **Byte** от состояния, является ли соотношение между использованными объектами **Byte** и полученными объектами **CharType** константой, и, если это так, определяет значение этого соотношения.  
  
```  
virtual int do_encoding() const throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Защищенная функция-член возвращает:  
  
-   значение -1, если кодировка последовательностей типа `extern_type` зависит от состояния.  
  
-   0, если кодировка включает последовательности переменной длины;  
  
- *N*, если кодировка включает только последовательности длиной *N*.  
  
### <a name="example"></a>Пример  
  См. пример для [encoding](#encoding), в котором вызывается `do_encoding`.  
  
##  <a name="do_in"></a>  codecvt::do_in  
 Виртуальная функция, вызываемая для преобразования последовательности внешних объектов **Byte** в последовательность внутренних объектов **CharType**.  
  
```  
virtual result do_in(
    StateType& _State,  
    const Byte* first1,   
    const Byte* last1,   
    const Byte*& next1,  
    CharType* first2,  
    CharType* last2,  
    CharType*& next2,) const;
```  
  
### <a name="parameters"></a>Параметры  
 `_State`  
 Состояние преобразования, которое поддерживается между вызовами функции-члена.  
  
 `first1`  
 Указатель на начало последовательности для преобразования.  
  
 `last1`  
 Указатель на конец последовательности для преобразования.  
  
 `next1`  
 Указатель за пределами преобразованной последовательности для первого непреобразованного символа.  
  
 `first2`  
 Указатель на начало преобразованной последовательности.  
  
 `last2`  
 Указатель на конец преобразованной последовательности.  
  
 `next2`  
 Указатель на **CharType**, который получает первый неизмененный символ в целевой последовательности после преобразования последнего **CharType**.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращаемое значение, которое указывает успех, частичный успех или сбой операции. Функция возвращает:  
  
- **codecvt_base::Error**, если исходная последовательность имеет неправильную форму;  
  
- `codecvt_base::noconv`, если функция не выполняет преобразование;  
  
- **codecvt_base::ok**, если преобразование выполнено успешно;  
  
- **codecvt_base::partial**, если недостаточно источника или если целевой объект недостаточно велик для успешного преобразования.  
  
### <a name="remarks"></a>Примечания  
 Объект `_State` должен представлять начальное состояние преобразования в начале новой исходной последовательности. Функция изменяет это сохраненное значение так, чтобы отразить текущее состояние успешного преобразования. В противном случае сохраненное значение будет незаданным.  
  
### <a name="example"></a>Пример  
  См. пример для [in](#in), в котором вызывается `do_in`.  
  
##  <a name="do_length"></a>  codecvt::do_length  
 Виртуальная функция, которая определяет, сколько объектов **Byte** из заданной последовательности внешних объектов **Byte** создают не более указанного количества внутренних объектов **CharType**, и возвращает это число объектов **Byte**.  
  
```  
virtual int do_length(
    const StateType& _State,  
    const Byte* first1,   
    const Byte* last1,  
    size_t _Len2) const;
```  
  
### <a name="parameters"></a>Параметры  
 `_State`  
 Состояние преобразования, которое поддерживается между вызовами функции-члена.  
  
 `first1`  
 Указатель на начало внешней последовательности.  
  
 `last1`  
 Указатель на конец внешней последовательности.  
  
 `_Len2`  
 Максимальное число объектов **Byte**, которое может возвратить функция-член.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Целое число, представляющее максимальное число преобразований, не превышающее значение `_Len2`, заданное внешней исходной последовательностью в [`first1`, `last1`).  
  
### <a name="remarks"></a>Примечания  
 Защищенная виртуальная функция-член эффективно вызывает `do_in`(`_State`, `first1`, `last1`, `next1`, `_Buf`, `_Buf`  +  `_Len2`, `next2`) для `_State` (копии состояния), некоторый буфер `_Buf`, а также указатели `next1` и `next2`.  
  
 Затем она возвращает `next2`  -  **buf**. Тем самым она вычисляет максимальное число преобразований, не превышающее значение `_Len2`, заданное исходной последовательностью в [`first1`, `last1`).  
  
 Версия шаблона всегда возвращает меньший из `last1`  -  `first1` и `_Len2`.  
  
### <a name="example"></a>Пример  
  См. пример для [length](#length), в котором вызывается **do_length**.  
  
##  <a name="do_max_length"></a>  codecvt::do_max_length  
 Виртуальная функция, возвращающая максимальное число внешних объектов **Byte**, необходимых для создания одного внутреннего **CharType**.  
  
```  
virtual int do_max_length() const throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Максимальное число объектов **Byte**, необходимых для создания одного **CharType**.  
  
### <a name="remarks"></a>Примечания  
 Защищенная виртуальная функция-член возвращает наибольшее допустимое значение, которое может быть возвращено [do_length](#do_length)(`first1`, `last1`, 1) для произвольных допустимых значений `first1` и `last1`.  
  
### <a name="example"></a>Пример  
  См. пример для [max_length](#max_length), в котором вызывается `do_max_length`.  
  
##  <a name="do_out"></a>  codecvt::do_out  
 Виртуальная функция, вызываемая для преобразования последовательности внутренних объектов **CharType** в последовательность внешних объектов **Byte**.  
  
```  
virtual result do_out(
    StateType& _State,  
    const CharType* first1,   
    const CharType* last1,  
    const CharType*& next1,  
    Byte* first2,   
    Byte* last2,   
    Byte*& next2) const;
```  
  
### <a name="parameters"></a>Параметры  
 `_State`  
 Состояние преобразования, которое поддерживается между вызовами функции-члена.  
  
 `first1`  
 Указатель на начало последовательности для преобразования.  
  
 `last1`  
 Указатель на конец последовательности для преобразования.  
  
 `next1`  
 Ссылка на указатель на первый непреобразованный **CharType** после последнего преобразованного **CharType**.  
  
 `first2`  
 Указатель на начало преобразованной последовательности.  
  
 `last2`  
 Указатель на конец преобразованной последовательности.  
  
 `next2`  
 Ссылка на указатель на первый непреобразованный **Byte** после последнего преобразованного **Byte**.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Функция возвращает:  
  
- **codecvt_base::Error**, если исходная последовательность имеет неправильную форму;  
  
- `codecvt_base::noconv`, если функция не выполняет преобразование;  
  
- **codecvt_base::ok**, если преобразование выполнено успешно;  
  
- **codecvt_base::partial**, если недостаточно источника или если целевой объект недостаточно велик для успешного преобразования.  
  
### <a name="remarks"></a>Примечания  
 Объект `_State` должен представлять начальное состояние преобразования в начале новой исходной последовательности. Функция изменяет это сохраненное значение так, чтобы отразить текущее состояние успешного преобразования. В противном случае сохраненное значение будет незаданным.  
  
### <a name="example"></a>Пример  
  См. пример для [out](#out), в котором вызывается `do_out`.  
  
##  <a name="do_unshift"></a>  codecvt::do_unshift  
 Виртуальная функция, вызываемая для предоставления объектов **Byte**, необходимых при зависимом от состояния преобразовании для завершения последнего символа в последовательности объектов **Byte**.  
  
```  
virtual result do_unshift(
    StateType& _State,  
    Byte* first2,   
    Byte* last2,   
    Byte*& next2) const;
```  
  
### <a name="parameters"></a>Параметры  
 `_State`  
 Состояние преобразования, которое поддерживается между вызовами функции-члена.  
  
 `first2`  
 Указатель первой позиции в целевом диапазоне.  
  
 `last2`  
 Указатель последней позиции в целевом диапазоне.  
  
 `next2`  
 Указатель на первый неизмененный элемент в целевой последовательности.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Функция возвращает:  
  
- **codecvt_base::Error**, если _ *State* представляет недопустимое состояние;  
  
- `codecvt_base::noconv`, если функция не выполняет преобразование;  
  
- **codecvt_base::ok**, если преобразование выполнено успешно;  
  
- **codecvt_base::partial**, если целевой объект недостаточно велик для успешного преобразования.  
  
### <a name="remarks"></a>Примечания  
 Защищенная виртуальная функция-член пытается преобразовать исходный элемент **CharType**(0) в целевую последовательность, которая хранится в [`first2`, `last2`), кроме завершающего элемента **Byte**(0). Она всегда хранит в `next2` указатель на первый неизмененный элемент в целевой последовательности.  
  
 Объект _ *State* должен представлять начальное состояние преобразования в начале новой исходной последовательности. Функция изменяет это сохраненное значение так, чтобы отразить текущее состояние успешного преобразования. Как правило, преобразование исходного элемента **CharType**(0) оставляет текущее состояние в начальном состоянии преобразования.  
  
### <a name="example"></a>Пример  
  См. пример для [unshift](#unshift), в котором вызывается `do_unshift`.  
  
##  <a name="encoding"></a>  codecvt::encoding  
 Проверяет, зависит ли кодировка потока **Byte** от состояния, является ли соотношение между использованными объектами **Byte** и полученными объектами **CharType** константой, и, если это так, определяет значение этого соотношения.  
  
```  
int encoding() const throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Если возвращаемое значение положительное, то число символов **Byte**, необходимых для получения символа **CharType**, является константой.  
  
 Защищенная функция-член возвращает:  
  
-   значение -1, если кодировка последовательностей типа `extern_type` зависит от состояния.  
  
-   0, если кодировка включает последовательности переменной длины;  
  
- *N*, если кодировка включает только последовательности длиной *N*.  
  
### <a name="remarks"></a>Примечания  
 Функция-член возвращает [do_encoding](#do_encoding).  
  
### <a name="example"></a>Пример  
  
```cpp  
// codecvt_encoding.cpp  
// compile with: /EHsc  
#include <locale>  
#include <iostream>  
using namespace std;  
  
int main( )     
{  
   locale loc ( "German_Germany" );  
   int result1 = use_facet<codecvt<char, char, mbstate_t> > ( loc ).encoding ( );  
   cout << result1 << endl;  
   result1 = use_facet<codecvt<wchar_t, char, mbstate_t> > ( loc ).encoding( );  
   cout << result1 << endl;  
   result1 = use_facet<codecvt<char, wchar_t, mbstate_t> > ( loc ).encoding( );  
   cout << result1 << endl;  
}  
```  
  
```Output  
1  
1  
1  
```  
  
##  <a name="extern_type"></a>  codecvt::extern_type  
 Тип символа, используемый для внешних представлений.  
  
```  
typedef Byte extern_type;  
```  
  
### <a name="remarks"></a>Примечания  
 Этот тип является синонимом для параметра-шаблона **Byte**.  
  
##  <a name="in"></a>  codecvt::in  
 Преобразует внешнее представление последовательности объектов **Byte** во внутреннее представление последовательности объектов **CharType**.  
  
```  
result in(
    StateType& _State,  
    const Byte* first1,   
    const Byte* last1,   
    const Byte*& next1,  
    CharType* first2,  
    CharType* last2,  
    CharType*& next2,) const;
```  
  
### <a name="parameters"></a>Параметры  
 `_State`  
 Состояние преобразования, которое поддерживается между вызовами функции-члена.  
  
 `first1`  
 Указатель на начало последовательности для преобразования.  
  
 `last1`  
 Указатель на конец последовательности для преобразования.  
  
 `next1`  
 Указатель за пределами преобразованной последовательности для первого непреобразованного символа.  
  
 `first2`  
 Указатель на начало преобразованной последовательности.  
  
 `last2`  
 Указатель на конец преобразованной последовательности.  
  
 `next2`  
 Указатель на **CharType**, который получает первый неизмененный символ в целевой последовательности после преобразования последнего **CharType**.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращаемое значение, которое указывает успех, частичный успех или сбой операции. Функция возвращает:  
  
- **codecvt_base::Error**, если исходная последовательность имеет неправильную форму;  
  
- `codecvt_base::noconv`, если функция не выполняет преобразование;  
  
- **codecvt_base::ok**, если преобразование выполнено успешно;  
  
- **codecvt_base::partial**, если недостаточно источника или если целевой объект недостаточно велик для успешного преобразования.  
  
### <a name="remarks"></a>Примечания  
 Объект `_State` должен представлять начальное состояние преобразования в начале новой исходной последовательности. Функция изменяет это сохраненное значение так, чтобы отразить текущее состояние успешного преобразования. После частичного преобразования `_State` необходимо задать так, чтобы разрешить возобновление преобразования при поступлении новых символов.  
  
 Функция-член возвращает [do_in](#do_in)(`_State`, _ *First1, last1, next1, First2, _Llast2, next2*).  
  
### <a name="example"></a>Пример  
  
```cpp  
// codecvt_in.cpp  
// compile with: /EHsc  
#define _INTL  
#include <locale>  
#include <iostream>  
using namespace std;  
#define LEN 90  
int main( )     
{  
   char* pszExt = "This is the string to be converted!";  
   wchar_t pwszInt [LEN+1];  
   memset(&pwszInt[0], 0, (sizeof(wchar_t))*(LEN+1));  
   const char* pszNext;  
   wchar_t* pwszNext;  
   mbstate_t state = {0};  
   locale loc("C");//English_Britain");//German_Germany  
   int res = use_facet<codecvt<wchar_t, char, mbstate_t> >  
     ( loc ).in( state,  
          pszExt, &pszExt[strlen(pszExt)], pszNext,  
          pwszInt, &pwszInt[strlen(pszExt)], pwszNext );  
   pwszInt[strlen(pszExt)] = 0;  
   wcout << ( (res!=codecvt_base::error)  L"It worked! " : L"It didn't work! " )  
   << L"The converted string is:\n ["  
   << &pwszInt[0]  
   << L"]" << endl;  
   exit(-1);  
}  
```  
  
```Output  
It worked! The converted string is:  
 [This is the string to be converted!]  
```  
  
##  <a name="intern_type"></a>  codecvt::intern_type  
 Тип символа, используемый для внутренних представлений.  
  
```  
typedef CharType intern_type;  
```  
  
### <a name="remarks"></a>Примечания  
 Тип является синонимом для параметра-шаблона **CharType**.  
  
##  <a name="length"></a>  codecvt::length  
 Определяет, сколько объектов **Byte** из заданной последовательности внешних объектов **Byte** создают не более указанного количества внутренних объектов **CharType**, и возвращает это число объектов **Byte**.  
  
```  
int length(
    const StateType& _State,  
    const Byte* first1,   
    const Byte* last1,  
    size_t _Len2) const;
```  
  
### <a name="parameters"></a>Параметры  
 `_State`  
 Состояние преобразования, которое поддерживается между вызовами функции-члена.  
  
 `first1`  
 Указатель на начало внешней последовательности.  
  
 `last1`  
 Указатель на конец внешней последовательности.  
  
 `_Len2`  
 Максимальное число объектов Byte, которое может возвратить функция-член.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Целое число, представляющее максимальное число преобразований, не превышающее значение `_Len2`, заданное внешней исходной последовательностью в [`first1`, `last1`).  
  
### <a name="remarks"></a>Примечания  
 Функция-член возвращает [do_length](#do_length)(*_State first1*, `last1`, `_Len2`).  
  
### <a name="example"></a>Пример  
  
```cpp  
// codecvt_length.cpp  
// compile with: /EHsc  
#define _INTL  
#include <locale>  
#include <iostream>  
using namespace std;  
#define LEN 90  
int main( )     
{  
   char* pszExt = "This is the string whose length is to be measured!";  
   mbstate_t state = {0};  
   locale loc("C");//English_Britain");//German_Germany  
   int res = use_facet<codecvt<wchar_t, char, mbstate_t> >  
     ( loc ).length( state,  
          pszExt, &pszExt[strlen(pszExt)], LEN );  
   cout << "The length of the string is: ";  
   wcout << res;  
   cout << "." << endl;  
   exit(-1);  
}  
```  
  
```Output  
The length of the string is: 50.  
```  
  
##  <a name="max_length"></a>  codecvt::max_length  
 Возвращает максимальное число внешних объектов **Byte**, необходимых для создания одного внутреннего объекта **CharType**.  
  
```  
int max_length() const throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Максимальное число объектов **Byte**, необходимых для создания одного **CharType**.  
  
### <a name="remarks"></a>Примечания  
 Функция-член возвращает [do_max_length](#do_max_length).  
  
### <a name="example"></a>Пример  
  
```cpp  
// codecvt_max_length.cpp  
// compile with: /EHsc  
#define _INTL  
#include <locale>  
#include <iostream>  
using namespace std;  
  
int main( )     
{  
   locale loc( "C");//English_Britain" );//German_Germany  
   int res = use_facet<codecvt<char, char, mbstate_t> >  
     ( loc ).max_length( );  
   wcout << res << endl;  
}  
```  
  
```Output  
1  
```  
  
##  <a name="out"></a>  codecvt::out  
 Преобразует последовательность внутренних объектов **CharType** в последовательность внешних объектов **Byte**.  
  
```  
result out(
    StateType& _State,  
    const CharType* first1,   
    const CharType* last1,  
    const CharType*& next1,  
    Byte* first2,   
    Byte* last2,   
    Byte*& next2) const;
```  
  
### <a name="parameters"></a>Параметры  
 `_State`  
 Состояние преобразования, которое поддерживается между вызовами функции-члена.  
  
 `first1`  
 Указатель на начало последовательности для преобразования.  
  
 `last1`  
 Указатель на конец последовательности для преобразования.  
  
 `next1`  
 Ссылка на указатель на первый непреобразованный **CharType** после последнего преобразованного **CharType**.  
  
 `first2`  
 Указатель на начало преобразованной последовательности.  
  
 `last2`  
 Указатель на конец преобразованной последовательности.  
  
 `next2`  
 Ссылка на указатель на первый непреобразованный **Byte** после последнего преобразованного **Byte**.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Функция-член возвращает [do_out](#do_out)(`_State`, `first1`, `last1`, `next1`, `first2`, `last2`, `next2`).  
  
### <a name="remarks"></a>Примечания  
 Дополнительные сведения см. в описании [codecvt::do_out](#do_out).  
  
### <a name="example"></a>Пример  
  
```cpp  
// codecvt_out.cpp  
// compile with: /EHsc  
#define _INTL  
#include <locale>  
#include <iostream>  
#include <wchar.h>  
using namespace std;  
#define LEN 90  
int main( )     
{  
   char pszExt[LEN+1];  
   wchar_t *pwszInt = L"This is the wchar_t string to be converted.";  
   memset( &pszExt[0], 0, ( sizeof( char ) )*( LEN+1 ) );  
   char* pszNext;  
   const wchar_t* pwszNext;  
   mbstate_t state;  
   locale loc("C");//English_Britain");//German_Germany  
   int res = use_facet<codecvt<wchar_t, char, mbstate_t> >  
      ( loc ).out( state,  
      pwszInt, &pwszInt[wcslen( pwszInt )], pwszNext ,  
      pszExt, &pszExt[wcslen( pwszInt )], pszNext );  
   pszExt[wcslen( pwszInt )] = 0;  
   cout << ( ( res!=codecvt_base::error )  "It worked: " : "It didn't work: " )  
   << "The converted string is:\n ["  
   << &pszExt[0]  
   << "]" << endl;  
}  
```  
  
```Output  
It worked: The converted string is:  
 [This is the wchar_t string to be converted.]  
```  
  
##  <a name="state_type"></a>  codecvt::state_type  
 Тип символа, который используется для представления промежуточных состояний во время преобразований между внутренними и внешними представлениями.  
  
```  
typedef StateType state_type;  
```  
  
### <a name="remarks"></a>Примечания  
 Этот тип является синонимом для параметра шаблона **StateType**.  
  
##  <a name="unshift"></a>  codecvt::unshift  
 Предоставляет объекты **Byte**, необходимые при зависимом от состояния преобразовании для завершения последнего символа в последовательности объектов**Byte**.  
  
```  
result unshift(
    StateType& _State,  
    Byte* first2,   
    Byte* last2,   
    Byte*& next2) const;
```  
  
### <a name="parameters"></a>Параметры  
 `_State`  
 Состояние преобразования, которое поддерживается между вызовами функции-члена.  
  
 `first2`  
 Указатель первой позиции в целевом диапазоне.  
  
 `last2`  
 Указатель последней позиции в целевом диапазоне.  
  
 `next2`  
 Указатель на первый неизмененный элемент в целевой последовательности.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Функция возвращает:  
  
- **codecvt_base::Error**, если state представляет недопустимое состояние;  
  
- `codecvt_base::noconv`, если функция не выполняет преобразование;  
  
- **codecvt_base::ok**, если преобразование выполнено успешно;  
  
- **codecvt_base::partial**, если целевой объект недостаточно велик для успешного преобразования.  
  
### <a name="remarks"></a>Примечания  
 Защищенная виртуальная функция-член пытается преобразовать исходный элемент **CharType**(0) в целевую последовательность, которая хранится в [`first2`, `last2`), кроме завершающего элемента **Byte**(0). Она всегда хранит в `next2` указатель на первый неизмененный элемент в целевой последовательности.  
  
 Объект `_State` должен представлять начальное состояние преобразования в начале новой исходной последовательности. Функция изменяет это сохраненное значение так, чтобы отразить текущее состояние успешного преобразования. Как правило, преобразование исходного элемента **CharType**(0) оставляет текущее состояние в начальном состоянии преобразования.  
  
 Функция-член возвращает [do_unshift](#do_unshift)(`_State`, `first2`, `last2`, `next2`).  
  
## <a name="see-also"></a>См. также  
 [\<locale>](../standard-library/locale.md)   
 [Кодовые страницы](../c-runtime-library/code-pages.md)   
 [Имена, языки и строки страны/региона языкового стандарта](../c-runtime-library/locale-names-languages-and-country-region-strings.md)   
 [Потокобезопасность в стандартной библиотеке C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)

