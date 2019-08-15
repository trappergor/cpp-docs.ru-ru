---
title: Оператор delete (C++)
ms.date: 08/12/2019
f1_keywords:
- delete_cpp
helpviewer_keywords:
- delete keyword [C++], syntax
- delete keyword [C++], deallocating objects
- delete keyword [C++]
ms.assetid: de39c900-3f57-489c-9598-dcb73c4b3930
ms.openlocfilehash: 3b00bf78d286ba530dee85240236a2a9ea171113
ms.sourcegitcommit: a146b169664c001406a0cccc7fbda1b8d7be5078
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/14/2019
ms.locfileid: "69024646"
---
# <a name="delete-operator-c"></a>Оператор delete (C++)

Отменяет выделение блока памяти.

## <a name="syntax"></a>Синтаксис

> [`::` ]`delete` *приведение выражения*\
> [`::` ]`delete []` *приведение выражения*

## <a name="remarks"></a>Примечания

Аргумент *Cast-Expression* должен быть указателем на блок памяти, выделенный ранее для объекта, созданного с помощью [оператора New](../cpp/new-operator-cpp.md). Оператор **Delete** имеет результат типа **void** и поэтому не возвращает значение. Например:

```cpp
CDialog* MyDialog = new CDialog;
// use MyDialog
delete MyDialog;
```

Использование инструкции **Delete** для указателя на объект, не выделенный с помощью **New** , дает непредсказуемые результаты. Однако можно использовать **Delete** для указателя со значением 0. Это означает, что когда **New** возвращает 0 в случае сбоя, удаление невыполненной **новой** операции является безвредным. Дополнительные сведения см. [в разделе операторы new и DELETE](../cpp/new-and-delete-operators.md).

Операторы **New** и **Delete** также можно использовать для встроенных типов, включая массивы. Если `pointer` ссылается на массив, поместите пустые скобки (`[]`) перед `pointer`:

```cpp
int* set = new int[100];
//use set[]
delete [] set;
```

Использование оператора **Delete** для объекта освобождает его память. Программа, которая разыменовывает указатель после удаления объекта, может создать непрогнозируемый результат или вызвать сбой.

Если для освобождения памяти для объекта C++ класса используется метод Delete, деструктор объекта вызывается до освобождения памяти объекта (если у объекта есть деструктор).

Если операнд оператора **Delete** является изменяемым l-значением, его значение не определено после удаления объекта.

Если указан параметр компилятора [/SDL (включить дополнительные проверки безопасности)](/cpp/build/reference/sdl-enable-additional-security-checks) , то после удаления объекта операнду оператора **Delete** присваивается недопустимое значение.

## <a name="using-delete"></a>Использование оператора delete

Существует два синтаксических варианта для [оператора delete](../cpp/delete-operator-cpp.md): один для единичных объектов, а другой для массивов объектов. В следующем фрагменте кода показано, как они отличаются:

```cpp
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

Следующие два варианта приводят к неопределенным результатам: использование формы массива delete (`delete []`) для объекта и использование немассивного класса DELETE в массиве.

## <a name="example"></a>Пример

Примеры использования инструкции **Delete**см. в разделе [оператор New](../cpp/new-operator-cpp.md).

## <a name="how-delete-works"></a>Принцип работы delete

Оператор delete вызывает **оператор функции Delete**.

Для объектов, не имеющих тип класса ([класс](../cpp/class-cpp.md), [Структура](../cpp/struct-cpp.md)или [объединение](../cpp/unions.md)), вызывается оператор глобального удаления. Для объектов типа класса имя функции освобождения разрешается в глобальной области, если выражение delete начинается с оператора унарного разрешения области (`::`). В противном случае перед освобождением памяти оператор удаления вызывает деструктор объекта (если указатель не имеет значения null). Оператор удаления можно определять отдельно для каждого класса; если для некоторого класса такое определение отсутствует, вызывается глобальный оператор удаления. Если выражение удаления используется для освобождения объекта класса, статический тип которого имеет виртуальный деструктор, функция освобождение разрешается через виртуальный деструктор динамического типа объекта.

## <a name="see-also"></a>См. также

[Выражения с унарными операторами](../cpp/expressions-with-unary-operators.md)\
[Ключевые слова](../cpp/keywords-cpp.md)\
[Операторы new и delete](../cpp/new-and-delete-operators.md)