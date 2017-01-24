---
title: "Оператор delete (C++) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "delete_cpp"
  - "delete"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "delete - ключевое слово [C++]"
  - "delete - ключевое слово [C++], освобождение объектов"
  - "delete - ключевое слово [C++], синтаксис"
ms.assetid: de39c900-3f57-489c-9598-dcb73c4b3930
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Оператор delete (C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Отменяет выделение блока памяти.  
  
## Синтаксис  
  
```  
[::] delete cast-expression  
[::] delete [ ] cast-expression  
```  
  
## Заметки  
 Аргумент *выражение\-приведения\-типа* должен быть указателем на блок памяти, ранее выделенный объекту, созданному при помощи оператора [new](../cpp/new-operator-cpp.md).  Оператор **delete** создает результат типа `void` и не возвращает значения.  Пример:  
  
```  
CDialog* MyDialog = new CDialog;  
// use MyDialog  
delete MyDialog;  
```  
  
 Использование оператора **delete** на указателе на объект, который не был создан при помощи оператора **new**, создает непрогнозируемый результат.  Однако можно оператор **delete** может использоваться на указателе со значением 0.  Это означает, что, если оператор **new** возвращает 0 при сбое, то результат такой операции **new** можно удалить без опасных последствий.  Дополнительные сведения см. в разделе [Операторы new и delete](../cpp/new-and-delete-operators.md).  
  
 Операторы **new** и **delete** могут также использоваться для встроенных типов, включая массивы.  Если указатель \(параметр `pointer`\) относится к массиву, то перед эти параметром `pointer` ставятся пустые скобки:  
  
```  
int* set = new int[100];  
//use set[]  
delete [] set;  
```  
  
 При использовании оператора **delete** на объекте отменяется выделение памяти.  Программа, которая разыменовывает указатель после удаления объекта, может создать непрогнозируемый результат или вызвать сбой.  
  
 Если оператор **delete** используется для отмены выделения памяти объекту класса C\+\+, то перед отменой выделения памяти объекта вызывается деструктор этого объекта \(если у объекта имеется деструктор\).  
  
 Если операнд оператора **удалить** представляет собой изменяемое l\-значение, то после удаления объекта его значение будет не определено.  
  
## Использование оператора delete  
 Существует два синтаксический варианта [оператора delete](../cpp/delete-operator-cpp.md): один для отдельных объектов и другой для массивов объектов.  В следующем фрагменте кода показано, чем они отличаются:  
  
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
  
 Следующие два случая дают неопределенный результат: использование формы, предназначенной для массивов \(delete \[ \]\), для удаления одиночного объекта и использовании формы, не предназначенной для массивов, для удаления массива.  
  
## Пример  
 Примеры использования оператора **delete** см. в разделе [оператор new](../cpp/new-operator-cpp.md).  
  
## Принцип работы delete  
 [Оператор delete](../cpp/delete-operator-cpp.md) вызывает функцию [operator delete](../Topic/operator%20delete%20Function.md).  
  
 Для объектов, не имеющих типа класса \([class](../cpp/class-cpp.md), [struct](../cpp/struct-cpp.md) или [union](../cpp/unions.md)\), вызывается глобальный оператор delete.  Для объектов типа класса имя функции освобождения разрешается в глобальной области, если выражение удаления начинается с унарного оператора разрешения области действия \(::\).  В противном случае перед освобождением памяти оператор удаления вызывает деструктор объекта \(если указатель не имеет значения null\).  Оператор удаления можно определять отдельно для каждого класса; если для некоторого класса такое определение отсутствует, вызывается глобальный оператор удаления.  Если выражение удаления используется для освобождения объекта класса, статический тип которого имеет виртуальный деструктор, функция освобождение разрешается через виртуальный деструктор динамического типа объекта.  
  
## См. также  
 [Выражения с унарными операторами](../Topic/Expressions%20with%20Unary%20Operators.md)   
 [Ключевые слова в C\+\+](../cpp/keywords-cpp.md)   
 [Операторы new и delete](../cpp/new-and-delete-operators.md)   
 [Функция operator delete](../Topic/operator%20delete%20Function.md)