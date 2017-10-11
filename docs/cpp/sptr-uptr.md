---
title: "__sptr __uptr | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- __uptr_cpp
- __sptr_cpp
dev_langs:
- C++
helpviewer_keywords:
- __sptr modifier
- __uptr modifier
ms.assetid: c7f5f3b2-9106-4a0b-a6de-d1588ab153ed
caps.latest.revision: 7
author: mikeblome
ms.author: mblome
manager: ghogen
ms.translationtype: HT
ms.sourcegitcommit: 6ffef5f51e57cf36d5984bfc43d023abc8bc5c62
ms.openlocfilehash: 684b9533c57d7c0ca90f18bc82f2cf6ddb65bc8e
ms.contentlocale: ru-ru
ms.lasthandoff: 09/25/2017

---
# <a name="sptr-uptr"></a>__sptr, __uptr
## <a name="microsoft-specific"></a>Блок, относящийся только к системам Microsoft  
 Используйте модификатор `__sptr` или `__uptr` при объявлении 32-разрядного указателя, чтобы определить, как компилятор преобразует 32-разрядный указатель в 64-разрядный. 32-разрядный указатель преобразуется, например, при присвоении 64-разрядной переменной или при разыменовывании на 64-разрядной платформе.  
  
 В документации корпорации Microsoft по поддержке 64-разрядных платформ иногда старший значащий бит 32-разрядного указателя называется знаковым битом. По умолчанию компилятор использует расширение знака для преобразования 32-разрядного указателя в 64-разрядный. При этом для младших значащих 32 битов 64-разрядного указателя устанавливается значение 32-разрядного указателя, а для старших значащих 32 битов устанавливается значение знакового бита 32-разрядного указателя. Такое преобразование дает правильные результаты, если знаковый бит равен 0, но если он равен 1, то результаты получаются неправильные. Например, 32-разрядный адрес 0x7FFFFFFF преобразуется в эквивалентный 64-разрядный адрес 0x000000007FFFFFFF, а 32-разрядный адрес 0x80000000 ошибочно преобразуется в 0xFFFFFFFF80000000.  
  
 Модификатор `__sptr` (или "указатель со знаком") указывает, что при преобразовании для старших значащих битов 64-разрядного указателя присваивается значение знакового бита 32-разрядного указателя. Модификатор `__uptr` (или указатель без знака) указывает, что при преобразовании для старших значащих битов устанавливается нулевое значение. В следующих объявлениях показано `__sptr` и `__uptr` модификаторы, используемые с двумя указателями без квалификаторов, двумя указателями с квалификаторами [__ptr32](../cpp/ptr32-ptr64.md) типа и параметра функции.  
  
```  
int * __sptr psp;  
int * __uptr pup;  
int * __ptr32 __sptr psp32;  
int * __ptr32 __uptr pup32;  
void MyFunction(char * __uptr __ptr32 myValue);  
```  
  
 Модификаторы `__sptr` и `__uptr` используются в объявлениях указателей. Используйте модификаторы позиции [квалификатора типа указателя](../c-language/pointer-declarations.md), означающее модификатор должны следовать символ звездочки. Невозможно использовать модификаторы с [указателей на члены](../cpp/pointers-to-members.md). Модификаторы не влияют на объявления, не являющиеся объявлениями указателей.  
  
## <a name="example"></a>Пример  
 В следующем примере объявляются 32-разрядные указатели с модификаторами `__sptr` и `__uptr`, каждый 32-разрядный указатель присваивается переменной, являющейся 64-разрядным указателем, затем отображаются шестнадцатеричные значения для каждого 64-разрядного указателя. Пример компилировался с помощью собственного 64-разрядного компилятора и выполнялся на 64-разрядной платформе.  
  
```cpp  
// sptr_uptr.cpp  
// processor: x64  
#include "stdio.h"  
  
int main()  
{  
    void *        __ptr64 p64;  
    void *        __ptr32 p32d; //default signed pointer  
    void * __sptr __ptr32 p32s; //explicit signed pointer  
    void * __uptr __ptr32 p32u; //explicit unsigned pointer  
  
// Set the 32-bit pointers to a value whose sign bit is 1.  
    p32d = reinterpret_cast<void *>(0x87654321);  
    p32s = p32d;  
    p32u = p32d;  
  
// The printf() function automatically displays leading zeroes with each 32-bit pointer. These are unrelated   
// to the __sptr and __uptr modifiers.   
    printf("Display each 32-bit pointer (as an unsigned 64-bit pointer):\n");  
    printf("p32d:       %p\n", p32d);   
    printf("p32s:       %p\n", p32s);  
    printf("p32u:       %p\n", p32u);  
  
    printf("\nDisplay the 64-bit pointer created from each 32-bit pointer:\n");  
    p64 = p32d;   
    printf("p32d: p64 = %p\n", p64);  
    p64 = p32s;  
    printf("p32s: p64 = %p\n", p64);  
    p64 = p32u;  
    printf("p32u: p64 = %p\n", p64);  
    return 0;  
}  
```  
  
```Output  
Display each 32-bit pointer (as an unsigned 64-bit pointer):  
p32d:       0000000087654321  
p32s:       0000000087654321  
p32u:       0000000087654321  
  
Display the 64-bit pointer created from each 32-bit pointer:  
p32d: p64 = FFFFFFFF87654321  
p32s: p64 = FFFFFFFF87654321  
p32u: p64 = 0000000087654321  
```  
  
**Завершение блока, относящегося только к системам Майкрософт**  
  
## <a name="see-also"></a>См. также  
 [Модификаторы, используемые в системах Майкрософт](../cpp/microsoft-specific-modifiers.md)
