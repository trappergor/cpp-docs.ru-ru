---
title: Операторы сдвига влево и вправо (&gt; &gt; и &lt; &lt;) | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-language
ms.tgt_pltfrm: ''
ms.topic: language-reference
f1_keywords:
- <<
- '>>'
dev_langs:
- C++
helpviewer_keywords:
- << operator [C++], with specific objects
- left shift operators [C++]
- right shift operators [C++]
- bitwise-shift operators [C++]
- '>> operator'
- shift operators [C++]
- operators [C++], shift
ms.assetid: 25fa0cbb-5fdd-4657-8745-b35f7d8f1606
caps.latest.revision: 18
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 7dece9ac4045fa8b46e5edf8b266312242000229
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="left-shift-and-right-shift-operators-gtgt-and-ltlt"></a>Операторы сдвига влево и вправо (&gt; &gt; и &lt; &lt;)
Операторы побитового сдвига являются оператором сдвига вправо (>>), который перемещает биты *выражение сдвига* оператор сдвига влево и вправо (<<), который перемещает биты *выражение сдвига* влево. <sup>1</sup>  
  
## <a name="syntax"></a>Синтаксис  
  
> *выражение сдвига* `<<` *выражение сложения*  
> *выражение сдвига* `>>` *выражение сложения*  
  
## <a name="remarks"></a>Примечания  
  
