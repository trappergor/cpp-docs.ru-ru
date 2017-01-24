---
title: "/Zc:inline (удаление COMDAT без ссылки) | Microsoft Docs"
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
  - "/Zc:inline"
  - "VC.Project.VCCLCompilerTool.RemoveUnreferencedCodeData"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/Zc - параметры компилятора (C++)"
  - "/Zc:inline"
  - "Zc - параметры компилятора (C++)"
  - "-Zc - параметры компилятора (C++)"
ms.assetid: a4c94224-1d73-4bea-a9d5-4fa73dc924df
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /Zc:inline (удаление COMDAT без ссылки)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Удаляет неиспользуемые функции или данные, являющиеся секциями COMDAT или имеющими только внутреннюю компоновку.  Если указан параметр **\/Zc:inline**, компилятор требует, чтобы записи преобразования, в которых используются подставляемые данные или функции, также включали определения данных или функций.  
  
## Синтаксис  
  
```  
/Zc:inline[-]  
```  
  
## Заметки  
 Когда указан параметр **\/Zc:inline**, компилятор не выдает символьную информацию для неиспользуемых функций или данных COMDAT, а также для функций или данных, которые имеют только внутреннюю компоновку.  По умолчанию этот параметр выключен \(**\/Zc:inline\-**\).  Эта оптимизация упрощает часть работы, выполняемой компоновщиком в сборке выпуска или в случае, если указан параметр компоновщика [\/OPT:REF](../../build/reference/opt-optimizations.md).  Если компилятор выполняет эту оптимизацию, размер файла OBJ может значительно уменьшиться, а скорость работы компоновщика — возрасти.  Этот параметр компилятора не включается, если отключены оптимизации \([\/Od](../../build/reference/od-disable-debug.md)\) или если указан параметр [\/GL \(оптимизация всей программы\)](../../build/reference/gl-whole-program-optimization.md).  
  
 Если указан параметр **\/Zc:inline**, компилятор следит за выполнением требования C\+\+11, в соответствии с которым все используемые функции, объявленные как `inline`, должны иметь определение в той же записи преобразования.  Если этот параметр не указан, [!INCLUDE[vcprvc](../../build/includes/vcprvc_md.md)] разрешает создание не соответствующего стандарту кода, который вызывает функции, объявленные как `inline`, даже если определение недоступно.  Подробнее см. в разделах 3.2 и 7.1.2 стандарта C\+\+11.  Этот параметр компилятора появился в Visual Studio 2013 с обновлением 2.  
  
 Для использования параметра **\/Zc:inline** обновите не соответствующий стандарту код.  В приведенном ниже примере показано, как при не соответствующем стандарту использовании объявления подставляемой функции без определения код все же компонуется, если указан параметр **\/Zc:inline\-** по умолчанию.  
  
```cpp  
// example.h  
// Compile by using: cl /W4 /EHsc /O2 zcinline.cpp example.cpp  
#pragma once  
  
class Example {  
public:  
   inline void inline_call(); // declared but not defined inline  
   void normal_call();  
   Example() {};  
};  
```  
  
```cpp  
// example.cpp  
// Compile by using: cl /W4 /EHsc /O2 zcinline.cpp example.cpp  
#include <stdio.h>  
#include "example.h"  
  
void Example::inline_call() {  
   printf("inline_call was called.\n");   
}  
  
void Example::normal_call() {  
   printf("normal_call was called.\n");   
   inline_call(); // with /Zc:inline-, inline_call forced into .obj file  
}  
```  
  
```cpp  
// zcinline.cpp  
// Compile by using: cl /W4 /EHsc /O2 zcinline.cpp example.cpp  
#include "example.h"  
  
void main() {  
   Example example;  
   example.inline_call(); // normal call when definition unavailable  
}  
```  
  
 Если параметр **\/Zc:inline** включен, этот же код вызывает ошибку [LNK2019](../Topic/Linker%20Tools%20Error%20LNK2019.md), так как компилятор не создает неподставляемый код для `Example::inline_call` в файле example.obj.  Из\-за этого неподставляемый вызов в `main` ссылается на неопределенный внешний символ.  
  
 Чтобы устранить эту ошибку, можно удалить ключевое слово `inline` из объявления `Example::inline_call`, перенести определение `Example::inline_call` в файл заголовка или перенести реализацию `Example` в файл main.cpp.  В следующем примере определение переносится в файл заголовка, где оно доступно любому вызывающему объекту, включающему заголовок.  
  
```cpp  
// example2.h  
// Compile by using: cl /W4 /EHsc /O2 zcinline2.cpp example2.cpp  
#pragma once  
#include <stdio.h>  
  
class Example2 {  
public:  
   inline void inline_call() {  
      printf("inline_call was called.\n");   
   }  
   void normal_call();  
   Example2() {};  
};  
```  
  
```cpp  
// example2.cpp  
// Compile by using: cl /W4 /EHsc /O2 zcinline2.cpp example2.cpp  
#include "example2.h"  
  
void Example2::normal_call() {  
   printf("normal_call was called.\n");   
   inline_call();   
}  
```  
  
```cpp  
// zcinline2.cpp  
// Compile by using: cl /W4 /EHsc /O2 zcinline2.cpp example2.cpp  
#include "example2.h"  
  
void main() {  
   Example2 example2;  
   example2.inline_call(); // normal call when definition unavailable  
}  
```  
  
 Подробнее о вопросах соответствия в Visual C\+\+ см. в статье [Нестандартное поведение](../Topic/Nonstandard%20Behavior.md).  
  
### Установка данного параметра компилятора в среде разработки Visual Studio  
  
1.  Откройте диалоговое окно **Страницы свойств** проекта.  Дополнительные сведения см. в разделе [Работа со свойствами проектов](../../ide/working-with-project-properties.md).  
  
2.  Выберите папку **C\/C\+\+**.  
  
3.  Выберите страницу свойств **Командная строка**.  
  
4.  Измените свойство **Дополнительные параметры**, включив параметр `/Zc:inline`, а затем нажмите кнопку **ОК**.  
  
## См. также  
 [\/Zc \(соответствие\)](../../build/reference/zc-conformance.md)