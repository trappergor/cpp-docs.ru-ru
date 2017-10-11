---
title: "Указатели const и volatile | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- volatile keyword [C++], and pointers
- pointers, and const
- pointers, and volatile
- const keyword [C++], volatile pointers
ms.assetid: 0c92dc6c-400e-4342-b345-63ddfe649d7e
caps.latest.revision: 10
author: mikeblome
ms.author: mblome
manager: ghogen
ms.translationtype: HT
ms.sourcegitcommit: 6ffef5f51e57cf36d5984bfc43d023abc8bc5c62
ms.openlocfilehash: bebd757f304de2377ab2337e5b41a577a2b492b6
ms.contentlocale: ru-ru
ms.lasthandoff: 09/25/2017

---
# <a name="const-and-volatile-pointers"></a>Указатели с ключевыми словами const и volatile
[Const](../cpp/const-cpp.md) и [volatile](../cpp/volatile-cpp.md) ключевые слова изменить способы обработки указателей. **Const** ключевое слово указывает, что указатель невозможно изменить после инициализации; он защищен от последующих изменений.  
  
 Ключевое слово `volatile` указывает, что значение, связанное с указанным после него именем, может быть изменено различными действиями (но не через пользовательское приложение). Таким образом, ключевое слово `volatile` полезно для объявления объектов в общей памяти, обращаться к которым могут несколько процессов или глобальных областей данных, используемых для обмена данными с процедурами службы прерываний.  
  
 Если имя объявляется как `volatile`, то каждый раз, когда программа обращается к значению, компилятор перезагружает его из памяти. Это значительно сокращает возможности оптимизации. Однако если состояние объекта может неожиданно изменяться, то это единственный способ гарантировать предсказуемую производительность программы.  
  
 Для объявления объекта, на который указывает указатель как **const** или `volatile`, используйте объявление следующего вида:  
  
```  
const char *cpch;  
volatile char *vpch;  
```  
  
 Чтобы объявить значение указателя — то есть, сохраненное в указателе фактический адрес — как **const** или `volatile`, используйте объявление следующего вида:  
  
```  
char * const pchc;  
char * volatile pchv;  
```  
  
 Язык C++ предотвращает присваивания, которые могут допустить изменение объекта или указателя, объявленного как **const**. Такие присваивания могут удалить информацию, с которой был объявлен объект или указатель, и тем самым подменить смысл исходного объявления. Рассмотрим следующее объявление:  
  
```  
const char cch = 'A';  
char ch = 'B';  
```  
  
 Учитывая приведенные выше объявления двух объектов (`cch`, типа **const char**, и `ch`, типа **char)**, допустимы следующие объявления и инициализации:  
  
```  
const char *pch1 = &cch;  
const char *const pch4 = &cch;  
const char *pch5 = &ch;  
char *pch6 = &ch;  
char *const pch7 = &ch;  
const char *const pch8 = &ch;  
```  
  
 Следующие объявления и инициализации вызывают ошибки.  
  
```  
char *pch2 = &cch;   // Error  
char *const pch3 = &cch;   // Error  
```  
  
 В объявлении `pch2` задается указатель, при помощи которого может быть изменен постоянный объект, поэтому это объявление запрещено. В объявлении `pch3` указано, что постоянным является не объект, а указатель (параметр `pointer`). Это объявление запрещено по той же причине, что и объявление `pch2`.  
  
 В следующих восьми примерах демонстрируется присваивание через указатель и изменение значения указателя для приведенных выше объявлений. Здесь мы предполагаем, что инициализация указателей `pch1`–`pch8` была выполнена без ошибок.  
  
```  
*pch1 = 'A';  // Error: object declared const  
pch1 = &ch;   // OK: pointer not declared const  
*pch2 = 'A';  // OK: normal pointer  
pch2 = &ch;   // OK: normal pointer  
*pch3 = 'A';  // OK: object not declared const  
pch3 = &ch;   // Error: pointer declared const  
*pch4 = 'A';  // Error: object declared const  
pch4 = &ch;   // Error: pointer declared const  
```  
  
 Указатели, объявленные как `volatile`, или сочетанием **const** и `volatile`, подчиняются тем же правилам.  
  
 Указатели на **const** объектов часто используются в объявлениях функций следующим образом:  
  
```  
errno_t strcpy_s( char *strDestination, size_t numberOfElements, const char *strSource );  
```  
  
 Выше инструкции объявляется функция, [strcpy_s](../c-runtime-library/reference/strcpy-s-wcscpy-s-mbscpy-s.md), в которой два из трех аргументов являются тип указателя на `char`. Так как аргументы передаются по ссылке, а не по значению, функция могла бы свободно изменить и `strDestination` и `strSource` Если `strSource` не были объявлены как **const**. Объявление `strSource` как **const** вызывающий объект гарантирует, что `strSource` вызываемая функция не может быть изменено.  
  
> [!NOTE]
>  Поскольку стандартное преобразование из *typename* ** \* ** для **const** *typename* ** \* **, можно передать аргумент типа **char \* ** для [strcpy_s](../c-runtime-library/reference/strcpy-s-wcscpy-s-mbscpy-s.md). Однако обратное неверно; неявные преобразования не существует для удаления **const** атрибут из объекта или указателя.  
  
 Объект **const** указатель данного типа могут быть назначены указатель того же типа. Однако указатель, не **const** не может быть назначен **const** указателя. В следующем коде показано одно верное и одно неверное присваивание.  
  
```  
// const_pointer.cpp  
int *const cpObject = 0;  
int *pObject;  
  
int main() {  
pObject = cpObject;  
cpObject = pObject;   // C3892  
}  
```  
  
 В следующем примере показано, как объявить объект как const, когда имеется указатель на указатель на объект.  
  
```  
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
