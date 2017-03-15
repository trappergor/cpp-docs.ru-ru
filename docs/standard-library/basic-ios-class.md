---
title: "Класс basic_ios | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- std.basic_ios
- ios/std::basic_ios
- basic_ios
- std::basic_ios
dev_langs:
- C++
helpviewer_keywords:
- basic_ios class
ms.assetid: 4fdcd8e1-62d2-4611-8a70-1e4f58434007
caps.latest.revision: 24
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
translationtype: Machine Translation
ms.sourcegitcommit: a937c9d083a7e4331af63323a19fb207142604a0
ms.openlocfilehash: 6987d9c75785ebb716324395e0ce295d4155e55f
ms.lasthandoff: 02/24/2017

---
# <a name="basicios-class"></a>Класс basic_ios
Этот класс шаблона описывает хранилище и функции-члены, общие для входных потоков (класс шаблона [basic_istream](../standard-library/basic-istream-class.md)) и выходных потоков (класс шаблона [basic_ostream](../standard-library/basic-ostream-class.md)), которые зависят от параметров шаблона. (Класс [basic_ios](../standard-library/ios-base-class.md) описывает общие принципы, не зависящие от параметров шаблона.) Объект класса **basic_ios\<class Elem, class Traits>** помогает управлять потоком с помощью элементов типа **Elem**, признаки символов которых определяются классом **Traits**.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
 