> [!IMPORTANT]
> Следующие описания и примеры распространяются на Windows для архитектур x86 и x64. Реализация операторов сдвига влево и сдвига вправо существенно отличается в Windows RT для устройств ARM. Дополнительные сведения см. раздел «Операторы сдвига» [Hello ARM](http://blogs.msdn.com/b/vcblog/archive/2012/10/25/hello-arm-exploring-undefined-unspecified-and-implementation-defined-behavior-in-c.aspx) записи блога.  
  
## <a name="left-shifts"></a>Сдвиги влево  
 Оператор сдвига влево вызывает сдвиг битов в *выражение сдвига* сдвиг влево на количество разрядов, указанных в *выражение сложения*. Позиции битов, освобожденные при операции сдвига, заполняются нулями. Сдвиг влево является логическим сдвигом (биты, сдвигаемые с конца отбрасываются, включая бит знака). Дополнительные сведения о типах побитовых сдвигов см. в разделе [побитовые сдвиги](http://en.wikipedia.org/wiki/Bitwise_shift).  
  
 В следующем примере показаны операции сдвига влево с использованием чисел без знака. В этом примере показано, что происходит с битами при представлении значения как bitset. Дополнительные сведения см. в разделе [класс bitset](../standard-library/bitset-class.md).  
  
```cpp  
#include <iostream>  
#include <bitset>  
using namespace std;  
  
int main() {  
    unsigned short short1 = 4;      
    bitset<16> bitset1{short1};   // the bitset representation of 4  
    cout << bitset1 << endl;  // 0000000000000100  
  
    unsigned short short2 = short1 << 1;     // 4 left-shifted by 1 = 8  
    bitset<16> bitset2{short2};  
    cout << bitset2 << endl;  // 0000000000001000  
  
    unsigned short short3 = short1 << 2;     // 4 left-shifted by 2 = 16  
    bitset<16> bitset3{short3};  
    cout << bitset3 << endl;  // 0000000000010000  
}  
  
```  
  
 Если выполняется сдвиг влево числа со знаком и при этом затрагивается бит знака, результат не определен. В следующем примере показано, что происходит в Visual C++, если выполняется сдвиг влево 1 бита в позицию бита знака.  
  
```cpp  
#include <iostream>  
#include <bitset>  
using namespace std;  
  
int main() {  
    short short1 = 16384;      
    bitset<16> bitset1{short2};  
    cout << bitset1 << endl;  // 0100000000000000   
  
    short short3 = short1 << 1;  
    bitset<16> bitset3{short3};  // 16384 left-shifted by 1 = -32768  
    cout << bitset3 << endl;  // 100000000000000  
  
    short short4 = short1 << 14;  
    bitset<16> bitset4{short4};  // 4 left-shifted by 14 = 0  
    cout << bitset4 << endl;  // 000000000000000    
}  
```  
  
## <a name="right-shifts"></a>Сдвиги вправо  
 Оператор сдвига вправо вызывает битов в *выражение сдвига* сдвиг вправо на количество разрядов, указанных в *выражение сложения*. Для чисел без знака позиции битов, освобожденные при операции сдвига, заполняются нулями. Для чисел со знаком бит знака используется для заполнения освобожденных позиций битов. Другими словами, если число является положительным, используется 0, если число является отрицательным, используется 1.  
  
> [!IMPORTANT]
> Результат сдвига вправо отрицательного числа со знаком зависит от реализации. Хотя Visual C++ использует бит знака для заполнения освобожденных позиций битов, нет никакой гарантии, что другие реализации также выполняют это.  
  
 В следующем примере показаны операции сдвига вправо с использованием чисел без знака.  
  
```cpp  
#include <iostream>  
#include <bitset>  
using namespace std;  
  
int main() {  
    unsigned short short11 = 1024;  
    bitset<16> bitset11{short11};  
    cout << bitset11 << endl;     // 0000010000000000  
  
    unsigned short short12 = short11 >> 1;  // 512  
    bitset<16> bitset12{short12};  
    cout << bitset12 << endl;     // 0000001000000000  
  
    unsigned short short13 = short11 >> 10;  // 1  
    bitset<16> bitset13{short13};  
    cout << bitset13 << endl;     // 0000000000000001  
  
    unsigned short short14 = short11 >> 11;  // 0  
    bitset<16> bitset14{short14};  
    cout << bitset14 << endl;     // 0000000000000000}  
}  
```  
  
 В следующем примере показаны операции сдвига вправо с использованием положительных чисел со знаком.  
  
```cpp  
#include <iostream>  
#include <bitset>  
using namespace std;  
  
int main() {  
    short short1 = 1024;  
    bitset<16> bitset1{short1};  
    cout << bitset1 << endl;     // 0000010000000000  
  
    short short2 = short1 >> 1;  // 512  
    bitset<16> bitset2{short2};  
    cout << bitset2 << endl;     // 0000001000000000  
  
    short short3 = short1 >> 11;  // 0  
    bitset<16> bitset3{short3};     
    cout << bitset3 << endl;     // 0000000000000000  
}  
```  
  
 В следующем примере показаны операции сдвига вправо с использованием отрицательных целых чисел со знаком.  
  
```cpp  
#include <iostream>  
#include <bitset>  
using namespace std;  
  
int main() {  
    short neg1 = -16;  
    bitset<16> bn1{neg1};  
    cout << bn1 << endl;  // 1111111111110000  
  
    short neg2 = neg1 >> 1; // -8  
    bitset<16> bn2{neg2};  
    cout << bn2 << endl;  // 1111111111111000  
  
    short neg3 = neg1 >> 2; // -4  
    bitset<16> bn3{neg3};  
    cout << bn3 << endl;  // 1111111111111100  
  
    short neg4 = neg1 >> 4; // -1  
    bitset<16> bn4{neg4};      
    cout << bn4 << endl;  // 1111111111111111  
  
    short neg5 = neg1 >> 5; // -1   
    bitset<16> bn5{neg5};      
    cout << bn5 << endl;  // 1111111111111111  
}  
```  
  
## <a name="shifts-and-promotions"></a>Сдвиги и перемещения  
 Выражения с обеих сторон оператора сдвига должны быть целочисленными типами. Восходящие приведения целых типов выполняются согласно правилам, описанным в [стандартные преобразования](standard-conversions.md). Тип результата совпадает со значением типу приводимого *выражение сдвига*.  
  
 В следующем примере у переменной типа `char` уровень повышается до `int`.  
  
```cpp  
#include <iostream>  
#include <typeinfo>  
  
using namespace std;  
  
int main() {  
    char char1 = 'a';  
  
    auto promoted1 = char1 << 1;   // 194  
    cout << typeid(promoted1).name() << endl;  // int  
  
    auto promoted2 = char1 << 10;  // 99328  
    cout << typeid(promoted2).name() << endl;  // int  
}  
```  
  
## <a name="additional-details"></a>Некоторые подробности  
 Результат операции сдвига не определен, если *выражение сложения* является отрицательным или если *выражение сложения* больше или равно числу битов в повышаемом  *выражение сдвига*. Операция сдвига не выполняется при *выражение сложения* — 0.  
  
```cpp  
#include <iostream>  
#include <bitset>  
using namespace std;  
  
int main() {  
    unsigned int int1 = 4;  
    bitset<32> b1{int1};  
    cout << b1 << endl;    // 00000000000000000000000000000100  
  
    unsigned int int2 = int1 << -3;  // C4293: '<<' : shift count negative or too big, undefined behavior  
    unsigned int int3 = int1 >> -3;  // C4293: '>>' : shift count negative or too big, undefined behavior  
  
    unsigned int int4 = int1 << 32;  // C4293: '<<' : shift count negative or too big, undefined behavior  
  
    unsigned int int5 = int1 >> 32;  // C4293: '>>' : shift count negative or too big, undefined behavior  
  
    unsigned int int6 = int1 << 0;  
    bitset<32> b6{int6};  
    cout << b6 << endl;    // 00000000000000000000000000000100 (no change)}  
}  
```  
  
## <a name="footnotes"></a>Примечания  
 1 ниже приводится описание операторов сдвига в C ++ 11 спецификации ISO (INCITS/ISO/IEC 14882-2011[2012]), разделы 5.8.2 и 5.8.3.  
  
 Значение **E1 << E2** — **E1** сдвиг влево **E2** позиций битов; освобожденные биты заполняются нулями. Если **E1** имеет тип без знака, результат равен **E1 × 2**<sup>**E2**</sup>, уменьшенное на остаток от деления на единицу больше, чем максимальное значение, которое может быть представлено в Тип результата. В противном случае, если **E1** имеет тип со знаком и неотрицательное значение и **E1 × 2**<sup>**E2** </sup> можно представить в соответствующий тип без знака для типа результата затем это значение, преобразованное в тип результата, будет значением результата; в противном случае поведение не определено.  
  
 Значение **E1 >> E2** — **E1** сдвигом вправо **E2** позиций битов. Если **E1** имеет тип без знака или если **E1** имеет тип со знаком и неотрицательное значение, значение результата является неотъемлемой частью частное **E1/2** <sup> **E2**</sup>. Если **E1** имеет тип со знаком и отрицательное значение, результат определяется реализацией.  
  
## <a name="see-also"></a>См. также  
 [Выражения с бинарными операторами](../cpp/expressions-with-binary-operators.md)   
 [Встроенные операторы C++, приоритет и ассоциативность](../cpp/cpp-built-in-operators-precedence-and-associativity.md)