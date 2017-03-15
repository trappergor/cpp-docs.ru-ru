---
title: "Необработанные исключения C++ | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "обработка исключений С++, необработанные исключения"
  - "catch - ключевое слово [C++], обработчик не найден"
  - "обработчики событий, необработанные исключения"
  - "исключения, необработанные"
  - "необработанные исключения"
ms.assetid: 13f09c53-9254-4407-9db9-14e730e047cc
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Необработанные исключения C++
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Если для текущего исключения не удается найти подходящий обработчик \(или обработчик **catch** для многоточия\), то вызывается предопределенная функция времени выполнения `terminate`. \(Функцию `terminate` также можно явным образом вызвать из любого обработчика.\) Действие по умолчанию для `terminate` заключается в том, что она вызывает функцию `abort`.  Если вам необходимо, чтобы перед выходом из приложения функция `terminate` в вашей программе вызывала какую\-то другую функцию, вызовите функцию `set_terminate`, указав в качестве ее единственного аргумента ту функцию, которую нужно вызвать.  Функцию `set_terminate` можно вызвать из любого места программы.  Процедура `terminate` всегда вызывает последнюю функцию, заданную в качестве аргумента для `set_terminate`.  
  
## Пример  
 В следующем примере создается исключение типа `char *`, однако в нем нет обработчика, предназначенного для перехвата исключений `char *`.  Вызов `set_terminate` содержит инструкцию, согласно которой `terminate` вызывает функцию `term_func`.  
  
```  
// exceptions_Unhandled_Exceptions.cpp  
// compile with: /EHsc  
#include <iostream>  
using namespace std;  
void term_func() {  
   cout << "term_func was called by terminate." << endl;  
   exit( -1 );  
}  
int main() {  
   try  
   {  
      set_terminate( term_func );  
      throw "Out of memory!"; // No catch handler for this exception  
   }  
   catch( int )  
   {  
      cout << "Integer exception raised." << endl;  
   }  
   return 0;  
}  
```  
  
## Вывод  
  
```  
term_func was called by terminate.  
```  
  
 Функция `term_func` должна завершать программу или текущий поток \(желательно путем вызова функции `exit`\).  Если вместо этого она возвращает управление вызвавшему объекту, то вызывается функция `abort`.  
  
## См. также  
 [Обработка исключений С\+\+](../cpp/cpp-exception-handling.md)