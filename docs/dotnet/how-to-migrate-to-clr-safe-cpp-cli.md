---
title: "Практическое руководство. Миграция в /clr:safe (C++/CLI) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/clr - параметр компилятора [C++], перенос в /clr:safe"
  - "перенос [C++], проверяемые сборки"
  - "обновление приложений Visual C++, проверяемые сборки"
  - "проверяемые сборки [C++], переход на"
ms.assetid: 75f9aae9-1dcc-448a-aa11-2d96f972f9d2
caps.latest.revision: 15
caps.handback.revision: 15
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Практическое руководство. Миграция в /clr:safe (C++/CLI)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Visual C\+\+ может создавать компоненты с помощью команды **\/clr:safe**, что приводит к возникновению ошибок в компиляторе для каждой не поддающейся проверке конструкции кода.  
  
## Заметки  
 Такие ошибки могут возникать в следующих случаях.  
  
-   Собственные типы.  Даже если эти типы не используются, объявление собственных классов, структур, указателей или массивов может помешать компиляции.  
  
-   Глобальные переменные  
  
-   Вызовы функции в неуправляемой библиотеке, включая вызовы функции в среде CLR.  
  
-   Проверяемая функция не может содержать [Оператор static\_cast](../cpp/static-cast-operator.md) для понижающего преобразования.  [Оператор static\_cast](../cpp/static-cast-operator.md) может использоваться для преобразования среди простых типов, однако, для понижающего преобразования должны использоваться [safe\_cast](../windows/safe-cast-cpp-component-extensions.md) и преобразование стиля C \(реализованного как [safe\_cast](../windows/safe-cast-cpp-component-extensions.md)\).  
  
-   Проверяемая функция не может содержать [Оператор reinterpret\_cast](../cpp/reinterpret-cast-operator.md) \(или любой другой эквивалент преобразования стиля C\).  
  
-   Проверяемая функция не может выполнять арифметические действия [interior\_ptr \(C\+\+\/CLI\)](../windows/interior-ptr-cpp-cli.md).  Действия могут присваиваться ей и использоваться для разыменования.  
  
-   Проверяемая функция может только вызывать и принимать указатели для ссылочных типов, поэтому типы значений должны упаковываться перед вызовом.  
  
-   Проверяемая функция может вызывать только проверяемые функции \(вызовы среды CLR не допускаются, включая `AtEntry`\/`AtExit`, поэтому также не разрешены глобальные конструкторы\).  
  
-   Класс переменной не может использовать <xref:System.Runtime.InteropServices.LayoutKind>.  
  
-   При сборке EXE главная функция не может объявлять параметры, поэтому для извлечения аргументов командной строки необходимо использовать <xref:System.Environment.GetCommandLineArgs%2A>.  
  
-   Невиртуальный вызов к виртуальной функции.  Примеры.  
  
    ```  
    // not_verifiable.cpp  
    // compile with: /clr  
    ref struct A {  
       virtual void Test() {}  
    };  
  
    ref struct B : A {};  
  
    int main() {  
       B^ b1 = gcnew B;  
       b1->A::Test();   // Non-virtual call to virtual function  
    }  
    ```  
  
 В проверяемом коде не допускается использование следующих ключевых слов:  
  
-   директивы pragma [unmanaged](../preprocessor/managed-unmanaged.md) и [pack](../preprocessor/pack.md)  
  
-   модификаторы [naked](../Topic/naked%20\(C++\).md) и [align](../cpp/align-cpp.md) [\_\_declspec](../cpp/declspec.md)  
  
-   [\_\_asm](../assembler/inline/asm.md)  
  
-   [\_\_based](../cpp/based-grammar.md)  
  
-   [\_\_try](../cpp/try-except-statement.md) и `__except`  
  
## См. также  
 [Чистый и проверяемый код](../dotnet/pure-and-verifiable-code-cpp-cli.md)