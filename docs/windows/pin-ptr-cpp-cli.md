---
title: pin_ptr (C + +/ CLI) | Документация Майкрософт
ms.custom: ''
ms.date: 10/12/2018
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- pin_ptr_cpp
- stdcli::language::pin_ptr
- pin_ptr
dev_langs:
- C++
helpviewer_keywords:
- pinning pointers
- pin_ptr keyword [C++]
ms.assetid: 6c2e6c73-4ec2-4dce-8e1f-ccf3a9f9d0aa
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: d4d8fcc0b1527483e0802eaf88339670abb8ed3c
ms.sourcegitcommit: 3f4e92266737ecb70507871e87dc8e2965ad7e04
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/15/2018
ms.locfileid: "49328471"
---
# <a name="pinptr-ccli"></a>pin_ptr (C++/CLI)

Объявляет *закрепляющий указатель*, который используется только с среда CLR.

## <a name="all-runtimes"></a>Все среды выполнения

(Отсутствуют комментарии для этой возможности языка, которая применяется во всех средах выполнения.)

## <a name="windows-runtime"></a>Среда выполнения Windows

(В среде выполнения Windows эта функция языка не поддерживается.)

## <a name="common-language-runtime"></a>Среда CLR

Объект *закрепляющий указатель* внутренний указатель, запрещающий объекту указывает перемещать в куче сбора мусора. То есть значение закрепляющего указателя не изменяется средой CLR. Это необходимо при передаче адреса управляемого класса в неуправляемую функцию, чтобы исключить неожиданное изменение адреса во время разрешения вызова неуправляемой функции.

### <a name="syntax"></a>Синтаксис

```cpp
[cli::]pin_ptr<cv_qualifiertype>var = &initializer;
```

### <a name="parameters"></a>Параметры

*cv_qualifier*<br/>
**const** или **volatile** квалификаторы. По умолчанию закрепляющий указатель определяется **volatile**. Она является избыточной, но не является ошибкой, чтобы объявить закрепляющий указатель **volatile**.

*type*<br/>
Тип *инициализатор*.

*var*<br/>
Имя **pin_ptr** переменной.

*initializer*<br/>
Член ссылочного типа, элемент управляемого массива или любой другой объект, который можно присвоить собственному указателю.

### <a name="remarks"></a>Примечания

Объект **pin_ptr** представляет надмножество функциональности собственного указателя. Таким образом, все, что могут быть назначены собственного указателя можно также присвоить **pin_ptr**. Внутреннему указателю разрешается выполнять тот же набор операций, что и собственному указателю, включая сравнение и вычисления с указателями.

Объект или часть объекта управляемого класса можно закрепить. В этом случае среда CLR не будет перемещать его во время сборки мусора. Эта возможность в основном используется для передачи указателя на управляемые данные в качестве фактического параметра вызова неуправляемой функции. Во время сборки мусора среда выполнения проверяет метаданные, созданные для закрепляющего указателя, и не перемещает элемент, на который он указывает.

При закреплении объекта также закрепляются его поля значений, то есть поля простых типов или типов значений. Однако поля, объявленные c помощью дескриптора отслеживания (`%`), не закрепляются.

Закрепление части объекта, определенной в управляемом объекте, имеет эффект закрепления всего объекта.

Если закрепляющий указатель переназначается и указывает на новое значение, предыдущий экземпляр, на который он указывал, больше не считается закрепленным.

Объект закреплен только пока **pin_ptr** указывает на нее. Если закрепляющий указатель выходит за пределы области, или задано значение больше не закреплен объект [nullptr](../windows/nullptr-cpp-component-extensions.md). После **pin_ptr** выходит за пределы области, объект, который был закреплен может быть перемещен в кучу сборщиком мусора. Все собственные указатели, по-прежнему указывающие на объект, не обновляются и разыменование одного из них может вызвать неустранимое исключение.

