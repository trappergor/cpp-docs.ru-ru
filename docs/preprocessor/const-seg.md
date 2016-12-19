---
title: "const_seg | Microsoft Docs"
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
  - "vc-pragma.const_seg"
  - "const_seg_CPP"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "const_seg - прагма"
  - "прагмы, const_seg"
ms.assetid: 1eb58ee2-fb0e-4a39-9621-699c8f5ef957
caps.latest.revision: 12
caps.handback.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# const_seg
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Указывает сегмент, в котором хранятся переменные [const](../cpp/const-cpp.md) в файле .obj.  
  
## Синтаксис  
  
```  
#pragma const_seg ( [ [ { push | pop}, ] [ identifier, ] ] [ "segment-name" [, "segment-class" ] )  
```  
  
## Заметки  
 Термины *сегмент* и *раздел* в этом разделе взаимозаменимы.  
  
 OBJ\-файлы можно просматривать в приложении [dumpbin](../build/reference/dumpbin-command-line.md).  По умолчанию для хранения переменных `const` в OBJ\-файле используется сегмент .rdata.  Некоторые переменные `const`, например скаляры, автоматически подставляются в поток кода.  Подставляемый код не отображается в сегменте .rdata.  
  
 Определение объекта, требующее динамической инициализации в `const_seg`, приводит к неопределенному поведению.  
  
 `#pragma const_seg` без параметров сбрасывает сегмент до .rdata.  
  
 `push` \(необязательно\)  
 Помещает запись во внутренний стек компилятора.  `push` может иметь `identifier` и `segment-name`.  
  
 `pop` \(необязательно\)  
 Удаляет запись из вершины внутреннего стека компилятора.  
  
 `identifier` \(необязательно\)  
 При использовании с директивой `push` присваивает имя записи во внутреннем стеке компилятора.  При использовании с директивой `pop` записи из внутреннего стека извлекаются до тех пор, пока не будет удален идентификатор `identifier`; если идентификатор `identifier` во внутреннем стеке не найден, ничего не извлекается.  
  
 `identifier` позволяет с помощью одной команды `pop` вывести сразу несколько записей.  
  
 "`segment-name`" \(необязательно\)  
 Имя сегмента.  При использовании с `pop` стек выводится, а `segment-name` становится активным именем сегмента.  
  
 "`segment-class`" \(необязательно\)  
 Включено для обеспечения совместимости с C\+\+ до версии 2.0.  Игнорируется.  
  
## Пример  
  
```  
// pragma_directive_const_seg.cpp  
// compile with: /EHsc  
#include <iostream>  
  
const int i = 7;               // inlined, not stored in .rdata  
const char sz1[]= "test1";     // stored in .rdata  
  
#pragma const_seg(".my_data1")  
const char sz2[]= "test2";     // stored in .my_data1  
  
#pragma const_seg(push, stack1, ".my_data2")  
const char sz3[]= "test3";     // stored in .my_data2  
  
#pragma const_seg(pop, stack1) // pop stack1 from stack  
const char sz4[]= "test4";     // stored in .my_data1  
  
int main() {  
    using namespace std;  
   // const data must be referenced to be put in .obj  
   cout << sz1 << endl;  
   cout << sz2 << endl;  
   cout << sz3 << endl;  
   cout << sz4 << endl;  
}  
```  
  
  **test1**  
**test2**  
**test3**  
**test4**   
## Примечания  
 Список имен, которые не следует использовать при создании раздела, см. в разделе [\/SECTION](../build/reference/section-specify-section-attributes.md).  
  
 Кроме того, можно указать разделы для инициализированных данных \([data\_seg](../preprocessor/data-seg.md)\), неинициализированных данных \([bss\_seg](../preprocessor/bss-seg.md)\), а также функций \([code\_seg](../preprocessor/code-seg.md)\).  
  
## См. также  
 [Директивы Pragma и ключевое слово \_\_Pragma](../preprocessor/pragma-directives-and-the-pragma-keyword.md)