---
title: "Класс function | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "functional/std::tr1::function"
  - "std.tr1.function"
  - "std::tr1::function"
  - "function"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "function - класс [TR1]"
ms.assetid: 7b5ca76b-9ca3-4d89-8fcf-cad70a4aeae6
caps.latest.revision: 26
caps.handback.revision: 14
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Класс function
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Программа\-оболочка можно вызвать для объекта.  
  
## Синтаксис  
  
```cpp  
template<class Fty>  
   class function  // Fty of type Ret(T1, T2, ..., TN)  
   : public unary_function<T1, Ret>       // when Fty is Ret(T1)  
   : public binary_function<T1, T2, Ret>  // when Fty is Ret(T1, T2)  
   {  
public:  
   typedef Ret result_type;  
  
   function();  
   function(nullptr_t);  
   function(const function& _Right);  
   template<class Fty2>  
      function(Fty2 fn);  
   template<class Fty2, class Alloc>  
       function (reference_wrapper<Fty2>, const Alloc& _Ax);  
   template<class Fty2, class Alloc>  
       void assign (Fty2, const Alloc& _Ax);  
   template<class Fty2, class Alloc>  
       assign (reference_wrapper<Fty2>, const Alloc& _Ax);  
```  
  
```cpp  
function& operator=(nullptr_t);  
function& operator=(const function&);  
template<class Fty2>  
   function& operator=(Fty2);  
template<class Fty2>  
   function& operator=(reference_wrapper<Fty2>);  
void swap(function&);  
  
explicit operator bool() const;  
result_type operator()(T1, T2, ....., TN) const;  
  
const std::type_info& target_type() const;  
template<class Fty2>  
   Fty2 *target();  
template<class Fty2>  
   const Fty2 *target() const;  
```  
  
```cpp  
   template<class Fty2>  
      void operator==(const Fty2&) const = delete;  
   template<class Fty2>  
      void operator!=(const Fty2&) const = delete;  
};  
```  
  
#### Параметры  
 `Fty`  
 Тип функции, который необходимо создать.  
  
 `_Ax`  
 Функция распределителя.  
  
## Заметки  
 Класс шаблона программа\-оболочка вызова, сигнатура вызова `Ret(T1, T2, ..., TN)`.  Он используется для преобразования различных объектов можно вызвать в равномерную программу\-оболочку.  
  
 Некоторые функции\-члены принимают операнду этому имена нужный целевой объект.  Можно указать один операнд несколькими способами:  
  
 `fn` \-\- можно вызвать объект `fn`; после вызова объект `function` содержит копию `fn`  
  
 `fnref` \-\- можно вызвать объект с именем `fnref.get()`; после вызова объект `function` хранит ссылку на `fnref.get()`  
  
 `right` \-\- можно вызвать объект, если имеется удержатьый объектом `right``function`  
  
 `npc` \-\- указатель; после вызова объект `function` пуст  
  
 Во всех случаях `INVOKE(f, t1, t2, ..., tN)`, где `f` можно вызвать объект и `t1, t2, ..., tN` значения типов `T1, T2, ..., TN` соответственно, должно быть с правильным форматом и, если `Ret` не пусто, преобразовать в значение `Ret`.  
  
 Пустой объект `function` не содержит можно вызвать объект или ссылку на вызываемую объектом.  
  
### конструкторов;  
  
|||  
|-|-|  
|[function::function](../Topic/function::function.md)|Построение программу\-оболочку, или пустой или хранит можно вызвать объект произвольного типа с фиксированной сигнатурой.|  
  
### Определения типов  
  
|||  
|-|-|  
|[function::result\_type](../Topic/function::result_type.md)|Тип возвращаемого значения, хранящиеся вызываемую объекта.|  
  
### Функции\-члены  
  
|||  
|-|-|  
|[function::assign](../Topic/function::assign.md)|Присвоить можно вызвать объект на этот объект функции.|  
|[function::swap](../Topic/function::swap.md)|Обмен 2 можно вызвать объекта.|  
|[function::target](../Topic/function::target.md)|Если тесты, сохраненные можно вызвать объект можно вызвать в указанном порядке.|  
|[function::target\_type](../Topic/function::target_type.md)|Получает сведения о типе можно вызвать в объекте.|  
  
### Операторы  
  
|||  
|-|-|  
|[function::operator unspecified](../Topic/function::operator%20unspecified.md)|Если тесты, сохраненные можно вызвать объект существует.|  
|[function::operator\(\)](../Topic/function::operator\(\).md)|Вызывает можно вызвать объект.|  
|[function::operator\=](../Topic/function::operator=.md)|Заменяет сохраненного можно вызвать объект.|  
  
## Требования  
 **Заголовок:** \<functional\>  
  
 **Пространство имен:** std  
  
## См. также  
 [Функция mem\_fn](../Topic/mem_fn%20Function.md)   
 [Класс reference\_wrapper](../Topic/reference_wrapper%20Class.md)