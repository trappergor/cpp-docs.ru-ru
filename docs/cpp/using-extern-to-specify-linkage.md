---
title: "Использование ключевого слова extern для задания компоновки | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "extern"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "объявления, внешние"
  - "extern - ключевое слово [C++], связь с отличными от C++ функциями"
  - "внешняя компоновка, extern - модификатор"
ms.assetid: 1e2f0ae3-ae98-4410-85b5-222d6abc865a
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 11
---
# Использование ключевого слова extern для задания компоновки
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

## Синтаксис  
  
```  
  
        extern string-literal { declaration-list }  
extern string-literal declaration  
```  
  
## Заметки  
 Ключевое слово `extern` объявляет переменную или функцию и указывает, что она имеет внешние компоновки \(ее имя будет видимым не только в пределах файла, в котором она определена, но и в других файлах\).  Когда выполняется изменение переменной, ключевое слово `extern` обозначает, что переменная имеет статическую длительность \(она выделяется в начале программы и высвобождается при завершении\).  Переменная или функция может быть определена в другом исходном файле или позднее в том же самом файле.  Объявления переменных и функций в области видимости файла являются внешними по умолчанию.  
  
## Пример  
  
```  
// specifying_linkage1.cpp  
int i = 1;  
void other();  
  
int main() {  
   // Reference to i, defined above:  
   extern int i;  
}  
  
void other() {  
   // Address of global i assigned to pointer variable:  
   static int *external_i = &i;  
  
   // i will be redefined; global i no longer visible:  
   // int i = 16;  
}  
```  
  
 Если в C\+\+ ключевое слово `extern` используется со строковым объектом, это означает, что для деклараторов используются соглашения о компоновках другого языка.  К функциям и данным C можно обращаться, только если ранее они были объявлены как имеющие компоновки C.  Однако они должны быть определены в блоке трансляции, который компилируется отдельно.  
  
 В Microsoft C\+\+ поддерживаются строки **"C"** и **"C\+\+"** в поле *строковый\-литерал*.  Во всех стандартных включаемых файлах используется синтаксис `extern`, характерный для языка C, благодаря чему в программах C\+\+ можно использовать функции библиотеки среды выполнения.  
  
## Пример  
 В следующем примере показаны другие способы объявления имен, которые имеют компоновки C:  
  
```  
// specifying_linkage2.cpp  
// compile with: /c  
// Declare printf with C linkage.  
extern "C" int printf( const char *fmt, ... );  
  
//  Cause everything in the specified header files  
//   to have C linkage.  
extern "C" {  
   // add your #include statements here  
   #include <stdio.h>  
}  
  
//  Declare the two functions ShowChar and GetChar  
//   with C linkage.  
extern "C" {  
   char ShowChar( char ch );  
   char GetChar( void );  
}  
  
//  Define the two functions ShowChar and GetChar  
//   with C linkage.  
extern "C" char ShowChar( char ch ) {  
   putchar( ch );  
   return ch;  
}  
  
extern "C" char GetChar( void ) {  
   char ch;  
  
   ch = getchar();  
   return ch;  
}  
  
// Declare a global variable, errno, with C linkage.  
extern "C" int errno;  
```  
  
 Если у функции несколько спецификаций компоновки, они должны быть согласованы; если для функции объявлены компоновки C и C\+\+ — это ошибка.  Кроме того, если в программе имеются два объявления функции \(одно со спецификацией компоновки, а другое без такой спецификации\), объявление с указанием компоновки должен быть первым.  Ко всем повторным объявлениям функций, уже имеющих спецификацию компоновки, применяется компоновка из первого объявления.  Пример:  
  
```  
extern "C" int CFunc1();  
...  
int CFunc1();            // Redeclaration is benign; C linkage is  
                         //  retained.  
  
int CFunc2();  
...  
extern "C" int CFunc2(); // Error: not the first declaration of  
                         //  CFunc2;  cannot contain linkage  
                         //  specifier.  
```  
  
 Функции и объекты, явно объявленные как **static** в теле составного описателя компоновки \(**{ }**\), рассматриваются как статические функции или объекты; описатель компоновки игнорируется.  Остальные функции и объекты ведут себя так, как если бы они были объявлены с помощью ключевого слова `extern`.  \(В разделе [Использование extern для указания компоновки](../cpp/using-extern-to-specify-linkage.md) см. подробнее о ключевом слове `extern`\)  
  
## См. также  
 [Ключевые слова в C\+\+](../cpp/keywords-cpp.md)   
 [\(NOTINBUILD\)Linkage Specifications](http://msdn.microsoft.com/ru-ru/d2b0cff1-7798-4c38-9ac8-61c3bfe2bfb9)   
 [Спецификатор класса хранения extern](../c-language/extern-storage-class-specifier.md)   
 [Поведение идентификаторов](../c-language/behavior-of-identifiers.md)   
 [Компоновка](../c-language/linkage.md)