---
title: "code_seg | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "code_seg_CPP"
  - "vc-pragma.code_seg"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "code_seg - прагма"
  - "прагмы, code_seg"
ms.assetid: bf4faac1-a511-46a6-8d9e-456851d97d56
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# code_seg
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Определяет текстовый сегмент, в котором хранятся функции в OBJ\-файле.  
  
## Синтаксис  
  
```  
#pragma code_seg( [ [ { push | pop }, ] [ identifier, ] ] [ "segment-name" [, "segment-class" ] )  
```  
  
## Заметки  
 Директива pragma `code_seg` не управляет размещением ни объектного кода, созданного для шаблонов с созданными экземплярами, ни неявно созданного компилятором кода, например, специальных функций\-членов.  Рекомендуется вместо этого использовать атрибут [\_\_declspec \(code\_seg \(...\)\)](../cpp/code-seg-declspec.md), поскольку он предоставляет возможность управления размещением всего объектного кода.  Сюда включается созданный компилятором код.  
  
 *Сегмент* в obj\-файле представляет собой именованный блок данных , который загружается в память как одно целое.  *Сегмент текста* — сегмент, содержащий исполняемый код.  В этой статье термины *сегмент* и *раздел* используются взаимозаменяемо.  
  
 Директива pragma `code_seg` заставляет компилятор поместить весь последующий объектный код из блока трансляции в сегмент текста с именем `segment-name`.  По умолчанию для функций в obj\-файле используется сегмент с именем .text.  
  
 Директива pragma `code_seg` без параметров сбрасывает имя сегмента текста для последующего объектного кода на значение .text.  
  
 **Push** \(необязательно\)  
 Помещает запись во внутренний стек компилятора.  **push** может иметь `identifier` и `segment-name`.  
  
 **pop** \(необязательно\)  
 Удаляет запись из вершины внутреннего стека компилятора.  
  
 `identifier` \(необязательно\)  
 При использовании с директивой **push** присваивает имя записи во внутреннем стеке компилятора.  При использовании с директивой **pop** записи из внутреннего стека извлекаются до тех пор, пока не будет удален идентификатор `identifier`; если идентификатор `identifier` во внутреннем стеке не найден, ничего не извлекается.  
  
 `identifier` позволяет при помощи одной команды **pop** вывести сразу несколько записей.  
  
 "`segment-name`" \(необязательно\)  
 Имя сегмента.  При использовании с **pop** стек выводится, а `segment-name` становится активным именем текстового сегмента.  
  
 "`segment-class`" \(необязательно\)  
 Игнорируется, но включается для обеспечения совместимости с версиями C\+\+ до версии 2.0.  
  
 Можно использовать приложение [DUMPBIN.EXE](../build/reference/dumpbin-command-line.md) для просмотра obj\-файлов.  Версии DUMPBIN для каждой поддерживаемой целевой архитектуры входят в состав [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)].  
  
## Пример  
 В этом примере показано, как использовать директиву pragma `code_seg` для определения места размещения объектного кода:  
  
```  
// pragma_directive_code_seg.cpp  
void func1() {                  // stored in .text  
}  
  
#pragma code_seg(".my_data1")  
void func2() {                  // stored in my_data1  
}  
  
#pragma code_seg(push, r1, ".my_data2")  
void func3() {                  // stored in my_data2  
}  
  
#pragma code_seg(pop, r1)      // stored in my_data1  
void func4() {  
}  
  
int main() {  
}  
```  
  
 Список имен, которые не следует использовать для создания раздела, см. в разделе [\/SECTION](../build/reference/section-specify-section-attributes.md).  
  
 Можно также указать разделы для инициализированных данных \([data\_seg](../preprocessor/data-seg.md)\), неинициализированных данных \([bss\_seg](../preprocessor/bss-seg.md)\) и переменных const \([const\_seg](../preprocessor/const-seg.md)\).  
  
## См. также  
 [code\_seg \(\_\_declspec\)](../cpp/code-seg-declspec.md)   
 [Директивы Pragma и ключевое слово \_\_Pragma](../preprocessor/pragma-directives-and-the-pragma-keyword.md)