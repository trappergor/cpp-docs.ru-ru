---
title: "На основе указателей (C++) | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- __based
- __based_cpp
dev_langs:
- C++
helpviewer_keywords:
- __based keyword [C++]
- based pointers
- pointers, based
ms.assetid: 1e5f2e96-c52e-4738-8e14-87278681205e
caps.latest.revision: 10
author: mikeblome
ms.author: mblome
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
ms.translationtype: HT
ms.sourcegitcommit: 6ffef5f51e57cf36d5984bfc43d023abc8bc5c62
ms.openlocfilehash: f3ba9e269a01fb4c10cce9417032ec47c1b3c158
ms.contentlocale: ru-ru
ms.lasthandoff: 09/25/2017

---
# <a name="based-pointers-c"></a>Основанные указатели (C++)
**Блок, относящийся только к системам Майкрософт**  
  
 Ключевое слово `__based` позволяет объявлять указатели на основе указателей (указатели со смещением относительно существующих указателей).  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
type __based( base ) declarator   
```  
  
## <a name="remarks"></a>Примечания  
 Указатели, основанные на адресах указателей, являются единственной формой ключевого слова `__based`, допустимой в 32- или 64-разрядных компиляциях. В 32-разрядном компиляторе Microsoft C/C++ относительный указатель имеет 32-разрядное смещение от 32-разрядной базы указателя. То же ограничение действует и для 64-разрядных сред, где относительный указатель имеет 64-разрядное смещение от 64-разрядной базы указателя.  
  
 Указатели на основе указателей, в частности, используются для постоянных идентификаторов, которые содержат указатели. Связанный список, состоящий из указателей на основе указателей, можно сохранить на диск, а затем перезагрузить в другое место в памяти. При этом все указатели останутся действительными. Например:  
  
```  
// based_pointers1.cpp  
// compile with: /c  
void *vpBuffer;  
struct llist_t {  
   void __based( vpBuffer ) *vpData;  
   struct llist_t __based( vpBuffer ) *llNext;  
};  
```  
  
 Указателю `vpBuffer` назначается адрес в памяти, который выделяется на более позднем этапе программы. Связанный список перемещается относительно значения `vpBuffer`.  
  
> [!NOTE]
>  Постоянные идентификаторы, содержащие указатели можно также с помощью [сопоставленные в памяти файлы](http://msdn.microsoft.com/library/windows/desktop/aa366556).  
  
 Когда выполняется разыменовывание относительных указателей, база должна быть либо явно указана, либо неявно известна из объявления.  
  
 Для обеспечения совместимости с предыдущими версиями **_based** является синонимом `__based`.  
  
## <a name="example"></a>Пример  
 В следующем примере демонстрируется изменение относительного указателя путем изменения его базы.  
  
```  
// based_pointers2.cpp  
// compile with: /EHsc  
#include <iostream>  
  
int a1[] = { 1,2,3 };  
int a2[] = { 10,11,12 };  
int *pBased;  
  
typedef int __based(pBased) * pBasedPtr;  
  
using namespace std;  
int main() {  
   pBased = &a1[0];  
   pBasedPtr pb = 0;  
  
   cout << *pb << endl;  
   cout << *(pb+1) << endl;  
  
   pBased = &a2[0];  
  
   cout << *pb << endl;  
   cout << *(pb+1) << endl;  
}  
```  
  
```Output  
1  
2  
10  
11  
```  
  
## <a name="see-also"></a>См. также  
 [Ключевые слова](../cpp/keywords-cpp.md)   
 [alloc_text](../preprocessor/alloc-text.md)
