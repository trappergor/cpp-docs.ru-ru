---
title: "__unaligned | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "__unaligned_cpp"
  - "__unaligned"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__unaligned - ключевое слово [C++]"
ms.assetid: 0cd83aad-1840-47e3-ad33-59bfcbe6375b
caps.latest.revision: 11
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# __unaligned
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

При объявлении указателя с модификатором `__unaligned` компилятор предполагает, что указатель обращается к данным без выравнивания.  Поэтому для тех приложений, которые предназначены для компьютеров с процессором семейства Itanium, компилятор создает код, считывающий такие данные по одному байту за раз.  
  
## Заметки  
 Модификатор `__unaligned` допустим для компиляторов [!INCLUDE[vcprx64](../Token/vcprx64_md.md)] и [!INCLUDE[vcpritanium](../cpp/includes/vcpritanium_md.md)], но действует только для приложений, предназначенных для компьютеров с процессором семейства Itanium.  Этот модификатор описывает только выравнивание данных, к которым выполняется обращение. Сам по себе указатель считается выровненным.  
  
 При обращении к данным с неверным выравниванием процессор семейства [!INCLUDE[vcpritanium](../cpp/includes/vcpritanium_md.md)] создает ошибку выравнивания, а время, необходимое для ее обработки, снижает производительность.  Используйте модификатор `__unaligned`, чтобы указать процессору считывать по одному байту за раз и предотвратить ошибку.  Этот модификатор не требуется для приложений [!INCLUDE[vcprx64](../Token/vcprx64_md.md)], поскольку процессор [!INCLUDE[vcprx64](../Token/vcprx64_md.md)] без ошибок обрабатывает данные с неверным выравниванием.  
  
 Дополнительные сведения о выравнивании см. в разделах:  
  
-   [align](../cpp/align-cpp.md)  
  
-   [Оператор \_\_alignof](../cpp/alignof-operator.md)  
  
-   [pack](../preprocessor/pack.md)  
  
-   [\/Zp \(Выравнивание члена структуры\)](../Topic/-Zp%20\(Struct%20Member%20Alignment\).md)  
  
-   [Примеры выравнивания структуры](../build/examples-of-structure-alignment.md)  
  
## Пример  
  
```  
// unaligned_keyword.cpp  
// compile with: /c  
// processor: x64 IPF  
#include <stdio.h>  
int main() {  
   char buf[100];  
  
   int __unaligned *p1 = (int*)(&buf[37]);  
   int *p2 = (int *)p1;  
  
   *p1 = 0;   // ok  
  
   __try {  
      *p2 = 0;  // throws an exception  
   }  
   __except(1) {  
      puts("exception");  
   }  
}  
```  
  
## См. также  
 [Ключевые слова в C\+\+](../cpp/keywords-cpp.md)