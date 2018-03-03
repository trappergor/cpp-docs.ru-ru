---
title: "Декларатор ссылки lvalue: &amp; | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- '&'
dev_langs:
- C++
helpviewer_keywords:
- reference operator
- '& operator [C++], reference operator'
ms.assetid: edf0513d-3dcc-4663-b276-1269795dda51
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 5bea07ed3139240279848d94184564ec821a8cd9
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="lvalue-reference-declarator-amp"></a>Декларатор ссылки lvalue:&amp;
Содержит адрес объекта, но синтаксически ведет себя подобно объекту.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
type-id & cast-expression  
```  
  
## <a name="remarks"></a>Примечания  
 Ссылку lvalue можно считать другим именем для объекта. Объявление ссылки lvalue состоит из необязательного списка спецификаторов, за которым следует декларатор ссылки. Ссылка должна быть инициализирована и не может быть изменена.  
  
 Любой объект, адрес которого можно преобразовать в некоторый тип указателя, можно также преобразовать в аналогичный ссылочный тип. Например, любой объект, адрес которого можно преобразовать в тип `char *`, можно также преобразовать в тип `char &`.  
  
 Не путайте объявления ссылки с использованием [оператор address-of](../cpp/address-of-operator-amp.md). Когда `&` *идентификатор* предшествуют типа, таких как `int` или `char`, *идентификатор* объявляется как ссылка на тип. Когда `&` *идентификатор* не предшествует типом, использование аналогично оператора взятия адреса.  
  
## <a name="example"></a>Пример  
 В следующем примере демонстрируется декларатор ссылки путем объявления объекта `Person` и ссылки на этот объект. Поскольку `rFriend` является ссылкой на `myFriend`, при обновлении любой из этих переменных изменяется один и тот же объект.  
  
```  
// reference_declarator.cpp  
// compile with: /EHsc  
// Demonstrates the reference declarator.  
#include <iostream>  
using namespace std;  
  
struct Person  
{  
    char* Name;  
    short Age;  
};  
  
int main()  
{  
   // Declare a Person object.  
   Person myFriend;  
  
   // Declare a reference to the Person object.  
   Person& rFriend = myFriend;  
  
   // Set the fields of the Person object.  
   // Updating either variable changes the same object.  
   myFriend.Name = "Bill";  
   rFriend.Age = 40;  
  
   // Print the fields of the Person object to the console.  
   cout << rFriend.Name << " is " << myFriend.Age << endl;  
}  
```  
  
```Output  
Bill is 40  
```  
  
## <a name="see-also"></a>См. также  
 [Ссылки](../cpp/references-cpp.md)   
 [Аргументы функции ссылочного типа](../cpp/reference-type-function-arguments.md)   
 [Возвращаемые значения функции ссылочного типа](../cpp/reference-type-function-returns.md)   
 [Ссылки на указатели](../cpp/references-to-pointers.md)