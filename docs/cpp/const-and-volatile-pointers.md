---
title: Указатели const и volatile | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- volatile keyword [C++], and pointers
- pointers, and const
- pointers, and volatile
- const keyword [C++], volatile pointers
ms.assetid: 0c92dc6c-400e-4342-b345-63ddfe649d7e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: e32312e8c6f3dc149f6e5e1f8dc37b1395732d02
ms.sourcegitcommit: 2b9e8af9b7138f502ffcba64e2721f7ef52af23b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/01/2018
ms.locfileid: "39408194"
---
# <a name="const-and-volatile-pointers"></a>Указатели с ключевыми словами const и volatile
[Const](../cpp/const-cpp.md) и [volatile](../cpp/volatile-cpp.md) ключевые слова изменить способы обработки указателей. **Const** ключевое слово указывает, что указатель невозможно изменить после инициализации; он защищен от последующих изменений.  
  
 **Volatile** ключевое слово указывает, что значение, связанное с указанное после него имя можно изменить на действия, кроме тех, в приложении пользователя. Таким образом **volatile** ключевое слово используется для объявления объектов в общей памяти, может осуществляться несколькими процессами или областей глобальных данных, используемых для обмена данными с процедурами службы прерываний.  
  
 Если имя объявляется как **volatile**, компилятор перезагружает его из памяти при каждом доступе с помощью программы. Это значительно сокращает возможности оптимизации. Однако если состояние объекта может неожиданно изменяться, то это единственный способ гарантировать предсказуемую производительность программы.  
  
 Чтобы объявить объект, на которые указывает указатель в виде **const** или **volatile**, используйте объявление следующего вида:  
  
```cpp 
const char *cpch;  
volatile char *vpch;  
```  
  
 Чтобы объявить значение указателя — то есть фактический адрес, сохраненное в указателе — как **const** или **volatile**, используйте объявление следующего вида:  
  
```cpp 
char * const pchc;  
char * volatile pchv;  
```  
  
 Язык C++ предотвращает присваивания, которые могут допустить изменение объекта или указателя, объявленного как **const**. Такие присваивания могут удалить информацию, с которой был объявлен объект или указатель, и тем самым подменить смысл исходного объявления. Рассмотрим следующее объявление:  
  
```cpp 
const char cch = 'A';  
char ch = 'B';  
```  
  
 Учитывая приведенные выше объявления двух объектов (`cch`, типа **const char**, и `ch`, типа **char)**, следующие объявления и инициализации являются допустимыми:  
  
```cpp 
const char *pch1 = &cch;  
const char *const pch4 = &cch;  
const char *pch5 = &ch;  
char *pch6 = &ch;  
char *const pch7 = &ch;  
const char *const pch8 = &ch;  
```  
  
 Следующие объявления и инициализации вызывают ошибки.  
  
```cpp 
char *pch2 = &cch;   // Error  
char *const pch3 = &cch;   // Error  
```  
  
 В объявлении `pch2` задается указатель, при помощи которого может быть изменен постоянный объект, поэтому это объявление запрещено. Объявление `pch3` указывает, что указатель является константой, не объект, объявление запрещено по той же причине `pch2` объявление запрещено.  
  
 В следующих восьми примерах демонстрируется присваивание через указатель и изменение значения указателя для приведенных выше объявлений. Здесь мы предполагаем, что инициализация указателей `pch1`–`pch8` была выполнена без ошибок.  
  
```cpp 
*pch1 = 'A';  // Error: object declared const  
pch1 = &ch;   // OK: pointer not declared const  
*pch2 = 'A';  // OK: normal pointer  
pch2 = &ch;   // OK: normal pointer  
*pch3 = 'A';  // OK: object not declared const  
pch3 = &ch;   // Error: pointer declared const  
*pch4 = 'A';  // Error: object declared const  
pch4 = &ch;   // Error: pointer declared const  
```  
  
 Указатели, объявленные как **volatile**, или сочетанием **const** и **volatile**, подчиняются тем же правилам.  
  
 Указатели на **const** объекты часто используются в объявлениях функций следующим образом:  
  
```cpp 
errno_t strcpy_s( char *strDestination, size_t numberOfElements, const char *strSource );  
```  
  
 Предыдущая инструкция объявляет функцию, [strcpy_s](../c-runtime-library/reference/strcpy-s-wcscpy-s-mbscpy-s.md), в которых два из трех аргументов являются типа pointer в **char**. Так как аргументы передаются по ссылке, а не по значению, функция могла бы свободно изменить и `strDestination` и `strSource` Если `strSource` не были объявлены как **const**. Объявление `strSource` как **const** вызывающий объект гарантирует, что `strSource` нельзя изменить вызываемой функцией.  
  
> [!NOTE]
>  Так как стандартное преобразование из *typename* **\*** для **const** *typename* **\***, можно передать аргумент типа `char *` для [strcpy_s](../c-runtime-library/reference/strcpy-s-wcscpy-s-mbscpy-s.md). Однако обратное неверно; неявные преобразования не существует для удаления **const** атрибут из объекта или указателя.  
  
 Объект **const** указатель заданного типа могут быть назначены указатель того же типа. Тем не менее, указатель, не **const** не могут быть назначены **const** указатель. В следующем коде показано одно верное и одно неверное присваивание.  
  
```cpp 
// const_pointer.cpp  
int *const cpObject = 0;  
int *pObject;  
  
int main() {  
pObject = cpObject;  
cpObject = pObject;   // C3892  
}  
```  
  
 В следующем примере показано, как объявить объект как const, когда имеется указатель на указатель на объект.  
  
```cpp 
// const_pointer2.cpp  
struct X {  
   X(int i) : m_i(i) { }  
   int m_i;  
};  
  
int main() {  
   // correct  
   const X cx(10);  
   const X * pcx = &cx;  
   const X ** ppcx = &pcx;  
  
   // also correct  
   X const cx2(20);  
   X const * pcx2 = &cx2;  
   X const ** ppcx2 = &pcx2;  
}  
```  
  
## <a name="see-also"></a>См. также  
 [Указатели](../cpp/pointers-cpp.md)