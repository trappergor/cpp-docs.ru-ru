---
title: "Оператор __alignof | Microsoft Docs"
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
  - "__alignof"
  - "alignof"
  - "alignas"
  - "__alignof_cpp"
  - "alignof_cpp"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__alignof - ключевое слово [C++]"
  - "alignas"
  - "выравнивание структур"
  - "alignof"
  - "типы [C++], требования к выравниванию"
ms.assetid: acb1eed7-6398-40bd-b0c5-684ceb64afbc
caps.latest.revision: 11
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Оператор __alignof
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

В C\+\+ 11 имеется оператор `alignof`, возвращающий выравнивание \(в байтах\) заданного типа.  Для обеспечения максимальной переносимости кода следует использовать оператор alignof вместо оператора \_\_alignof, тесно связанного с системами Майкрософт.  
  
 **Блок, относящийся только к системам Microsoft**  
  
 Возвращает значение типа **size\_t**, которое является требованием к выравниванию типа.  
  
## Синтаксис  
  
```  
  
        __alignof(   
   type    
)  
```  
  
## Заметки  
 Пример:  
  
|Выражение|Значение|  
|---------------|--------------|  
|**\_\_alignof\( char \)**|1|  
|**\_\_alignof\( short \)**|2|  
|**\_\_alignof\( int \)**|4|  
|**\_\_alignof\( \_\_int64 \)**|8|  
|**\_\_alignof\( float \)**|4|  
|**\_\_alignof\( double \)**|8|  
|**\_\_alignof\( char\* \)**|4|  
  
 Значение `__alignof` совпадает со значением `sizeof` для базовых типов.  Однако рассмотрим следующий пример.  
  
```  
typedef struct { int a; double b; } S;  
// __alignof(S) == 8  
```  
  
 В этом случае значение `__alignof` является требованием к выравниванию наибольшего элемента в структуре.  
  
 Аналогичным образов, в  
  
```  
typedef __declspec(align(32)) struct { int a; } S;  
```  
  
 `__alignof(S)` равно `32`.  
  
 Одним из применений выражения `__alignof` является его использование в качестве параметра одной из пользовательских подпрограмм выделения памяти.  Например, в следующей определенной структуре `S` можно вызвать подпрограмму выделения памяти с именем `aligned_malloc` для выделения памяти на определенной границе выравнивания.  
  
```  
typedef __declspec(align(32)) struct { int a; double b; } S;  
int n = 50; // array size  
S* p = (S*)aligned_malloc(n * sizeof(S), __alignof(S));  
```  
  
 Дополнительные сведения об изменении выравнивания см. в следующих разделах.  
  
-   [pack](../preprocessor/pack.md)  
  
-   [align](../cpp/align-cpp.md)  
  
-   [\_\_unaligned](../cpp/unaligned.md)  
  
-   [\/Zp \(Выравнивание члена структуры\)](../Topic/-Zp%20\(Struct%20Member%20Alignment\).md)  
  
-   [Примеры выравнивания структуры](../build/examples-of-structure-alignment.md) \(для x64\)  
  
 Дополнительные сведения о различиях в выравнивании в коде для 32\- \(x86\) и 64\-разрядных \(x64\) сред см. в статье  
  
-   [Конфликты с компилятором x86](../Topic/Conflicts%20with%20the%20x86%20Compiler.md)  
  
## Завершение блока, относящегося только к системам Майкрософт  
  
## См. также  
 [Выражения с унарными операторами](../Topic/Expressions%20with%20Unary%20Operators.md)   
 [Ключевые слова в C\+\+](../cpp/keywords-cpp.md)