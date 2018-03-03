---
title: "Дескриптор отслеживания для упакованных значений | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- boxed value types, tracking handle to
ms.assetid: 16c92048-5b74-47d5-8eca-dfea3d38879a
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: baae8c5317f1e5c9c5acf5bef26a4b79de281a3e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="a-tracking-handle-to-a-boxed-value"></a>Дескриптор отслеживания для упакованных значений
Использование дескриптора отслеживания для ссылки на тип значения отличается от управляемых расширений для C++ к Visual C++.  
  
 Упаковка-преобразование является особенностью CLR единой системы типов. Типы значений непосредственно содержат их состоянии, пока ссылочные типы представляют собой неявные пары: Именованная сущность является дескриптором для неименованного объекта, размещенного в управляемой куче. Инициализации или присвоения значения типа `Object`, например, должны располагаться, тип значения в куче среды CLR — это создала изображение для упаковки-преобразования он - сначала путем выделения памяти связан, а затем путем копирования состояние тип значения и затем возвращает адрес этот анонимный гибридного значение/ссылки. Таким образом, при написании на C#  
  
```  
object o = 1024; // C# implicit boxing  
```  
  
 не существует гораздо больше процессов, чем выполненное очевидной простота кода. Проект C# скрывает сложность не только то, какие операции, происходящих за кулисами, но также абстракции самого процесса упаковки. Управляемые расширения для C++, с другой стороны, важно, это может привести к заблуждение эффективность, помещает его в лицевой стороны для пользователя, поскольку требует явных инструкций:  
  
```  
Object *o = __box( 1024 ); // Managed Extensions explicit boxing  
```  
  
 Упаковка является неявно в Visual C++:  
  
```  
Object ^o = 1024; // new syntax implicit boxing  
```  
  
 `__box` Ключевое слово выполняет очень важную функцию в управляемых расширениях, которая отсутствует в таких языках, как C# и Visual Basic: оно предоставляет словарь и отслеживания дескриптор для непосредственного управления упакованного экземпляра в управляемой куче. Например рассмотрим следующую небольшую программу:  
  
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
  
 Базовый код, созданный для трех вызовов функции `WriteLine` Показать введите различные уровни затрат на обращение к значению упакованных значений (спасибо Иву Дольче за указание на эти различия), где указанными строками Показать дополнительные издержки, связанные с каждым вызов.  
  
```  
// Console::WriteLine( S"result :: {0}", result.ToString() ) ;  
ldstr      "result :: {0}"  
ldloca.s   result  // ToString overhead  
call       instance string  [mscorlib]System.Double::ToString()  // ToString overhead  
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
  
 Передаче упакованный тип значения непосредственно `Console::WriteLine` исключает упаковка-преобразование и необходимость вызова `ToString()`. (Конечно, существует более ранняя упаковка-преобразование для инициализации `br`, чтобы извлечь выгоду, необходимо использовать `br` для работы.  
  
 В новом синтаксисе поддержка типов упакованных значений значительно более элегантный, встроенная в систему типов, сохраняя ее эффективности. Например вот перевод ранее небольшой программы:  
  
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
  
## <a name="see-also"></a>См. также  
 [Типы значений и их поведение (C + +/ CLI)](../dotnet/value-types-and-their-behaviors-cpp-cli.md)   
 [Практическое руководство. Явный запрос упаковки-преобразования](../dotnet/how-to-explicitly-request-boxing.md)