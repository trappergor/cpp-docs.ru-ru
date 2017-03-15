---
title: "data_seg | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "data_seg_CPP"
  - "vc-pragma.data_seg"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "data_seg - прагма"
  - "прагмы, data_seg"
ms.assetid: 65c66466-4c98-494f-93af-106beb4caf78
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# data_seg
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Задает сегмент данных, в котором инициализированные переменные сохраняются в OBJ\-файле.  
  
## Синтаксис  
  
```  
  
#pragma data_seg( [ [ { push | pop }, ] [ identifier, ] ] [ "segment-name" [, "segment-class" ] )  
```  
  
## Заметки  
 Термины *сегмент* и *раздел* в этом разделе взаимозаменимы.  
  
 OBJ\-файлы можно просматривать в приложении [dumpbin](../build/reference/dumpbin-command-line.md).  По умолчанию сегмент в OBJ\-файле для инициализированных переменных — DATA.  Неинициализированные переменные считаются инициализированными с нулем и сохраняются в BSS\-файле.  
  
 **data\_seg** без параметров сбрасывает сегмент до DATA.  
  
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
// pragma_directive_data_seg.cpp  
int h = 1;                     // stored in .data  
int i = 0;                     // stored in .bss  
#pragma data_seg(".my_data1")  
int j = 1;                     // stored in "my_data1"  
  
#pragma data_seg(push, stack1, ".my_data2")     
int l = 2;                     // stored in "my_data2"  
  
#pragma data_seg(pop, stack1)   // pop stack1 off the stack  
int m = 3;                     // stored in "stack_data1"  
  
int main() {  
}  
```  
  
 Данные, предоставленные с использованием **data\_seg**, не сохраняют никакой информации о своем расположении.  
  
 Список имен, которые не следует использовать при создании раздела, см. в разделе [\/SECTION](../build/reference/section-specify-section-attributes.md).  
  
 Можно также задать разделы для переменных const \([const\_seg](../preprocessor/const-seg.md)\), неинициализированных данных \([bss\_seg](../preprocessor/bss-seg.md)\) и функций \([code\_seg](../preprocessor/code-seg.md)\).  
  
## См. также  
 [Директивы Pragma и ключевое слово \_\_Pragma](../preprocessor/pragma-directives-and-the-pragma-keyword.md)