---
title: "bss_seg | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc-pragma.bss_seg"
  - "bss_seg_CPP"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "bss_seg - прагма"
  - "прагмы, bss_seg"
ms.assetid: 755f0154-de51-4778-97d3-c9b24e445079
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# bss_seg
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Задает сегмент, в котором неинициализированные переменные сохраняются в OBJ\-файле.  
  
## Синтаксис  
  
```  
  
#pragma bss_seg( [ [ { push | pop }, ] [ identifier, ] ] [ "segment-name" [, "segment-class" ] )  
```  
  
## Заметки  
 OBJ\-файлы можно просматривать в приложении [dumpbin](../build/reference/dumpbin-command-line.md).  По умолчанию сегмент в OBJ\-файле для неинициализированных данных — BSS.  В некоторых случаях использование **bss\_seg** может ускорить время загрузки благодаря группировке неинициализированных данных в один раздел.  
  
 **bss\_seg** без параметров сбрасывает сегмент до BSS.  
  
 **push** \(необязательно\)  
 Помещает запись во внутренний стек компилятора.  Ключевое слово **push** может иметь *идентификатор* и *имя\-сегмента*.  
  
 **pop** \(необязательно\)  
 Удаляет запись из вершины внутреннего стека компилятора.  
  
 *идентификатор* \(необязательно\)  
 Если используется с ключевым словом **push**, назначает имя записи во внутреннем стеке компилятора.  Если используется с ключевым словом **pop**, выводит запись из внутреннего стека до тех пор, пока не будет удален соответствующий *идентификатор*. Если этот *идентификатор* во внутреннем стеке не найден, записи не выводятся.  
  
 Параметр *identifier* позволяет при помощи одной команды **pop** вывести несколько записей.  
  
 *"имя\-сегмента"* \(необязательно\)  
 Имя сегмента*.* Если используется с ключевым словом **pop**, то стек выводится, а *имя\-сегмента* становится активным именем сегмента.  
  
 *"класс\-сегмента"* \(необязательно\)  
 Включено для обеспечения совместимости с C\+\+ до версии 2.0.  Игнорируется.  
  
## Пример  
  
```  
// pragma_directive_bss_seg.cpp  
int i;                     // stored in .bss  
#pragma bss_seg(".my_data1")  
int j;                     // stored in "my_data1"  
  
#pragma bss_seg(push, stack1, ".my_data2")     
int l;                     // stored in "my_data2"  
  
#pragma bss_seg(pop, stack1)   // pop stack1 from stack  
int m;                     // stored in "stack_data1"  
  
int main() {  
}  
```  
  
 Можно также задать разделы для инициализированных данных \([data\_seg](../preprocessor/data-seg.md)\), функций \([code\_seg](../preprocessor/code-seg.md)\) и переменных const \([code\_seg](../preprocessor/const-seg.md)\).  
  
 Данные, предоставленные с использованием директивы pragma **bss\_seg**, не сохраняют никакой информации о своем расположении.  
  
 Список имен, которые не следует использовать при создании раздела, см. в разделе [\/SECTION](../build/reference/section-specify-section-attributes.md).  
  
## См. также  
 [Директивы Pragma и ключевое слово \_\_Pragma](../preprocessor/pragma-directives-and-the-pragma-keyword.md)