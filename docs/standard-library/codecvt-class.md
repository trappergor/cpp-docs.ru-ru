---
title: "Класс codecvt | Microsoft Docs"
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
  - "codecvt"
  - "std::codecvt"
  - "std.codecvt"
  - "xlocale/std::codecvt"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "codecvt - класс"
ms.assetid: 37d3efa1-2b7f-42b6-b04f-7a972c8c2c86
caps.latest.revision: 23
caps.handback.revision: 23
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Класс codecvt
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

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
 Класс шаблона описывает объект, который можно использовать в качестве [аспекта языкового стандарта](../standard-library/locale-class.md#facet_class), для управления преобразованиями между последовательностями значений типа `CharType` и последовательность значений типа `Byte`. Класс `StateType` характеризует преобразование, а объект класса `StateType` сохраняет все необходимые сведения о состоянии во время преобразования.  
  
 Внутренняя кодировка использует представление с фиксированным числом байтов на один знак, обычно либо тип `char`, либо тип `wchar_t`.  
  
 Как и в случае любого другого аспекта языкового стандарта, начальное сохраненное значение статического `id` объекта равно нулю. Первая попытка получить доступ к сохраненному значению сохранит уникальное положительное значение в `id`.  
  
 Шаблонные версии [do_in](#codecvt__do_in) и [do_out](#codecvt__do_out) всегда возвращать `codecvt_base::noconv`.  
  
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
|[codecvt](#codecvt__codecvt)|Конструктор для объектов класса `codecvt`, который служит в качестве аспекта языкового стандарта для обработки преобразований.|  
  
### <a name="typedefs"></a>Typedefs  
  
|||  
|-|-|  
|[extern_type](#codecvt__extern_type)|Тип символа, используемый для внешних представлений.|  
|[intern_type](#codecvt__intern_type)|Тип символа, используемый для внутренних представлений.|  
|[state_type](#codecvt__state_type)|Тип символа, который используется для представления промежуточных состояний во время преобразований между внутренними и внешними представлениями.|  
  
### <a name="member-functions"></a>Функции-члены  
  
|||  
|-|-|  
|[always_noconv](#codecvt__always_noconv)|Проверяет, не требуется ли выполнит преобразования.|  
|[do_always_noconv](#codecvt__do_always_noconv)|Виртуальная функция, вызываемая проверки того, не требуется ли выполнить преобразования.|  
|[do_encoding](#codecvt__do_encoding)|Виртуальная функция, проверяющая, зависит ли кодировка потока `Byte` от состояния, является ли соотношение между использованными объектами `Byte` и полученными объектами `CharType` константой, и, если это так, определяет значение этого соотношения.|  
|[do_in](#codecvt__do_in)|Виртуальная функция, вызываемая для преобразования последовательности внутренних `Byte` в последовательность внешних `CharType`.|  
|[do_length](#codecvt__do_length)|Виртуальная функция, которая определяет, сколько объектов `Byte` из заданной последовательности внешних объектов `Byte` создают не более указанного количества внутренних объектов `CharType`, и возвращает это число объектов `Byte`.|  
|[do_max_length](#codecvt__do_max_length)|Виртуальная функция, возвращающая максимальное число внешних байтов, необходимых для создания одного внутреннего `CharType`.|  
|[do_out](#codecvt__do_out)|Виртуальная функция, вызываемая для преобразования последовательности внутренних `CharType` в последовательность внешних байтов.|  
|[do_unshift](#codecvt__do_unshift)|Виртуальная функция, вызываемая для предоставления объектов `Byte`, необходимых при зависимом от состояния преобразовании для завершения последнего символа в последовательности объектов `Byte`.|  
|[Кодировка](#codecvt__encoding)|Проверяет, зависит ли кодировка потока `Byte` от состояния, является ли соотношение между использованными объектами `Byte` и полученными объектами `CharType` константой, и, если это так, определяет значение этого соотношения.|  
|[в](#codecvt__in)|Преобразует внешнее представление последовательности объектов `Byte` во внутреннее представление последовательности объектов `CharType`.|  
|[Длина](#codecvt__length)|Определяет, сколько объектов `Byte` из заданной последовательности внешних объектов `Byte` создают не более указанного количества внутренних объектов `CharType`, и возвращает это число объектов `Byte`.|  
|[max_length](#codecvt__max_length)|Возвращает максимальное число внешних объектов `Byte`, необходимых для создания одного внутреннего `CharType`.|  
|[Выход](#codecvt__out)|Преобразует последовательность внутренних объектов `CharType` в последовательность внешних объектов `Byte`.|  
|[unshift](#codecvt__unshift)|Предоставляет внешние `Byte`, необходимые при зависимом от состояния преобразовании для завершения последнего символа в последовательности объектов `Byte`.|  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** \< языкового стандарта>  
  
 **Пространство имен:** std  
  
##  <a name="a-namecodecvtalwaysnoconva-codecvtalwaysnoconv"></a><a name="codecvt__always_noconv"></a>  codecvt::always_noconv  
 Проверяет, не требуется ли выполнит преобразования.  
  
```  
bool always_noconv() const throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Логическое значение, равное **true** если требуется выполнить преобразование; **false** по крайней мере один должен выполняться.  
  
### <a name="remarks"></a>Примечания  
 Функция-член возвращает [do_always_noconv](#codecvt__do_always_noconv).  
  
### <a name="example"></a>Пример  
  
```  
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
  
##  <a name="a-namecodecvtcodecvta-codecvtcodecvt"></a><a name="codecvt__codecvt"></a>  codecvt::codecvt  
 Конструктор для объектов класса codecvt, который служит в качестве аспекта языкового стандарта для обработки преобразований.  
  
```  
explicit codecvt(size_t _Refs = 0);
```  
  
### <a name="parameters"></a>Параметры  
 `_Refs`  
 Целочисленное значение используется для указания типа управление памятью для объекта.  
  
### <a name="remarks"></a>Примечания  
 Возможные значения параметра `_Refs` параметров и их важность являются:  
  
-   0: время существования объекта управляется национальных настроек, которые его содержат.  
  
-   1: время существования объекта должно осуществляться вручную.  
  
-   \> 0: эти значения не определены.  
  
 Конструктор инициализирует его `locale::facet` базовый объект с **locale::**[аспекта](../standard-library/locale-class.md#facet_class)( `_Refs`) *.*  
  
##  <a name="a-namecodecvtdoalwaysnoconva-codecvtdoalwaysnoconv"></a><a name="codecvt__do_always_noconv"></a>  codecvt::do_always_noconv  
 Виртуальная функция, вызываемая проверки того, не требуется ли выполнить преобразования.  
  
```  
virtual bool do_always_noconv() const throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает защищенный виртуальной функции-члена **true** только тогда, когда каждый вызов [do_in](#codecvt__do_in) или [do_out](#codecvt__do_out) возвращает **noconv**.  
  
 Всегда возвращает версию шаблона **true**.  
  
### <a name="example"></a>Пример  
  В примере показано [always_noconv](#codecvt__always_noconv), который вызывает метод `do_always_noconv`.  
  
##  <a name="a-namecodecvtdoencodinga-codecvtdoencoding"></a><a name="codecvt__do_encoding"></a>  codecvt::do_encoding  
 Виртуальная функция, которая проверяет кодировку **байтов** поток находится в состоянии, зависимые, является ли соотношение между **байтов**s используется и **CharType**использованными является константой и если это так, определяет значение этого соотношения.  
  
```  
virtual int do_encoding() const throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает защищенный виртуальной функции-члена:  
  
-   -1, если кодировка последовательностей типа `extern_type` зависит от состояния.  
  
-   0, если кодировка включает последовательности переменной длины.  
  
- *N*, если кодировка включает в себя только последовательности длины *N*  
  
### <a name="example"></a>Пример  
  В примере показано [Кодировка](#codecvt__encoding), который вызывает метод `do_encoding`.  
  
##  <a name="a-namecodecvtdoina-codecvtdoin"></a><a name="codecvt__do_in"></a>  codecvt::do_in  
 Виртуальная функция, вызываемая для преобразования последовательности внешних объектов **байтов**последовательность внутренних **CharType**s.  
  
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
 Состояние преобразования, который ведется между вызовами функции-члена.  
  
 ` first1`  
 Указатель на начало последовательности для преобразования.  
  
 ` last1`  
 Указатель на конец последовательности для преобразования.  
  
 ` next1`  
 Указатель за пределами преобразованный последовательности, для первого непреобразованного символа.  
  
 ` first2`  
 Указатель на начало преобразованный последовательности.  
  
 ` last2`  
 Указатель на конец преобразованный последовательности.  
  
 ` next2`  
 Указатель на **CharType** который поставляется вместе после преобразования последнего **CharType**, первый символ без изменений в целевой последовательности.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Return, который означает успех, частичный успех или сбой операции. Функция возвращает:  
  
- **codecvt_base::Error** Если исходная последовательность неправильный формат.  
  
- `codecvt_base::noconv` Если функция преобразование не выполняется.  
  
- **codecvt_base::OK** Если преобразование завершается успешно.  
  
- **codecvt_base::partial** недостаточно источника или назначения недостаточно велик, для успешного преобразования.  
  
### <a name="remarks"></a>Примечания  
 `_State` должно представлять состояние начального преобразования в начале новой исходной последовательности. Функция изменяет сохраненному значению, необходимыми для отражения текущего состояния успешного преобразования. В противном случае не определен сохраненному значению.  
  
### <a name="example"></a>Пример  
  В примере показано [в](#codecvt__in), который вызывает метод `do_in`.  
  
##  <a name="a-namecodecvtdolengtha-codecvtdolength"></a><a name="codecvt__do_length"></a>  codecvt::do_length  
 Виртуальная функция, которая определяет, сколько **байтов**из заданной последовательности внешних объектов **байтов**создают не более указанного количества внутренних объектов **CharType**s и возвращает соответствующее количество **байтов**s.  
  
```  
virtual int do_length(
    const StateType& _State,  
    const Byte* first1,   
    const Byte* last1,  
    size_t _Len2) const;
```  
  
### <a name="parameters"></a>Параметры  
 `_State`  
 Состояние преобразования, который ведется между вызовами функции-члена.  
  
 ` first1`  
 Указатель на начало внешних последовательности.  
  
 ` last1`  
 Указатель в конец внешней последовательности.  
  
 `_Len2`  
 Максимальное число **байтов**s, возвращаемой функцией-членом.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Целое число, представляющее число преобразований, не больше максимального числа `_Len2`, определяемой внешним источником последовательность [ ` first1`, ` last1`).  
  
### <a name="remarks"></a>Примечания  
 Вызывает защищенный виртуальной функции-члена `do_in`( `_State`, ` first1`, ` last1`, ` next1`, `_Buf`, `_Buf` + `_Len2`, ` next2`) для `_State` (копии состояния), некоторые буфера `_Buf`, и указатели ` next1`и ` next2`.  
  
 Затем она возвращает ` next2` – **buf**. Таким образом, он подсчитывает число преобразований, не больше `_Len2`, определенных в исходной последовательности [ ` first1`, ` last1`).  
  
 Версия шаблона всегда возвращает меньший из ` last1` – ` first1` и `_Len2`.  
  
### <a name="example"></a>Пример  
  В примере показано [Длина](#codecvt__length), который вызывает метод **do_length**.  
  
##  <a name="a-namecodecvtdomaxlengtha-codecvtdomaxlength"></a><a name="codecvt__do_max_length"></a>  codecvt::do_max_length  
 Виртуальная функция, возвращающая максимальное число внешних **байтов**необходимых для создания одного внутреннего **CharType**.  
  
```  
virtual int do_max_length() const throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Максимальное число **байтов**необходимых для создания одного **CharType**.  
  
### <a name="remarks"></a>Примечания  
 Защищенные виртуальная функция-член возвращает наибольшее значение допустимого, возвращаемый [do_length](#codecvt__do_length)( ` first1`, ` last1`, 1) произвольных допустимые значения ` first1` и ` last1`.  
  
### <a name="example"></a>Пример  
  В примере показано [max_length](#codecvt__max_length), который вызывает метод `do_max_length`.  
  
##  <a name="a-namecodecvtdoouta-codecvtdoout"></a><a name="codecvt__do_out"></a>  codecvt::do_out  
 Виртуальная функция, вызываемая для преобразования последовательности внутренних **CharType**в последовательность внешних **байтов**s.  
  
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
 Состояние преобразования, который ведется между вызовами функции-члена.  
  
 ` first1`  
 Указатель на начало последовательности для преобразования.  
  
 ` last1`  
 Указатель на конец последовательности для преобразования.  
  
 ` next1`  
 Ссылка на указатель на первый непреобразованных **CharType**, после последнего **CharType** преобразования.  
  
 ` first2`  
 Указатель на начало преобразованный последовательности.  
  
 ` last2`  
 Указатель на конец преобразованный последовательности.  
  
 ` next2`  
 Ссылка на указатель на первый непреобразованных **байтов**, после последнего **байтов** преобразования.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Функция возвращает:  
  
- **codecvt_base::Error** Если исходная последовательность неправильный формат.  
  
- `codecvt_base::noconv` Если функция преобразование не выполняется.  
  
- **codecvt_base::OK** Если преобразование завершается успешно.  
  
- **codecvt_base::partial** недостаточно источника или назначения недостаточно велик для успешного преобразования.  
  
### <a name="remarks"></a>Примечания  
 `_State` должно представлять состояние начального преобразования в начале новой исходной последовательности. Функция изменяет сохраненному значению, необходимыми для отражения текущего состояния успешного преобразования. В противном случае не определен сохраненному значению.  
  
### <a name="example"></a>Пример  
  В примере показано [out](#codecvt__out), который вызывает метод `do_out`.  
  
##  <a name="a-namecodecvtdounshifta-codecvtdounshift"></a><a name="codecvt__do_unshift"></a>  codecvt::do_unshift  
 Виртуальная функция, вызываемая для предоставления **байтов**необходимых в зависимом от состояния преобразовании для завершения последнего символа в последовательности **байтов**s.  
  
```  
virtual result do_unshift(
    StateType& _State,  
    Byte* first2,   
    Byte* last2,   
    Byte*& next2) const;
```  
  
### <a name="parameters"></a>Параметры  
 `_State`  
 Состояние преобразования, который ведется между вызовами функции-члена.  
  
 ` first2`  
 Указатель на первое место в диапазон назначения.  
  
 ` last2`  
 Указатель на последнее место в диапазон назначения.  
  
 ` next2`  
 Указатель на первый элемент без изменений в целевой последовательности.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Функция возвращает:  
  
- **codecvt_base::Error** Если _ *состояние* представляет недопустимое состояние  
  
- `codecvt_base::noconv` Если функция преобразование не выполняется  
  
- **codecvt_base::OK** Если преобразование завершается успешно  
  
- **codecvt_base::partial** Если назначения недостаточно велик для успешного преобразования  
  
### <a name="remarks"></a>Примечания  
 Защищенные виртуальной функции-члена пытается преобразовать исходный элемент **CharType**(0) в последовательность назначения, который хранится в [ ` first2`, ` last2`), за исключением завершающего элемента **байтов**(0). Всегда сохраняет в ` next2` указатель на первый элемент без изменений в целевой последовательности.  
  
 _ *Состояние* должны представлять состояние начального преобразования в начале новой исходной последовательности. Функция изменяет сохраненному значению, необходимыми для отражения текущего состояния успешного преобразования. Как правило, преобразование исходного элемента **CharType**(0) выходит из текущего состояния в начальным состоянием преобразования.  
  
### <a name="example"></a>Пример  
  В примере показано [unshift](#codecvt__unshift), который вызывает метод `do_unshift`.  
  
##  <a name="a-namecodecvtencodinga-codecvtencoding"></a><a name="codecvt__encoding"></a>  codecvt::Encoding  
 Проверяет, кодировка **байтов** поток находится в состоянии, зависимые, является ли соотношение между **байтов**s используется и **CharType**использованными является константой и, если это так, определяет значение этого соотношения.  
  
```  
int encoding() const throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Если возвращаемое значение является положительным, то это значение является постоянным числом **байтов** символов, необходимых для создания **CharType** символов.  
  
 Возвращает защищенный виртуальной функции-члена:  
  
-   -1, если кодировка последовательностей типа `extern_type` зависит от состояния.  
  
-   0, если кодировка включает последовательности переменной длины.  
  
- *N*, если кодировка включает в себя только последовательности длины *N.*  
  
### <a name="remarks"></a>Примечания  
 Функция-член возвращает [do_encoding](#codecvt__do_encoding).  
  
### <a name="example"></a>Пример  
  
```  
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
  
##  <a name="a-namecodecvtexterntypea-codecvtexterntype"></a><a name="codecvt__extern_type"></a>  codecvt::extern_type  
 Тип символа, используемый для внешних представлений.  
  
```  
typedef Byte extern_type;  
```  
  
### <a name="remarks"></a>Примечания  
 Тип является синонимом параметра шаблона **байтов**.  
  
##  <a name="a-namecodecvtina-codecvtin"></a><a name="codecvt__in"></a>  codecvt::in  
 Преобразует внешнее представление последовательности **байтов**внутреннее представление последовательности **CharType**s.  
  
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
 Состояние преобразования, который ведется между вызовами функции-члена.  
  
 ` first1`  
 Указатель на начало последовательности для преобразования.  
  
 ` last1`  
 Указатель на конец последовательности для преобразования.  
  
 ` next1`  
 Указатель за пределы преобразованный последовательности для первого непреобразованного символа.  
  
 ` first2`  
 Указатель на начало преобразованный последовательности.  
  
 ` last2`  
 Указатель на конец преобразованный последовательности.  
  
 ` next2`  
 Указатель на **CharType** который поставляется вместе после преобразования последнего **Chartype** неизмененным первого символа в последовательности назначения.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Return, который означает успех, частичный успех или сбой операции. Функция возвращает:  
  
- **codecvt_base::Error** Если исходная последовательность неправильный формат.  
  
- `codecvt_base::noconv` Если функция преобразование не выполняется.  
  
- **codecvt_base::OK** Если преобразование завершается успешно.  
  
- **codecvt_base::partial** недостаточно источника или назначения недостаточно велик для успешного преобразования.  
  
### <a name="remarks"></a>Примечания  
 `_State` должно представлять состояние начального преобразования в начале новой исходной последовательности. Функция изменяет сохраненному значению, при необходимости, чтобы отразить текущее состояние успешного преобразования. После частичного преобразования `_State` необходимо задать таким образом, чтобы разрешить преобразование возобновить при поступлении новых символов.  
  
 Функция-член возвращает [do_in](#codecvt__do_in)( `_State`, _ *First1, last1, next1, First2, _Llast2, next2*).  
  
### <a name="example"></a>Пример  
  
```  
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
  
##  <a name="a-namecodecvtinterntypea-codecvtinterntype"></a><a name="codecvt__intern_type"></a>  codecvt::intern_type  
 Тип символа, используемый для внутренних представлений.  
  
```  
typedef CharType intern_type;  
```  
  
### <a name="remarks"></a>Примечания  
 Тип является синонимом параметра шаблона **CharType**.  
  
##  <a name="a-namecodecvtlengtha-codecvtlength"></a><a name="codecvt__length"></a>  codecvt::length  
 Определяет, сколько **байтов**из заданной последовательности внешних объектов **байтов**создают не более указанного количества внутренних объектов **CharType**s и возвращает соответствующее количество **байтов**s.  
  
```  
int length(
    const StateType& _State,  
    const Byte* first1,   
    const Byte* last1,  
    size_t _Len2) const;
```  
  
### <a name="parameters"></a>Параметры  
 `_State`  
 Состояние преобразования, который ведется между вызовами функции-члена.  
  
 ` first1`  
 Указатель на начало внешних последовательности.  
  
 ` last1`  
 Указатель в конец внешней последовательности.  
  
 `_Len2`  
 Максимальное число байтов, возвращенных функцией-членом.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Целое число, представляющее число преобразований, не больше максимального числа `_Len2`, определяемой внешним источником последовательность [ ` first1`, ` last1`).  
  
### <a name="remarks"></a>Примечания  
 Функция-член возвращает [do_length](#codecvt__do_length)( *_State first1*, ` last1`, `_Len2`).  
  
### <a name="example"></a>Пример  
  
```  
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
  
##  <a name="a-namecodecvtmaxlengtha-codecvtmaxlength"></a><a name="codecvt__max_length"></a>  codecvt::max_length  
 Возвращает максимальное число внешних объектов **байтов**необходимых для создания одного внутреннего **CharType**.  
  
```  
int max_length() const throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Максимальное число **байтов**необходимых для создания одного **CharType**.  
  
### <a name="remarks"></a>Примечания  
 Функция-член возвращает [do_max_length](#codecvt__do_max_length).  
  
### <a name="example"></a>Пример  
  
```  
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
  
##  <a name="a-namecodecvtouta-codecvtout"></a><a name="codecvt__out"></a>  codecvt::out  
 Преобразует последовательность внутренних **CharType**в последовательность внешних **байтов**s.  
  
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
 Состояние преобразования, который ведется между вызовами функции-члена.  
  
 ` first1`  
 Указатель на начало последовательности для преобразования.  
  
 ` last1`  
 Указатель на конец последовательности для преобразования.  
  
 ` next1`  
 Ссылка на указатель на первый непреобразованных **CharType** после последнего **CharType** преобразования.  
  
 ` first2`  
 Указатель на начало преобразованный последовательности.  
  
 ` last2`  
 Указатель на конец преобразованный последовательности.  
  
 ` next2`  
 Ссылка на указатель на первый непреобразованных **байтов** после преобразования последнего **байтов**.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Функция-член возвращает [do_out](#codecvt__do_out)( `_State`, ` first1`, ` last1`, ` next1`, ` first2`, ` last2`, ` next2`).  
  
### <a name="remarks"></a>Примечания  
 Дополнительные сведения см. в разделе [codecvt::do_out](#codecvt__do_out).  
  
### <a name="example"></a>Пример  
  
```  
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
  
##  <a name="a-namecodecvtstatetypea-codecvtstatetype"></a><a name="codecvt__state_type"></a>  codecvt::state_type  
 Тип символа, который используется для представления промежуточных состояний во время преобразований между внутренними и внешними представлениями.  
  
```  
typedef StateType state_type;  
```  
  
### <a name="remarks"></a>Примечания  
 Тип является синонимом параметра шаблона **StateType**.  
  
##  <a name="a-namecodecvtunshifta-codecvtunshift"></a><a name="codecvt__unshift"></a>  codecvt::unshift  
 Предоставляет **байтов**необходимых в зависимом от состояния преобразовании для завершения последнего символа в последовательности **байтов**s.  
  
```  
result unshift(
    StateType& _State,  
    Byte* first2,   
    Byte* last2,   
    Byte*& next2) const;
```  
  
### <a name="parameters"></a>Параметры  
 `_State`  
 Состояние преобразования, который ведется между вызовами функции-члена.  
  
 ` first2`  
 Указатель на первое место в диапазон назначения.  
  
 ` last2`  
 Указатель на последнее место в диапазон назначения.  
  
 ` next2`  
 Указатель на первый элемент без изменений в целевой последовательности.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Функция возвращает:  
  
- **codecvt_base::Error** Если состояние представляет недопустимое состояние.  
  
- `codecvt_base::noconv` Если функция преобразование не выполняется.  
  
- **codecvt_base::OK** Если преобразование завершается успешно.  
  
- **codecvt_base::partial** Если назначения недостаточно велик для успешного преобразования.  
  
### <a name="remarks"></a>Примечания  
 Защищенные виртуальной функции-члена пытается преобразовать исходный элемент **CharType**(0) в последовательность назначения, который хранится в [ ` first2`, ` last2`), за исключением завершающего элемента **байтов**(0). Всегда сохраняет в ` next2` указатель на первый элемент без изменений в целевой последовательности.  
  
 `_State` должно представлять состояние начального преобразования в начале новой исходной последовательности. Функция изменяет сохраненному значению, при необходимости, чтобы отразить текущее состояние успешного преобразования. Как правило, преобразование исходного элемента **CharType**(0) выходит из текущего состояния в начальным состоянием преобразования.  
  
 Функция-член возвращает [do_unshift](#codecvt__do_unshift)( `_State`, ` first2`, ` last2`, ` next2` ).  
  
## <a name="see-also"></a>См. также раздел  
 [\< языкового стандарта>](../standard-library/locale.md)   
 [Кодовые страницы](../c-runtime-library/code-pages.md)   
 [Имени языкового стандарта, языков и стран и регионов](../c-runtime-library/locale-names-languages-and-country-region-strings.md)   
 [Потокобезопасность в стандартной библиотеке C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)

