---
title: "pin_ptr (C + +/ CLI) | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- pin_ptr_cpp
- stdcli::language::pin_ptr
- pin_ptr
dev_langs: C++
helpviewer_keywords:
- pinning pointers
- pin_ptr keyword [C++]
ms.assetid: 6c2e6c73-4ec2-4dce-8e1f-ccf3a9f9d0aa
caps.latest.revision: "28"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: c72149aa023723f4524ac22252f6778494341f44
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="pinptr-ccli"></a>pin_ptr (C++/CLI)
Объявляет *закрепляющий указатель*, который используется только с общеязыковая среда выполнения.  
  
## <a name="all-runtimes"></a>Все среды выполнения  
 (Отсутствуют комментарии для этой функции языка, которая применяется во всех средах выполнения.)  
  
## <a name="windows-runtime"></a>Среда выполнения Windows  
 (В среде выполнения Windows эта функция языка не поддерживается.)  
  
## <a name="common-language-runtime"></a>Среда CLR  
 Объект *закрепляющий указатель* внутренний указатель, не позволяющая объекта указывает перемещать в куче сбора мусора. То есть значение закрепляющего указателя не изменяется средой CLR. Это необходимо при передаче адреса управляемого класса в неуправляемую функцию, чтобы исключить неожиданное изменение адреса во время разрешения вызова неуправляемой функции.  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp  
[cli::]pin_ptr<cv_qualifiertype>var = &initializer;  
```  
  
### <a name="parameters"></a>Параметры  
 *cv_qualifier*  
 Квалификатор `const` или `volatile`. По умолчанию закрепляющий указатель определяется как `volatile`. Объявление закрепляющего указателя как `volatile` избыточно, но не является ошибкой.  
  
 *type*  
 Тип параметра `initializer`.  
  
 *var*  
 Имя переменной `pin_ptr`.  
  
 *initializer*  
 Член ссылочного типа, элемент управляемого массива или любой другой объект, который можно присвоить собственному указателю.  
  
### <a name="remarks"></a>Примечания  
 `pin_ptr` представляет надмножество функциональности собственного указателя. Таким образом, все, что можно присвоить собственному указателю, можно также присвоить указателю `pin_ptr`. Внутреннему указателю разрешается выполнять тот же набор операций, что и собственному указателю, включая сравнение и вычисления с указателями.  
  
 Объект или часть объекта управляемого класса можно закрепить. В этом случае среда CLR не будет перемещать его во время сборки мусора. Эта возможность в основном используется для передачи указателя на управляемые данные в качестве фактического параметра вызова неуправляемой функции. Во время сборки мусора среда выполнения проверяет метаданные, созданные для закрепляющего указателя, и не перемещает элемент, на который он указывает.  
  
 При закреплении объекта также закрепляются его поля значений, то есть поля простых типов или типов значений. Однако поля, объявленные c помощью дескриптора отслеживания (`%`), не закрепляются.  
  
 Закрепление части объекта, определенной в управляемом объекте, имеет эффект закрепления всего объекта.  
  
 Если закрепляющий указатель переназначается и указывает на новое значение, предыдущий экземпляр, на который он указывал, больше не считается закрепленным.  
  
 Объект закреплен только пока `pin_ptr` указывает на него. Если закрепляющий указатель выходит за пределы области, или имеет значение больше не закреплен объект [nullptr](../windows/nullptr-cpp-component-extensions.md). После выхода `pin_ptr` за пределы области видимости объект, который был закреплен, может быть перемещен в кучу сборщиком мусора. Все собственные указатели, по-прежнему указывающие на объект, не обновляются и разыменование одного из них может вызвать неустранимое исключение.  
  
 При отсутствии закрепляющих указателей, указывающих на объект (все закрепляющие указатели вышли за пределы области видимости, были переназначены для указания на другие объекты или были назначены [nullptr](../windows/nullptr-cpp-component-extensions.md)), объект гарантированно не будет закреплен.  
  
 Закрепляющий указатель может указывать на дескриптор ссылки, тип значения, дескриптор упакованного типа, член управляемого типа или элемент управляемого массива. Он не может указывать на ссылочный тип.  
  
 Получение адреса `pin_ptr`, указывающего на собственный объект, приводит к неопределенному поведению.  
  
 Закрепляющие указатели можно объявлять только как нестатические локальные переменные в стеке.  
  
 Закрепляющие указатели нельзя использовать в качестве:  
  
-   параметры функции  
  
-   возвращаемого типа функции;  
  
-   члена класса;  
  
-   целевого типа приведения типов.  
  
 `pin_ptr` находится в пространстве имен `cli`. Дополнительные сведения см. в разделе [платформы, по умолчанию и пространства имен cli](../windows/platform-default-and-cli-namespaces-cpp-component-extensions.md).  
  
 Дополнительные сведения о внутренних указателей см. в разделе [interior_ptr (C + +/ CLI)](../windows/interior-ptr-cpp-cli.md).  
  
 Дополнительные сведения о Закрепление указателей см. в разделе [как: ПИН-код указателей и массивов](../windows/how-to-pin-pointers-and-arrays.md) и [как: объявить Закрепление указателей и типы значений](../windows/how-to-declare-pinning-pointers-and-value-types.md).  
  
### <a name="requirements"></a>Требования  
 Параметр компилятора: **/clr**  
  
### <a name="examples"></a>Примеры  
 **Пример**  
  
 В следующем примере используется `pin_ptr` для ограничения позиции первого элемента массива.  
  
```  
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
  
 **Вывод**  
  
```Output  
45  
```  
  
 **Пример**  
  
 В следующем примере показано, что внутренний указатель можно преобразовать в закрепляющий, и что возвращаемый тип оператора взятия адреса (`&`) является внутренним указателем, если операнд находится в управляемой куче.  
  
```  
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
  
 **Вывод**  
  
```Output  
1  
```  
  
 **Пример**  
  
 В следующем примере показано, что закрепляющий указатель может быть приведен к другому типу.  
  
```  
// pin_ptr_3.cpp  
// compile with: /clr  
using namespace System;  
  
ref class ManagedType {  
public:  
   int i;  
};  
  
int main() {  
   ManagedType ^mt = gcnew ManagedType;  
   pin_ptr< int > pt = &mt->i;  
   *pt = 8;  
   Console::WriteLine(mt->i);  
  
   char *pc = ( char* ) pt;  
   *pc = 255;  
   Console::WriteLine(mt->i);  
}  
```  
  
 **Вывод**  
  
```Output  
8  
255  
```