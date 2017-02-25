---
title: "Дескриптор отслеживания для упакованных значений | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "типы упакованных значений, дескриптор отслеживания для"
ms.assetid: 16c92048-5b74-47d5-8eca-dfea3d38879a
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 11
---
# Дескриптор отслеживания для упакованных значений
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Использование дескриптора отслеживания для ссылки на тип значения в [!INCLUDE[cpp_current_long](../dotnet/includes/cpp_current_long_md.md)] отличается от управляемых расширений для C\+\+.  
  
 Упаковка\-преобразование является особенностью унифицированной системы типов среды CLR.  Типы значений непосредственно содержат данные об их состоянии, в то время как ссылочные типы представляют собой неявные пары: именованная сущность является дескриптором для неименованного объекта, размещенного в управляемой куче.  Для инициализации или присвоения значения типа объекту `Object` требуется, чтобы тип значения размещался внутри кучи CLR \(той же, которая создала изображение для упаковки\-преобразования\). Для этого необходимо сначала выделить связанную память, скопировать состояние типа значения, а затем возвратить адрес гибрида "значение\/ссылка" анонимного типа.  Таким образом, при написании на C\#  
  
```  
object o = 1024; // C# implicit boxing  
```  
  
 происходит гораздо больше различных процессов, чем может показаться из\-за внешней простоты кода.  Язык C\# скрывает не только сложность выполняемых операций, но и абстрактность самого процесса упаковки.  Из\-за угрозы введения пользователя в заблуждение относительно эффективности, управляемые расширения для C\+\+, в свою очередь, открыто демонстрировали эту сложность, постоянно запрашивая явные инструкции.  
  
```  
Object *o = __box( 1024 ); // Managed Extensions explicit boxing  
```  
  
 Упаковка\-преобразование в [!INCLUDE[cpp_current_long](../dotnet/includes/cpp_current_long_md.md)] является неявной:  
  
```  
Object ^o = 1024; // new syntax implicit boxing  
```  
  
 Ключевое слово `__box` выполняет очень важную функцию в управляемых расширениях, которая отсутствует в таких языках, как C\# и [!INCLUDE[vbprvb](../dotnet/includes/vbprvb_md.md)]: оно предоставляет словарь и дескриптор отслеживания для непосредственного управления упакованного экземпляра в управляемой куче.  Например, рассмотрим следующую небольшую программу:  
  
```  
int main() {  
   double result = 3.14159;  
   __box double * br = __box( result );  
  
   result = 2.7;   
   *br = 2.17;     
   Object * o = br;  
  
   Console::WriteLine( S"result :: {0}", result.ToString() ) ;  
   Console::WriteLine( S"result :: {0}", __box(result) ) ;  
   Console::WriteLine( S"result :: {0}", br );  
}  
```  
  
 В основном коде, созданном для трех вызовов функции `WriteLine`, показаны различные уровни затрат на доступ к значению типа упакованных значений \(спасибо Иву Дольче за указание на эти различия\). Обозначенные строки показывают издержки, связанные с каждым вызовом функции.  
  
```  
// Console::WriteLine( S"result :: {0}", result.ToString() ) ;  
ldstr      "result :: {0}"  
ldloca.s   result  // ToString overhead  
call       instance string  [mscorlib]System.Double::ToString()  // ToString overhead  
call       void [mscorlib]System.Console::WriteLine(string, object)  
  
// Console::WriteLine( S"result :: {0}", __box(result) ) ;  
Ldstr    " result :: {0}"  
ldloc.0  
box    [mscorlib]System.Double // box overhead  
call    void [mscorlib]System.Console::WriteLine(string, object)  
  
// Console::WriteLine( S"result :: {0}", br );  
ldstr    "result :: {0}"  
ldloc.0  
call     void [mscorlib]System.Console::WriteLine(string, object)  
```  
  
 Передача типа упакованных значений непосредственно в `Console::WriteLine` сводит к минимуму необходимость упаковки и вызова метода `ToString()`. \(Конечно, существует более ранняя упаковка\-преобразование для инициализации `br`, поэтому, чтобы извлечь выгоду, необходимо использовать `br`.\)  
  
 В новом синтаксисе поддержка типов упакованных значений стала гораздо более элегантной и лучше интегрируется в систему типов, сохраняя при этом широкие возможности.  Например, ниже приводится перевод указанной ранее небольшой программы:  
  
```  
int main()  
{  
   double result = 3.14159;  
   double^ br = result;  
   result = 2.7;  
   *br = 2.17;  
   Object^ o = br;  
   Console::WriteLine( "result :: {0}", result.ToString() );  
   Console::WriteLine( "result :: {0}", result );  
   Console::WriteLine( "result :: {0}", br );  
}  
```  
  
## См. также  
 [Типы значений и их режимы работы \(C\+\+\/CLI\)](../dotnet/value-types-and-their-behaviors-cpp-cli.md)   
 [Практическое руководство. Явный запрос упаковки\-преобразования](../Topic/How%20to:%20Explicitly%20Request%20Boxing.md)