Если нет закрепляющих указателей, указывающих на объект (все закрепляющие указатели из области видимости, были переназначены для указания на другие объекты или были назначены [nullptr](../windows/nullptr-cpp-component-extensions.md)), объект гарантированно не быть закреплен.

Закрепляющий указатель может указывать на дескриптор ссылки, тип значения, дескриптор упакованного типа, член управляемого типа или элемент управляемого массива. Он не может указывать на ссылочный тип.

Получение адреса **pin_ptr** приводит к неопределенному поведению, что указывает на собственный объект.

Закрепляющие указатели можно объявлять только как нестатические локальные переменные в стеке.

Закрепляющие указатели нельзя использовать в качестве:

- параметры функции

- типа возвращаемого значения функции;

- члена класса;

- целевого типа приведения типов.

**pin_ptr** в `cli` пространства имен. Дополнительные сведения см. в разделе [Platform, default и cli пространства имен](../windows/platform-default-and-cli-namespaces-cpp-component-extensions.md).

Дополнительные сведения о внутренних указателях см. в разделе [interior_ptr (C + +/ CLI)](../windows/interior-ptr-cpp-cli.md).

Дополнительные сведения о закрепляющих указателях см. в разделе [как: ПИН-код указателей и массивов](../windows/how-to-pin-pointers-and-arrays.md) и [как: объявить Закрепление указателей и типы значений](../windows/how-to-declare-pinning-pointers-and-value-types.md).

### <a name="requirements"></a>Требования

Параметр компилятора: `/clr`

### <a name="examples"></a>Примеры

В следующем примере используется **pin_ptr** для ограничения позиции первого элемента массива.

```cpp
// pin_ptr_1.cpp
// compile with: /clr
using namespace System;
#define SIZE 10

#pragma unmanaged
// native function that initializes an array
void native_function(int* p) {
   for(int i = 0 ; i < 10 ; i++)  
    p[i] = i;
}
#pragma managed

public ref class A {
private:
   array<int>^ arr;   // CLR integer array

public:
   A() {
      arr = gcnew array<int>(SIZE);
   }

   void load() {
   pin_ptr<int> p = &arr[0];   // pin pointer to first element in arr
   int* np = p;   // pointer to the first element in arr
   native_function(np);   // pass pointer to native function
   }

   int sum() {
      int total = 0;
      for (int i = 0 ; i < SIZE ; i++)  
         total += arr[i];
      return total;
   }
};

int main() {
   A^ a = gcnew A;
   a->load();   // initialize managed array using the native function
   Console::WriteLine(a->sum());
}
```

```Output
45
```

В следующем примере показано, что внутренний указатель можно преобразовать в закрепляющий, и что возвращаемый тип оператора взятия адреса (`&`) является внутренним указателем, если операнд находится в управляемой куче.

```cpp
// pin_ptr_2.cpp
// compile with: /clr
using namespace System;

ref struct G {
   G() : i(1) {}
   int i;
};

ref struct H {
   H() : j(2) {}
   int j;
};

int main() {
   G ^ g = gcnew G;   // g is a whole reference object pointer
   H ^ h = gcnew H;

   interior_ptr<int> l = &(g->i);   // l is interior pointer

   pin_ptr<int> k = &(h->j);   // k is a pinning interior pointer

   k = l;   // ok
   Console::WriteLine(*k);
};
```

```Output
1
```

В следующем примере показано, что закрепляющий указатель может быть приведен к другому типу.

```cpp
// pin_ptr_3.cpp
// compile with: /clr
using namespace System;

ref class ManagedType {
public:
   int i;
};

int main() {
   ManagedType ^mt = gcnew ManagedType;
   pin_ptr<int> pt = &mt->i;
   *pt = 8;
   Console::WriteLine(mt->i);

   char *pc = ( char* ) pt;
   *pc = 255;
   Console::WriteLine(mt->i);
}
```

```Output
8
255
```