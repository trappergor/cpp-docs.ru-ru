---
title: "Определения типов &lt;ios&gt; | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ios/std::ios
- ios/std::streamoff
- ios/std::streampos
- ios/std::streamsize
- ios/std::wios
- ios/std::wstreampos
ms.assetid: 0b962632-3439-44de-bf26-20c67a7f0ff3
caps.latest.revision: 13
manager: ghogen
translationtype: Machine Translation
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: d9f9dd5f13f0f4559455ff8d8cf09bab5350b1f0
ms.lasthandoff: 02/24/2017

---
# <a name="ltiosgt-typedefs"></a>Определения типов &lt;ios&gt;
||||  
|-|-|-|  
|[ios](#ios)|[streamoff](#streamoff)|[streampos](#streampos)|  
|[streamsize](#streamsize)|[wios](#wios)|[wstreampos](#wstreampos)|  
  
##  <a name="ios"></a>  ios  
 Поддерживает класс ios из старой библиотеки iostream.  
  
```  
typedef basic_ios<char, char_traits<char>> ios;  
```  
  
### <a name="remarks"></a>Примечания  
 Этот тип является синонимом класса шаблона [basic_ios](../standard-library/basic-ios-class.md), специализированного для элементов типа `char` с признаками символов по умолчанию.  
  
##  <a name="streamoff"></a>  streamoff  
 Поддерживает внутренние операции.  
  
```  
#ifdef _WIN64  
    typedef __int64 streamoff;  
#else  
    typedef long streamoff;  
#endif  
```  
  
### <a name="remarks"></a>Примечания  
 Тип — целое число со знаком, описывающее объект, который может хранить смещение в байтах, участвующее в различных операциях размещения потока. Его представление имеет по крайней мере 32 бита значения. Оно не обязательно достаточно велико для представления произвольных позиций внутри потока. Значение **streamoff(-1)** обычно указывает на ошибочное смещение.  
  
##  <a name="streampos"></a>  streampos  
 Содержит текущее положение указателя буфера или указателя файла.  
  
```  
typedef fpos<mbstate_t> streampos;  
```  
  
### <a name="remarks"></a>Примечания  
 Тип является синонимом для [fpos](../standard-library/fpos-class.md)< `mbstate_t`>.  
  
### <a name="example"></a>Пример  
  
```cpp  
// ios_streampos.cpp  
// compile with: /EHsc  
#include <iostream>  
#include <fstream>  
  
int main( )   
{  
   using namespace std;  
  
   ofstream x( "iostream.txt" );  
   x << "testing";  
   streampos y = x.tellp( );  
   cout << y << endl;  
}  
```  
  
```Output  
7  
```  
  
##  <a name="streamsize"></a>  streamsize  
 Указывает размер потока.  
  
```  
#ifdef _WIN64  
    typedef __int64 streamsize;  
#else  
    typedef int streamsize;  
#endif  
```  
  
### <a name="remarks"></a>Примечания  
 Тип — целое число со знаком, описывающее объект, который может хранить количество элементов, участвующих в различных операциях размещения потока. Его представление имеет по крайней мере 16 битов значения. Оно не обязательно достаточно велико для представления произвольных позиций внутри потока.  
  
### <a name="example"></a>Пример  
  После компиляции и запуска следующей программы рассмотрим файл Test.txt, чтобы увидеть влияние параметра `streamsize`.  
  
```  
// ios_streamsize.cpp  
// compile with: /EHsc  
#include <iostream>  
#include <fstream>  
  
int main( )   
{  
   using namespace std;  
   char a[16] = "any such text";  
   ofstream x( "test.txt" );  
   streamsize y = 6;  
   x.write( a, y );  
}  
```  
  
##  <a name="wios"></a>  wios  
 Поддерживает класс wios из старой библиотеки iostream.  
  
```  
typedef basic_ios<wchar_t, char_traits<wchar_t>> wios;  
```  
  
### <a name="remarks"></a>Примечания  
 Этот тип является синонимом класса шаблона [basic_ios](../standard-library/basic-ios-class.md), специализированного для элементов типа `wchar_t` с признаками символов по умолчанию.  
  
##  <a name="wstreampos"></a>  wstreampos  
 Содержит текущее положение указателя буфера или указателя файла.  
  
```  
typedef fpos<mbstate_t> wstreampos;  
```  
  
### <a name="remarks"></a>Примечания  
 Тип является синонимом для [fpos](../standard-library/fpos-class.md)< `mbstate_t`>.  
  
### <a name="example"></a>Пример  
  
```cpp  
// ios_wstreampos.cpp  
// compile with: /EHsc  
#include <iostream>  
#include <fstream>  
  
int main( )   
{  
   using namespace std;  
   wofstream xw( "wiostream.txt" );  
   xw << L"testing";  
   wstreampos y = xw.tellp( );  
   cout << y << endl;  
}  
```  
  
```Output  
7  
```  
  
## <a name="see-also"></a>См. также  
 [\<ios>](../standard-library/ios.md)


