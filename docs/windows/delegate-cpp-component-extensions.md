---
title: Delegate (расширения компонентов C++) | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- delegate_cpp
- delegate
dev_langs:
- C++
helpviewer_keywords:
- delegate keyword [C++]
ms.assetid: 03caf23d-7873-4a23-9b34-becf42aaf429
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 73d40bb33509f89273b37f7704cd1922a8d5adc2
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2018
ms.locfileid: "33879663"
---
# <a name="delegate--c-component-extensions"></a>delegate (расширения компонентов C++)
Объявляет тип, который представляет указатель на функцию.  
  
## <a name="all-runtimes"></a>Все среды выполнения  
 Общеязыковая среда выполнения и среды выполнения Windows поддерживает делегаты.  
  
### <a name="remarks"></a>Примечания  
 `delegate` — контекстно-зависимое ключевое слово. Дополнительные сведения см. в разделе [контекстно-зависимые ключевые слова](../windows/context-sensitive-keywords-cpp-component-extensions.md).  
  
 Чтобы обнаружить во время компиляции, если тип является делегатом, используйте `__is_delegate()` Признак типа. Дополнительные сведения см. в разделе [поддержка характеристик типов компилятором](../windows/compiler-support-for-type-traits-cpp-component-extensions.md).  
  
## <a name="windows-runtime"></a>Среда выполнения Windows  
 C + +/ CX поддерживает делегаты со следующим синтаксисом.  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp  
access  
delegate  
return-type  
delegate-type-identifier  
(  
[ parameters ]  
)  
  
```  
  
### <a name="parameters"></a>Параметры  
 *access*  
 (необязательно) Специальные возможности делегата, который может быть `public` (по умолчанию) или `private`. Прототип функции также могут быть дополнены `const` или `volatile` ключевые слова.  
  
 *Тип возвращаемого значения*  
 Тип возвращаемого значения прототип функции.  
  
 *идентификатор для типа делегата*  
 Имя типа объявленный делегат.  
  
 *Параметры*  
 (Необязательно) Типы и идентификаторы прототип функции.  
  
### <a name="remarks"></a>Примечания  
 Используйте *идентификатора для типа делегата* для объявления события с прототипом же, что и делегат. Дополнительные сведения см. в разделе [делегаты (C + +/ CX)](../cppcx/delegates-c-cx.md).  
  
### <a name="requirements"></a>Требования  
 Параметр компилятора: **/ZW**  
  
## <a name="common-language-runtime"></a>Среда CLR  
 Общеязыковая среда выполнения поддерживает делегаты со следующим синтаксисом.  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp  
access  
delegate  
function_declaration  
  
```  
  
### <a name="parameters"></a>Параметры  
 *access*  
 (необязательно) Специальные возможности делегата за пределами сборки может быть открытыми или закрытыми.  Значение по умолчанию является закрытым.  Внутри класса делегат может иметь любой уровень доступа.  
  
 *function_declaration*  
 Подпись функции, который может быть привязан к делегату. Тип возвращаемого значения делегата может быть любой управляемый тип. В целях взаимодействия рекомендуется, тип возвращаемого значения делегата был типом CLS.  
  
 Для определения непривязанного делегата, первый параметр в *function_declaration* должен быть типом значения `this` указатель для объекта. 
  
### <a name="remarks"></a>Примечания  
 Делегаты являются многоадресными: «указатель на функцию» могут быть привязаны к один или несколько методов управляемого класса. **Делегировать** ключевое слово определяет тип делегата многоадресной рассылки с помощью определенного метода подписи.  
  
 Делегат можно также привязать метод класса значений, таких как статический метод.  
  
 Делегат имеет следующие характеристики:  
  
-   Он наследуется от **System::MulticastDelegate**.  
  
-   Он имеет конструктор, который принимает два аргумента: указатель на управляемый класс или **NULL** (в случае привязки к статическому методу) и полный метод указанного типа.  
  
-   Он содержит метод `Invoke`, сигнатура которого соответствует объявленной сигнатуре делегата.  
  
 При вызове делегата его функции вызываются в порядке, в котором они были присоединены.  
  
 Возвращает значение в делегат, содержащий возвращаемое значение его последнего функции присоединенного члена.  
  
 Делегаты не могут быть перегружены.  
  
 Делегаты можно привязать или отсутствует привязка.  
  
 При создании экземпляра делегата привязанного, первый аргумент должен быть ссылка на объект.  Второй аргумент функции создания экземпляра делегата должны либо быть адрес метода объекта управляемого класса или ссылки в метод типа значения.   Второй аргумент функции создания экземпляра делегата необходимо имя метода с помощью синтаксиса области полный класс и применить оператор address-of.  
  
 При создании экземпляра непривязанного делегата, первый аргумент должен быть адресом метода объекта управляемого класса, или указатель на метод типа значения.   Аргумент должен назовите метод с помощью синтаксиса области полный класс и применить оператор address-of.  
  
 При создании делегата статической или глобальной функции, требуется только один параметр: функция (при необходимости адрес функции).  
  
 Дополнительные сведения о делегатах см. в разделе  
  
-   [Практическое руководство. Определение и использование делегатов (C++/CLI)](../dotnet/how-to-define-and-use-delegates-cpp-cli.md)  
  
-   [Универсальные делегаты (Visual C++)](../windows/generic-delegates-visual-cpp.md)  
  
### <a name="requirements"></a>Требования  
 Параметр компилятора: **/clr**  
  
### <a name="examples"></a>Примеры  
 **Пример**  
  
 В следующем примере показано, как объявить, инициализации и вызова делегатов.  
  
```cpp  
// mcppv2_delegate.cpp  
// compile with: /clr  
using namespace System;  
  
// declare a delegate  
public delegate void MyDel(int i);  
  
ref class A {  
public:  
   void func1(int i) {  
      Console::WriteLine("in func1 {0}", i);  
   }  
  
   void func2(int i) {  
      Console::WriteLine("in func2 {0}", i);  
   }  
  
   static void func3(int i) {  
      Console::WriteLine("in static func3 {0}", i);  
   }  
};  
  
int main () {  
   A ^ a = gcnew A;  
  
   // declare a delegate instance  
   MyDel^ DelInst;  
  
   // test if delegate is initialized  
   if (DelInst)  
      DelInst(7);  
  
   // assigning to delegate  
   DelInst = gcnew MyDel(a, &A::func1);  
  
   // invoke delegate  
   if (DelInst)  
      DelInst(8);  
  
   // add a function  
   DelInst += gcnew MyDel(a, &A::func2);  
  
   DelInst(9);  
  
   // remove a function  
   DelInst -= gcnew MyDel(a, &A::func1);  
  
   // invoke delegate with Invoke  
   DelInst->Invoke(10);  
  
   // make delegate to static function  
   MyDel ^ StaticDelInst = gcnew MyDel(&A::func3);  
   StaticDelInst(11);  
}  
```  
  
 **Вывод**  
  
```Output  
in func1 8  
  
in func1 9  
  
in func2 9  
  
in func2 10  
  
in static func3 11  
```  
  
## <a name="see-also"></a>См. также  
 [Расширения компонентов для платформ среды выполнения](../windows/component-extensions-for-runtime-platforms.md)