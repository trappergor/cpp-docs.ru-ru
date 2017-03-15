---
title: "delegate (расширения компонентов C++) | Microsoft Docs"
ms.custom: ""
ms.date: "12/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "delegate_cpp"
  - "delegate"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Ключевое слово delegate [C++]"
ms.assetid: 03caf23d-7873-4a23-9b34-becf42aaf429
caps.latest.revision: 26
caps.handback.revision: 24
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# delegate (расширения компонентов C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Объявляет тип, представляющий указатель функции.  
  
## Все среды выполнения  
 И [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)], и среда CLR поддерживают делегаты.  
  
### Примечания  
 `delegate` — это контекстно\-зависимое ключевое слово.  Для получения дополнительной информации см. [Контекстные ключевые слова](../windows/context-sensitive-keywords-cpp-component-extensions.md).  
  
 Для обнаружения во время компиляции, является ли тип делегатом, используйте характеристики типа `__is_delegate()`.  Для получения дополнительной информации см. [Поддержка характеристик типов компилятором](../windows/compiler-support-for-type-traits-cpp-component-extensions.md).  
  
## среда выполнения Windows  
 C\+\+\/CX поддерживает делегаты следующим синтаксисом.  
  
### Синтаксис  
  
```cpp  
  
access delegate return-type delegate-type-identifier ([ parameters ])  
```  
  
### Параметры  
 *access*  
 \(необязательно\) Доступность делегата, который может быть `public` \(по умолчанию\) или `private`.  Прототип функции может также содержать ключевое слово `const` или `volatile`.  
  
 *return\-type*  
 Тип возвращаемого значения прототипа функции.  
  
 *delegate\-type\-identifier*  
 Имя объявленного типа делегата.  
  
 *parameters*  
 \(Необязательно\) Типы и идентификаторы прототипа функции.  
  
### Примечания  
 Используйте *delegate\-type\-identifier* для объявления события с таким же прототипом, что и у делегата.  Дополнительные сведения см. в разделе [Делегаты \(C\+\+\/CX\)](../Topic/Delegates%20\(C++-CX\).md).  
  
### Требования  
 Параметр компилятора: **\/ZW**  
  
## Среда CLR  
 Среда CLR поддерживает делегаты со следующим синтаксисом.  
  
### Синтаксис  
  
```cpp  
  
access delegate function_declaration  
```  
  
### Параметры  
 *access*  
 \(необязательно\) Доступность делегата вне сборки может быть в открытом и закрытом доступе.  По умолчанию используется закрытый тип доступа.  Внутри класса делегат может обладать любым типом доступа.  
  
 *function\_declaration*  
 Сигнатура функции, которая может быть привязана к делегату.  Тип возвращаемого значения делегата может быть любым управляемым типом.  Во избежание проблем взаимодействия, в качестве типа возвращаемого значения делегата рекомендуется тип CLS.  
  
 Для определения непривязанного делегата первый параметр в *function\_declaration* должен быть типом указателя `this` для объекта.  Для получения дополнительной информации см. [Несвязанные делегаты](../Topic/Unbound%20Delegates.md).  
  
### Примечания  
 Делегаты являются многоадресным: "указатель на функцию" можно привязать к одному или нескольким методам в управляемый класс.  Ключевое слово **delegate** определяет тип множественного делегата с определенной сигнатурой метода.  
  
 Делегат может также привязать к методу класса значений, такому как статический метод.  
  
 Делегат обладает следующими характеристиками:  
  
-   Он наследуется от **System::MulticastDelegate**.  
  
-   Он имеет конструктор, который принимает два аргумента: указатель на управляемый класс или **NULL** \(в случае привязки к статическому методу\) и полный метод указанного типа.  
  
-   Он содержит метод `Invoke`, сигнатура которого соответствует объявленной сигнатуре делегата.  
  
 При вызове делегата его функция\(и\) вызываются в том порядке, в котором они были присоединены.  
  
 Возвращаемое значение делегата — это возвращаемое значение из последнего подключенного функции\-члена.  
  
 Делегаты не могут быть перегружены.  
  
 Делегаты могут быть привязанными или несвязанными.  
  
 После создания привязанного делегата, первым аргументом будет ссылка на объект.  Второй аргумент создания делегата будет или адрес метода объекта управляемого класса, или указатель на метод типа значения.   Второй аргумент создания делегата должен иметь имя метода с полным синтаксисом области класса и применять оператор address\-of.  
  
 При создании экземпляра несвязанного делегата первым аргументом будет или адрес метода объекта управляемого класса, или указатель на метод типа значения.   Аргумент должен быть именем метода с полным синтаксисом области класса и применять оператор address\-of.  
  
 При создании делегата статической или глобальной функции нужен только один параметр: функция \(при необходимости адрес функции\).  
  
 Дополнительные сведения о делегатах см. в разделах  
  
-   [Несвязанные делегаты](../Topic/Unbound%20Delegates.md)  
  
-   [Практическое руководство. Определение и использование делегатов](../Topic/How%20to:%20Define%20and%20Use%20Delegates%20\(C++-CLI\).md)  
  
-   [Делегат члена класса значений](../misc/how-to-associate-delegates-to-members-of-a-value-class.md)  
  
-   [Делегат неуправляемой функции](../misc/how-to-associate-delegates-to-unmanaged-functions.md)  
  
-   [Составные делегаты](../misc/how-to-compose-delegates.md)  
  
-   [Практическое руководство. Передача Delegate^ в неуправляемую функцию, ожидающую указатель на функцию](../misc/how-to-pass-a-delegate-hat-to-a-native-function-expecting-a-function-pointer.md)  
  
-   [Универсальные делегаты \(Visual C\+\+\)](../Topic/Generic%20Delegates%20\(Visual%20C++\).md)  
  
### Требования  
 Параметр компилятора: **\/clr**  
  
### Примеры  
 **Пример**  
  
 В следующем примере показано объявление, инициализация и вызов делегата.  
  
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
  
 **Output**  
  
  **in func1 8**  
 **in func1 9**  
 **in func2 9**  
 **in func2 10**  
 **in static func3 11**   
## См. также  
 [Расширения компонентов для платформ среды выполнения](../windows/component-extensions-for-runtime-platforms.md)