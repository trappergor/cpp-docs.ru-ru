---
title: "Предупреждение компилятора (уровень 1) C4251 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4251"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4251"
ms.assetid: a9992038-f0c2-4fc4-a9be-4509442cbc1e
caps.latest.revision: 16
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 16
---
# Предупреждение компилятора (уровень 1) C4251
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"идентификатор": класс "тип" должен иметь dll\-интерфейс для использования клиентами класса "тип\_2"  
  
 Для минимизации возможности повреждения данных во время экспортирования класса с параметром [\_\_declspec\(dllexport\)](../../cpp/dllexport-dllimport.md) убедитесь, что соблюдаются следующие условия.  
  
-   Все статические данные доступны функциям, экспортируемым из библиотеки DLL.  
  
-   Ни один из встроенных методов класса не может изменить статистические данные.  
  
-   Функции CRT не используются ни одним из встроенных методов класса, а статические данные не используются иными библиотечными функциями \(дополнительные сведения см. в разделе [Потенциальные ошибки при передаче объектов CRT через границы DLL](../../c-runtime-library/potential-errors-passing-crt-objects-across-dll-boundaries.md)\).  
  
-   Ни один из методов класса \(независимо от встраивания\) не может использовать типы, в которых присутствует отличие статистических данных экземпляров в EXE и DLL.  
  
 Экспортирование классов можно предотвратить путем определения библиотеки DLL, определяющей класс с виртуальными функциями, и функций, которые можно вызвать для создания и удаления объектов типа.  Затем можно вызвать виртуальные функции типа.  
  
 Дополнительные сведения о экспортировать шаблоны см. в разделе [http:\/\/support.microsoft.com\/default.aspx?scid\=KB;EN\-US;168958](http://support.microsoft.com/default.aspx?scid=KB;EN-US;168958).  
  
 Ошибка C4251 может быть пропущена при наследовании от типа из стандартной библиотеки C\+\+ при компиляции отладочного выпуска \(**\/MTd**\), где сообщение об ошибке компилятора ссылается на \_Container\_base.  
  
```  
// C4251.cpp  
// compile with: /EHsc /MTd /W2 /c  
#include <vector>  
using namespace std;  
class Node;  
class __declspec(dllimport) VecWrapper : vector<Node *> {};   // C4251  
```