template <class Elem, class Traits>  
class basic_ios : public ios_base  
```  
  
#### <a name="parameters"></a>Параметры  
 `Elem`  
 Тип.  
  
 `Traits`  
 Переменная типа `char_traits`.  
  
## <a name="remarks"></a>Примечания  
 Объект класса **basic_ios\<class Elem, class Traits>** хранит следующее.  
  
-   Указатель на объект типа [basic_istream](../standard-library/basic-istream-class.md)**\<Elem, Traits>**.  
  
-   Указатель буфера потока на объект типа [basic_streambuf](../standard-library/basic-streambuf-class.md)**\<Elem, Traits >**.  
  
- [Сведения о форматировании](../standard-library/ios-base-class.md).  
  
- [Сведения о состоянии потока](../standard-library/ios-base-class.md) в базовом объекте типа [ios_base](../standard-library/ios-base-class.md).  
  
-   Символ заполнения в объекте типа `char_type`.  
  
### <a name="constructors"></a>Конструкторы  
  
|||  
|-|-|  
|[basic_ios](#basic_ios__basic_ios)|Создает класс `basic_ios`.|  
  
### <a name="typedefs"></a>Typedefs  
  
|||  
|-|-|  
|[char_type](#basic_ios__char_type)|Синоним параметра шаблона `Elem`.|  
|[int_type](#basic_ios__int_type)|Синоним для `Traits::int_type`.|  
|[off_type](#basic_ios__off_type)|Синоним для `Traits::off_type`.|  
|[pos_type](#basic_ios__pos_type)|Синоним для `Traits::pos_type`.|  
|[traits_type](#basic_ios__traits_type)|Синоним параметра шаблона `Traits`.|  
  
### <a name="member-functions"></a>Функции-члены  
  
|||  
|-|-|  
|[bad](#basic_ios__bad)|Сообщает о потере целостности буфера потока.|  
|[clear](#basic_ios__clear)|Очищает все флаги ошибок.|  
|[copyfmt](#basic_ios__copyfmt)|Копирует флаги из одного потока в другой.|  
|[eof](#basic_ios__eof)|Указывает, достигнут ли конец потока.|  
|[exceptions](#basic_ios__exceptions)|Указывает, какие исключения будут создаваться потоком.|  
|[fail](#basic_ios__fail)|Сообщает об ошибке при извлечении допустимого поля из потока.|  
|[fill](#basic_ios__fill)|Задает или возвращает символ, который будет использоваться, если ширина текста не совпадает с шириной потока.|  
|[good](#basic_ios__good)|Указывает, что поток находится в хорошем состоянии.|  
|[imbue](#basic_ios__imbue)|Изменяет языковой стандарт.|  
|[init](#basic_ios__init)|Вызывается конструкторами `basic_ios`.|  
|[move](#basic_ios__move)|Перемещает все значения, кроме указателя на буфер потока, из параметра в текущий объект.|  
|[narrow](#basic_ios__narrow)|Находит эквивалентный char для данного `char_type`.|  
|[rdbuf](#basic_ios__rdbuf)|Направляет поток в указанный буфер.|  
|[rdstate](#basic_ios__rdstate)|Считывает состояние битов для флагов.|  
|[set_rdbuf](#basic_ios__set_rdbuf)|Назначает буфер потока буфером чтения для этого объекта потока.|  
|[setstate](#basic_ios__setstate)|Устанавливает дополнительные флаги.|  
|[swap](#basic_ios__swap)|Меняет местами значения в этом объекте `basic_ios` и значения другого объекта `basic_ios`. Указатели на буферы потока не меняются местами.|  
|[tie](#basic_ios__tie)|Гарантирует, что один поток обрабатывается до другого потока.|  
|[widen](#basic_ios__widen)|Находит эквивалент `char_type` для указанного char.|  
  
### <a name="operators"></a>Операторы  
  
|||  
|-|-|  
|[explicit operator bool](#basic_ios__operator_bool)|Позволяет использовать объект `basic_ios` как `bool`. Автоматическое преобразование типов отключено для предотвращения распространенных непредвиденных побочных эффектов.|  
|[operator void *](#basic_ios__operator_void_star)|Указывает, находится ли поток по-прежнему в хорошем состоянии.|  
|[оператор!](#basic_ios__operator_not)|Указывает, не находится ли поток в плохом состоянии.|  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** \<ios>  
  
 **Пространство имен:** std  
  
##  <a name="a-namebasiciosbada--basiciosbad"></a><a name="basic_ios__bad"></a>  basic_ios::bad  
 Сообщает о потере целостности буфера потока.  
  
```  
bool bad() const;
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение `true`, если `rdstate & badbit` не равно нулю; в противном случае — значение `false`.  
  
 Дополнительные сведения по `badbit` см. в разделе [ios_base::iostate](../standard-library/ios-base-class.md#ios_base__iostate).  
  
### <a name="example"></a>Пример  
  
```cpp  
// basic_ios_bad.cpp  
// compile with: /EHsc  
#include <iostream>  
  
int main( void )  
{  
  using namespace std;  
  bool b = cout.bad( );  
  cout << boolalpha;  
  cout << b << endl;  
    
  b = cout.good( );  
  cout << b << endl;  
}  
  
```  
  
##  <a name="a-namebasiciosbasiciosa--basiciosbasicios"></a><a name="basic_ios__basic_ios"></a>  basic_ios::basic_ios  
 Конструирует класс basic_ios.  
  
```   
explicit basic_ios(basic_streambuf<Elem,  Traits>* sb);
basic_ios();
```  
  
### <a name="parameters"></a>Параметры  
 `sb`  
 Стандартный буфер для хранения элементов ввода или вывода.  
  
### <a name="remarks"></a>Примечания  
 Первый конструктор инициализирует свой объект-член путем вызова [init](#basic_ios__init)(_ *Sb*). Второй (защищенный) конструктор оставляет свои объекты-члены не инициализированными. Последующий вызов **init** должен инициализировать объект, прежде чем он может быть безопасно уничтожен.  
  
##  <a name="a-namebasicioschartypea--basicioschartype"></a><a name="basic_ios__char_type"></a>  basic_ios::char_type  
 Синоним параметра-шаблона **Elem**.  
  
```   
typedef Elem char_type;  
```  
  
##  <a name="a-namebasicioscleara--basiciosclear"></a><a name="basic_ios__clear"></a>  basic_ios::clear  
 Очищает все флаги ошибок.  
  
```   
void clear(iostate state = goodbit, bool reraise = false); 
void clear(io_state state);
```  
  
### <a name="parameters"></a>Параметры  
 `state` (необязательно)  
 Флаги, которые следует задать после очистки всех флагов. По умолчанию — `goodbit`.  
  
 `reraise` (необязательно)  
 Указывает, следует ли заново создать исключение. По умолчанию — `false` (исключение не будет создано заново).  
  
### <a name="remarks"></a>Примечания  
 Флаги — **goodbit**, **failbit**, **eofbit** и **badbit**. Проверяет наличие этих флагов с помощью [good](#basic_ios__good), [bad](#basic_ios__bad), [eof](#basic_ios__eof) и [fail](#basic_ios__fail)  
  
 Функция-член заменяет сохраненную информацию о состоянии потока на следующее:  
  
 `state` &#124; `(`[rdbuf](#basic_ios__rdbuf) != 0 **goodbit** : **badbit**)  
  
 Если `state`**&**[exceptions](#basic_ios__exceptions) имеет ненулевое значение, то создается объект класса [failure](../standard-library/ios-base-class.md#ios_base__failure).  
  
### <a name="example"></a>Пример  
  Примеры использования **clear** см. в разделах [rdstate](#basic_ios__rdstate) и [getline](../standard-library/string-functions.md#getline).  
  
##  <a name="a-namebasicioscopyfmta--basicioscopyfmt"></a><a name="basic_ios__copyfmt"></a>  basic_ios::copyfmt  
 Копирует флаги из одного потока в другой.  
  
```   
basic_ios<Elem, Traits>& copyfmt(
const basic_ios<Elem, Traits>& right);
```  
  
### <a name="parameters"></a>Параметры  
 ` right`  
 Поток, флаги которого требуется скопировать.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Объект **this** для потока, в который копируются флаги.  
  
### <a name="remarks"></a>Примечания  
 Функция-член возвращает событие обратного вызова erase_event. Затем она копирует из ` right` в **\*this** символ заливки, указатель tie и сведения о форматировании. Перед изменением маски исключения она сообщает событие обратного вызова copyfmt_event. Если после завершения копирования **state & **[exceptions](#basic_ios__exceptions) не равно нулю, функция эффективно вызывает [clear](#basic_ios__clear) с аргументом [rdstate](#basic_ios__rdstate). Она возвращает **\*this**.  
  
### <a name="example"></a>Пример  
  
```cpp    
// basic_ios_copyfmt.cpp  
// compile with: /EHsc  
#include <iostream>  
#include <fstream>  
  
int main( )  
{  
  using namespace std;  
  ofstream x( "test.txt" );  
  int i = 10;  
    
  x << showpos;  
  cout << i << endl;  
  cout.copyfmt( x );  
  cout << i << endl;  
}  
  
```  
  
##  <a name="a-namebasicioseofa--basicioseof"></a><a name="basic_ios__eof"></a>  basic_ios::eof  
 Указывает, достигнут ли конец потока.  
  
```  
bool eof() const;
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение `true` достигло конца потока; в противном случае — значение `false`.  
  
### <a name="remarks"></a>Примечания  
 Функция-член возвращает `true`, если [rdstate](#basic_ios__rdstate) `& eofbit` имеет ненулевое значение. Дополнительные сведения по `eofbit` см. в разделе [ios_base::iostate](../standard-library/ios-base-class.md#ios_base__iostate).  
  
### <a name="example"></a>Пример  
  
```cpp    
// basic_ios_eof.cpp  
// compile with: /EHsc  
#include <iostream>  
#include <fstream>  
  
using namespace std;  
  
int main( int argc, char* argv[] )  
{  
  fstream   fs;  
  int n = 1;  
  fs.open( "basic_ios_eof.txt" );   // an empty file  
  cout << boolalpha  
  cout << fs.eof() << endl;  
  fs >> n;   // Read the char in the file  
  cout << fs.eof() << endl;  
}  
  
```  
  
##  <a name="a-namebasiciosexceptionsa--basiciosexceptions"></a><a name="basic_ios__exceptions"></a>  basic_ios::exceptions  
 Указывает, какие исключения будут создаваться потоком.  
  
```   
iostate exceptions() const; 
void exceptions(iostate Newexcept);
void exceptions(io_state Newexcept);
```  
  
### <a name="parameters"></a>Параметры  
 *Newexcept*  
 Флаги, которые должны вызывать исключение.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Флаги, указанные в настоящий момент для создания исключения для потока.  
  
### <a name="remarks"></a>Примечания  
 Первая функция-член возвращает сохраненную маску исключения. Вторая функция-член сохраняет *_Except* в маске исключения и возвращает предыдущее хранившееся там значение. Обратите внимание, что сохранение новой маски исключения может вызвать исключение так же, как вызов [clear](#basic_ios__clear)( [rdstate](#basic_ios__rdstate) ).  
  
### <a name="example"></a>Пример  
  
```cpp  
// basic_ios_exceptions.cpp  
// compile with: /EHsc /GR  
#include <iostream>  
  
int main( )  
{  
  using namespace std;  
    
  cout << cout.exceptions( ) << endl;  
  cout.exceptions( ios::eofbit );  
  cout << cout.exceptions( ) << endl;  
  try  
  {  
    cout.clear( ios::eofbit );   // Force eofbit on  
  }  
  catch ( exception &e )  
  {  
    cout.clear( );  
    cout << "Caught the exception." << endl;  
    cout << "Exception class: " << typeid(e).name()  << endl;  
    cout << "Exception description: " << e.what() << endl;  
  }  
}  
  
```  
  
```Output  
  
0  
1  
Caught the exception.  
Exception class: class std::ios_base::failure  
Exception description: ios_base::eofbit set   
```  
  
##  <a name="a-namebasiciosfaila--basiciosfail"></a><a name="basic_ios__fail"></a>  basic_ios::fail  
 Сообщает об ошибке при извлечении допустимого поля из потока.  
  
```  
bool fail() const;
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение `true`, если [rdstate](#basic_ios__rdstate) `& (badbit|failbit)` не равен нулю; в противном случае — значение `false`.  
  
 Дополнительные сведения по `failbit` см. в разделе [ios_base::iostate](../standard-library/ios-base-class.md#ios_base__iostate).  
  
### <a name="example"></a>Пример  
  
```cpp  
// basic_ios_fail.cpp  
// compile with: /EHsc  
#include <iostream>  
  
int main( void )  
{  
  using namespace std;  
  bool b = cout.fail( );  
  cout << boolalpha;  
  cout << b << endl;  
}  
  
```  
  
##  <a name="a-namebasiciosfilla--basiciosfill"></a><a name="basic_ios__fill"></a>  basic_ios::fill  
 Задает или возвращает символ, который будет использоваться, если ширина текста не совпадает с шириной потока.  
  
```   
char_type fill() const; 
char_type fill(char_type Char);
```  
  
### <a name="parameters"></a>Параметры  
 `Char`  
 Символ, который нужно использовать в качестве символа заливки.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Текущий символ заливки.  
  
### <a name="remarks"></a>Примечания  
 Первая функция-член возвращает сохраненный символ заливки. Вторая функция-член сохраняет `Char` в символе заливки и возвращает его ранее сохраненное значение.  
  
### <a name="example"></a>Пример  
  
```cpp  
// basic_ios_fill.cpp  
// compile with: /EHsc  
#include <iostream>  
#include <iomanip>  
  
int main( )  
{  
  using namespace std;  
    
  cout << setw( 5 ) << 'a' << endl;     
  cout.fill( 'x' );  
  cout << setw( 5 ) << 'a' << endl;      
  cout << cout.fill( ) << endl;  
}  
  
```  
  
```Output  
  
a  
xxxxa  
x   
```  
  
##  <a name="a-namebasiciosgooda--basiciosgood"></a><a name="basic_ios__good"></a>  basic_ios::good  
 Указывает, что поток находится в хорошем состоянии.  
  
```  
bool good() const;
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение `true`, если [rdstate](#basic_ios__rdstate) `== goodbit` (флаги состояния не установлены), в противном случае — значение `false`.  
  
 Дополнительные сведения по `goodbit` см. в разделе [ios_base::iostate](../standard-library/ios-base-class.md#ios_base__iostate).  
  
### <a name="example"></a>Пример  
  Пример использования `good` разделе [basic_ios::bad](#basic_ios__bad).  
  
##  <a name="a-namebasiciosimbuea--basiciosimbue"></a><a name="basic_ios__imbue"></a>  basic_ios::imbue  
 Изменяет языковой стандарт.  
  
```   
locale imbue(const locale& Loc);
```  
  
### <a name="parameters"></a>Параметры  
 `Loc`  
 Строка языкового стандарта.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Предыдущий языковой стандарт.  
  
### <a name="remarks"></a>Примечания  
 Если [rdbuf](#basic_ios__rdbuf) не является пустым указателем, функция-член вызывает  
  
 `rdbuf`-> [pubimbue](../standard-library/basic-streambuf-class.md#basic_streambuf__pubimbue)(_ *Loc*)  
  
 В любом случае возвращается [ios_base::imbue](../standard-library/ios-base-class.md#ios_base__imbue)(_ *Loc*).  
  
### <a name="example"></a>Пример  
  
```cpp  
// basic_ios_imbue.cpp  
// compile with: /EHsc  
#include <iostream>  
#include <locale>  
  
int main( )  
{  
  using namespace std;  
    
  cout.imbue( locale( "french_france" ) );  
  double x = 1234567.123456;  
  cout << x << endl;  
}  
  
```  
  
##  <a name="a-namebasiciosinita--basiciosinit"></a><a name="basic_ios__init"></a>  basic_ios::init  
 Вызывается конструкторами basic_ios.  
  
```  
 
void init(basic_streambuf<Elem,Traits>* _Sb, bool _Isstd = false);
```  
  
### <a name="parameters"></a>Параметры  
 `_Sb`  
 Стандартный буфер для хранения элементов ввода или вывода.  
  
 `_Isstd`  
 Указывает, является ли этот поток стандартным.  
  
### <a name="remarks"></a>Примечания  
 Функция-член сохраняет значения во всех объектах-членах, так что:  
  
- [rdbuf](#basic_ios__rdbuf) возвращает *_Sb*;  
  
- [tie](#basic_ios__tie) возвращает пустой указатель;  
  
- [rdstate](#basic_ios__rdstate) возвращает [goodbit](../standard-library/ios-base-class.md#ios_base__iostate), если `_Sb` не равен нулю; в противном случае возвращается [badbit](../standard-library/ios-base-class.md#ios_base__iostate);  
  
- [exceptions](#basic_ios__exceptions) возвращает **goodbit**;  
  
- [flags](../standard-library/ios-base-class.md#ios_base__flags) возвращает [skipws](../standard-library/ios-base-class.md#ios_base__fmtflags) &#124; [dec](../standard-library/ios-base-class.md#ios_base__fmtflags);  
  
- [width](../standard-library/ios-base-class.md#ios_base__width) возвращает 0;  
  
- [precision](../standard-library/ios-base-class.md#ios_base__precision) возвращает 6;  
  
- [fill](#basic_ios__fill) возвращает символ пробела;  
  
- [getloc](../standard-library/ios-base-class.md#ios_base__getloc) возвращает `locale::classic`;  
  
- [iword](../standard-library/ios-base-class.md#ios_base__iword) возвращает ноль, и [pword](../standard-library/ios-base-class.md#ios_base__pword) возвращает пустой указатель для всех значений аргумента.  
  
##  <a name="a-namebasiciosinttypea--basiciosinttype"></a><a name="basic_ios__int_type"></a>  basic_ios::int_type  
 Синоним для **traits_type::int_type**.  
  
```  
typedef typename traits_type::int_type int_type;  
```  
  
##  <a name="a-namebasiciosmovea--basiciosmove"></a><a name="basic_ios__move"></a>  basic_ios::move  
 Перемещает все значения, кроме указателя на буфер потока, из параметра в текущий объект.  
  
```   
void move(basic_ios&& right);
```  
  
### <a name="parameters"></a>Параметры  
 `right`  
 Объект `ios_base`, из которого будут перемещаться значения.  
  
### <a name="remarks"></a>Примечания  
 Защищенная функция-член перемещает в `*this` все значения, хранящиеся в ` right`, за исключением сохраненного `stream buffer pointer`, который не изменяется в ` right` и устанавливается в пустой указатель в `*this`. Сохраненному `tie pointer` присваивается пустой указатель в ` right`.  
  
##  <a name="a-namebasiciosnarrowa--basiciosnarrow"></a><a name="basic_ios__narrow"></a>  basic_ios::narrow  
 Находит эквивалентный char для данного `char_type`.  
  
```  
 
char narrow(char_type Char, char Default = '\0') const;
```  
  
### <a name="parameters"></a>Параметры  
 `Char`  
 Преобразуемый объект `char`.  
  
 `Default`  
 `char`, который должен возвращаться, если эквивалент не будет найден.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Эквивалент `char` для указанного `char_type`.  
  
### <a name="remarks"></a>Примечания  
 Функция-член возвращает [use_facet](../standard-library/basic-filebuf-class.md#basic_filebuf__open)**<**Â **ctype**\< **E**> >( [getloc](../standard-library/ios-base-class.md#ios_base__getloc)( ) ). `narrow`( `Char`, `Default`).  
  
### <a name="example"></a>Пример  
  
```cpp  
// basic_ios_narrow.cpp  
// compile with: /EHsc  
#include <ios>  
#include <iostream>  
#include <wchar.h>  
  
int main( )  
{  
  using namespace std;  
  wchar_t *x = L"test";  
  char y[10];  
  cout << x[0] << endl;  
  wcout << x << endl;  
  y[0] = wcout.narrow( x[0] );  
  cout << y[0] << endl;  
}  
  
```  
  
##  <a name="a-namebasiciosofftypea--basiciosofftype"></a><a name="basic_ios__off_type"></a>  basic_ios::off_type  
 Синоним для **traits_type::off_type**.  
  
```  
typedef typename traits_type::off_type off_type;  
```  
  
##  <a name="a-namebasiciosoperatorvoidstara--basiciosoperator-void-"></a><a name="basic_ios__operator_void_star"></a>  basic_ios::operator void *  
 Указывает, находится ли поток по-прежнему в хорошем состоянии.  
  
```  
 operator void *() const;
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Оператор возвращает пустой указатель только в том случае, если [fail](#basic_ios__fail).  
  
### <a name="example"></a>Пример  
  
```cpp  
// basic_ios_opgood.cpp  
// compile with: /EHsc  
#include <iostream>  
  
int main( )  
{  
  using namespace std;  
  cout << (bool)(&cout != 0) << endl;   // Stream is still good  
}  
  
```  
  
```Output  
1  
```  
  
##  <a name="a-namebasiciosoperatornota--basiciosoperator"></a><a name="basic_ios__operator_not"></a>  basic_ios::operator!  
 Указывает, не находится ли поток в плохом состоянии.  
  
```   
bool operator!() const;
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает [fail](#basic_ios__fail).  
  
### <a name="example"></a>Пример  
  
```cpp  
// basic_ios_opbad.cpp  
// compile with: /EHsc  
#include <iostream>  
  
int main( )  
{  
  using namespace std;  
  cout << !cout << endl;   // Stream is not bad  
}  
  
```  
  
```Output  
0  
```  
  
##  <a name="a-namebasiciosoperatorboola--basiciosoperator-bool"></a><a name="basic_ios__operator_bool"></a>  basic_ios::operator bool  
 Позволяет использовать объект `basic_ios` как `bool`. Автоматическое преобразование типов отключено для предотвращения распространенных непредвиденных побочных эффектов.  
  
```  
explicit operator bool() const;
```  
  
### <a name="remarks"></a>Примечания  
 Оператор возвращает значение, которое можно преобразовать в `false`, только если `fail``()`. Тип возвращаемого значения можно преобразовать только в `bool`, а не в `void *` или в другие известные скалярные типы.  
  
##  <a name="a-namebasiciospostypea--basiciospostype"></a><a name="basic_ios__pos_type"></a>  basic_ios::pos_type  
 Синоним для **traits_type::pos_type**.  
  
```  
typedef typename traits_type::pos_type pos_type;  
```  
  
##  <a name="a-namebasiciosrdbufa--basiciosrdbuf"></a><a name="basic_ios__rdbuf"></a>  basic_ios::rdbuf  
 Направляет поток в указанный буфер.  
  
```   
basic_streambuf<Elem, Traits> *rdbuf() const; 
basic_streambuf<Elem, Traits> *rdbuf(
basic_streambuf<Elem, Traits>* _Sb);
```  
  
### <a name="parameters"></a>Параметры  
 `_Sb`  
 Поток.  
  
### <a name="remarks"></a>Примечания  
 Первая функция-член возвращает сохраненный указатель буфера потока.  
  
 Вторая функция-член сохраняет `_Sb` в сохраненном указателе буфера потока и возвращает ранее сохраненное в нем значение.  
  
### <a name="example"></a>Пример  
  
```cpp  
// basic_ios_rdbuf.cpp  
// compile with: /EHsc  
#include <ios>  
#include <iostream>  
#include <fstream>  
  
int main( )  
{  
  using namespace std;  
  ofstream file( "rdbuf.txt" );  
  streambuf *x = cout.rdbuf( file.rdbuf( ) );  
  cout << "test" << endl;   // Goes to file  
  cout.rdbuf(x);  
  cout << "test2" << endl;  
}  
  
```  
  
```Output  
test2  
```  
  
##  <a name="a-namebasiciosrdstatea--basiciosrdstate"></a><a name="basic_ios__rdstate"></a>  basic_ios::rdstate  
 Считывает состояние битов для флагов.  
  
```  
 
iostate rdstate() const;
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Сведения о состоянии сохраненного потока.  
  
### <a name="example"></a>Пример  
  
```cpp  
// basic_ios_rdstate.cpp  
// compile with: /EHsc  
#include <iostream>  
#include <fstream>  
using namespace std;  
  
void TestFlags( ios& x )  
{  
  cout << ( x.rdstate( ) & ios::badbit ) << endl;  
  cout << ( x.rdstate( ) & ios::failbit ) << endl;  
  cout << ( x.rdstate( ) & ios::eofbit ) << endl;  
  cout << endl;  
}  
  
int main( )  
{  
  fstream x( "c:\test.txt", ios::out );  
  x.clear( );  
  TestFlags( x );  
  x.clear( ios::badbit | ios::failbit | ios::eofbit );  
  TestFlags( x );  
}  
  
```  
  
```Output  
  
0  
0  
0  
  
4  
2  
1   
```  
  
##  <a name="a-namebasiciossetstatea--basiciossetstate"></a><a name="basic_ios__setstate"></a>  basic_ios::setstate  
 Устанавливает дополнительные флаги.  
  
```   
void setstate(iostate _State);
```  
  
### <a name="parameters"></a>Параметры  
 `_State`  
 Дополнительные флаги для установки.  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член эффективно вызывает [clear](#basic_ios__clear)(_ *State* &#124; [rdstate](#basic_ios__rdstate)).  
  
### <a name="example"></a>Пример  
  
```cpp    
// basic_ios_setstate.cpp  
// compile with: /EHsc  
#include <ios>  
#include <iostream>  
using namespace std;  
  
int main( )  
{  
  bool b = cout.bad( );  
  cout << b << endl;   // Good  
  cout.clear( ios::badbit );  
  b = cout.bad( );  
  // cout.clear( );  
  cout << b << endl;   // Is bad, good  
  b = cout.fail( );  
  cout << b << endl;   // Not failed  
  cout.setstate( ios::failbit );  
  b = cout.fail( );  
  cout.clear( );  
  cout << b << endl;   // Is failed, good  
  return 0;  
}  
  
```  
  
```Output  
  
0  
1   
```  
  
##  <a name="a-namebasiciossetrdbufa--basiciossetrdbuf"></a><a name="basic_ios__set_rdbuf"></a>  basic_ios::set_rdbuf  
 Назначает буфер потока буфером чтения для этого объекта потока.  
  
```   
void set_rdbuf(
basic_streambuf<Elem, Tr>* strbuf)  
```  
  
### <a name="parameters"></a>Параметры  
 ` strbuf`  
 Буфер потока, который должен стать буфером чтения.  
  
### <a name="remarks"></a>Примечания  
 Защищенная функция-член сохраняет ` strbuf` в `stream buffer pointer`. Она не вызывает `clear`.  
  
##  <a name="a-namebasiciostiea--basiciostie"></a><a name="basic_ios__tie"></a>  basic_ios::tie  
 Гарантирует, что один поток обрабатывается до другого потока.  
  
```  
 
basic_ostream<Elem, Traits> *tie() const; 
basic_ostream<Elem, Traits> *tie(
basic_ostream<Elem, Traits>* str);
```  
  
### <a name="parameters"></a>Параметры  
 ` str`  
 Поток.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Первая функция-член возвращает сохраненный указатель tie. Вторая функция-член сохраняет ` str` в указателе tie и возвращает его ранее сохраненное значение.  
  
### <a name="remarks"></a>Примечания  
 `tie` вызывает синхронизацию двух потоков, так что операции в одном потоке операций происходят после завершения операций в другом потоке.  
  
### <a name="example"></a>Пример  
  В этом примере путем связывания cin с cout гарантируется, что строка "Enter a number:" будет появляться на консоли перед самим номером, извлекаемым из cin. Это исключает возможность того, что строка "Enter a number:" будет оставаться в буфере при считывании номера, и таким образом мы гарантируем, что пользователь фактически получает некоторый запрос, на который нужно отреагировать. По умолчанию cin и cout связаны.  
  
```  
  
#include <ios>  
#include <iostream>  
  
int main( )  
{  
  using namespace std;  
  int i;  
  cin.tie( &cout );  
  cout << "Enter a number:";  
  cin >> i;  
}  
  
```  
  
##  <a name="a-namebasiciostraitstypea--basiciostraitstype"></a><a name="basic_ios__traits_type"></a>  basic_ios::traits_type  
 Синоним для параметра-шаблона **Traits**.  
  
```   
typedef Traits traits_type;  
```  
  
##  <a name="a-namebasicioswidena--basicioswiden"></a><a name="basic_ios__widen"></a>  basic_ios::widen  
 Находит эквивалент `char_type` для указанного `char`.  
  
```   
char_type widen(char Char) const;
```  
  
### <a name="parameters"></a>Параметры  
 `Char`  
 Символ для преобразования.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Находит эквивалент `char_type` для указанного `char`.  
  
### <a name="remarks"></a>Примечания  
 Функция-член возвращает [use_facet](../standard-library/basic-filebuf-class.md#basic_filebuf__open)< **ctype**\< **E**> >( [getloc](../standard-library/ios-base-class.md#ios_base__getloc)). `widen`( `Char`).  
  
### <a name="example"></a>Пример  
  
```cpp    
// basic_ios_widen.cpp  
// compile with: /EHsc  
#include <ios>  
#include <iostream>  
#include <wchar.h>  
  
int main( )  
{  
  using namespace std;  
  char *z = "Hello";  
  wchar_t y[2] = {0,0};  
  cout << z[0] << endl;  
  y[0] = wcout.widen( z[0] );  
  wcout << &y[0] << endl;  
}  
  
```  
  
##  <a name="a-namebasiciosswapa--basiciosswap"></a><a name="basic_ios__swap"></a>  basic_ios::swap  
 Меняет местами значения в этом объекте `basic_ios` и значения другого объекта `basic_ios`. Однако указатели на буферы потока не меняются местами.  
  
```   
void swap(basic_ios&& right);
```  
  
### <a name="parameters"></a>Параметры  
 `right`  
 Объект `basic_ios`, используемый для обмена значений.  
  
### <a name="remarks"></a>Примечания  
 Защищенная функция-член меняет обменивает все значения, хранящиеся в ` right`, со значениями `*this`, за исключением сохраненного `stream buffer pointer`.  
  
## <a name="see-also"></a>См. также  
 [Потокобезопасность в стандартной библиотеке C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [Программирование iostream](../standard-library/iostream-programming.md)   
 [Соглашения iostreams](../standard-library/iostreams-conventions.md)


