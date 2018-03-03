---
title: "Оператор delete (C++) | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- delete_cpp
dev_langs:
- C++
helpviewer_keywords:
- delete keyword [C++], syntax
- delete keyword [C++], deallocating objects
- delete keyword [C++]
ms.assetid: de39c900-3f57-489c-9598-dcb73c4b3930
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 36da346329341221d43af2ec96aa17be4f819bf8
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="delete-operator-c"></a>Оператор delete (C++)
Отменяет выделение блока памяти.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
[::] delete cast-expression  
[::] delete [ ] cast-expression  
```  
  
## <a name="remarks"></a>Примечания  
 *Выражение приведения* аргумент должен быть указателем на блок памяти, ранее выделенный объекту, созданному с [оператор new](../cpp/new-operator-cpp.md). **Удаление** оператор имеет результат типа `void` и поэтому не возвращает значение. Пример:  
  
```  
CDialog* MyDialog = new CDialog;  
// use MyDialog  
delete MyDialog;  
```  
  
 С помощью **удаление** на указатель на объект, который не выделен с помощью **новый** дает непредсказуемые результаты. Однако, можно использовать **удалить** на указателе со значением 0. Это означает, что, когда **новый** возвращает 0 в случае сбоя в результате сбоя при удалении **новый** операции не опасное. В разделе [новый и удаление операторов](../cpp/new-and-delete-operators.md) для получения дополнительной информации.  
  
 **Новый** и **удалить** операторы могут также использоваться для встроенных типов, включая массивы. Если указатель (параметр `pointer`) относится к массиву, то перед эти параметром `pointer` ставятся пустые скобки:  
  
```  
int* set = new int[100];  
//use set[]  
delete [] set;  
```  
  
 С помощью **удалить** оператор на объекте отменяется выделение памяти. Программа, которая разыменовывает указатель после удаления объекта, может создать непрогнозируемый результат или вызвать сбой.  
  
 Когда **удалить** — используется для освобождения памяти для объекта класса C++, деструктор объекта вызывается до освобождения памяти объекта (если объект имеет деструктор).  
  
 Если операнд **удалить** оператор является изменяемым l значением, его значение не определено, после удаления объекта.  
  
## <a name="using-delete"></a>Использование оператора delete  
 Существует два синтаксический варианта [оператор delete](../cpp/delete-operator-cpp.md): один для отдельных объектов и другой для массивов объектов. В следующем фрагменте кода показано, чем они отличаются:  
  
```  
// expre_Using_delete.cpp  
struct UDType   
{  
};  
  
int main()  
{  
   // Allocate a user-defined object, UDObject, and an object  
   //  of type double on the free store using the  
   //  new operator.  
   UDType *UDObject = new UDType;  
   double *dObject = new double;  
   // Delete the two objects.  
   delete UDObject;  
   delete dObject;   
   // Allocate an array of user-defined objects on the  
   // free store using the new operator.  
   UDType (*UDArr)[7] = new UDType[5][7];  
   // Use the array syntax to delete the array of objects.  
   delete [] UDArr;  
}  
```  
  
 Следующие два случая дают неопределенный результат: использование формы, предназначенной для массивов (delete [ ]), для удаления одиночного объекта и использовании формы, не предназначенной для массивов, для удаления массива.  
  
## <a name="example"></a>Пример  
 Примеры использования **удаление**, в разделе [оператор new](../cpp/new-operator-cpp.md).  
  
## <a name="how-delete-works"></a>Принцип работы delete  
 Оператор delete вызывает функцию **оператор delete**.  
  
 Для объектов, не имеющих типа класса ([класса](../cpp/class-cpp.md), [структуры](../cpp/struct-cpp.md), или [объединение](../cpp/unions.md)), вызывается глобальный оператор delete. Для объектов типа класса имя функции освобождения разрешается в глобальной области, если выражение удаления начинается с унарного оператора разрешения области действия (::). В противном случае перед освобождением памяти оператор удаления вызывает деструктор объекта (если указатель не имеет значения null). Оператор удаления можно определять отдельно для каждого класса; если для некоторого класса такое определение отсутствует, вызывается глобальный оператор удаления. Если выражение удаления используется для освобождения объекта класса, статический тип которого имеет виртуальный деструктор, функция освобождение разрешается через виртуальный деструктор динамического типа объекта.  
  
## <a name="see-also"></a>См. также  
 [Выражения с унарными операторами](../cpp/expressions-with-unary-operators.md)   
 [Ключевые слова](../cpp/keywords-cpp.md)   
 [Операторы new и delete](../cpp/new-and-delete-operators.md)   
 
