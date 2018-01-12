---
title: "-Zc: встроенная (удаление COMDAT без ссылки) | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- /Zc:inline
- VC.Project.VCCLCompilerTool.RemoveUnreferencedCodeData
dev_langs: C++
helpviewer_keywords:
- -Zc compiler options (C++)
- /Zc compiler options (C++)
- Zc compiler options (C++)
- /Zc:inline
ms.assetid: a4c94224-1d73-4bea-a9d5-4fa73dc924df
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 1c8d14f6055c96f5c9feed16d2ad0b996f0d0b94
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="zcinline-remove-unreferenced-comdat"></a>/Zc:inline (удаление COMDAT без ссылки)
Удаляет неиспользуемые функции или данные, являющиеся секциями COMDAT или имеющими только внутреннюю компоновку. Когда **/Zc: inline** указан, компилятор требует преобразования, в которых используются подставляемые данные или встроенные функции также включали определения данных или функций.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
/Zc:inline[-]  
```  
  
## <a name="remarks"></a>Примечания  
 Когда **/Zc: inline** указан, компилятор не выдает символьную информацию для неиспользуемые функции COMDAT или данных, а также для функций или данных, которые имеют только внутреннюю компоновку. По умолчанию этот параметр выключен (**/Zc:inline-**). Эта оптимизация упрощает часть работы, выполняемой компоновщиком в сборке выпуска или если параметр компоновщика [/OPT: ref](../../build/reference/opt-optimizations.md) указано. Если компилятор выполняет эту оптимизацию, размер файла OBJ может значительно уменьшиться, а скорость работы компоновщика — возрасти. Этот параметр компилятора не включен, после отключения оптимизации ([/Od](../../build/reference/od-disable-debug.md)) или когда [/GL (оптимизация всей программы)](../../build/reference/gl-whole-program-optimization.md) указано.  
  
 Если **/Zc: inline** указан, компилятор следит за выполнением C ++ 11 требования, все функции, объявленные `inline` должен иметь определение в той же записи преобразования, если они используются. Если этот параметр не указан, [!INCLUDE[vcprvc](../../build/includes/vcprvc_md.md)] разрешает создание не соответствующего стандарту кода, который вызывает функции, объявленные как `inline`, даже если определение недоступно. Подробнее см. в разделах 3.2 и 7.1.2 стандарта C++11. Этот параметр компилятора появился в Visual Studio 2013 с обновлением 2.  
  
 Для использования **/Zc: inline** параметр обновите не соответствующий стандарту код. В этом примере показано, как несовместимые использование объявления встраиваемой функции без определения по-прежнему компилируется и ссылки, когда значение по умолчанию **/Zc:inline-** используется параметр:  
  
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
  
 Когда **/Zc: inline** включена, этот же код вызывает [LNK2019](../../error-messages/tool-errors/linker-tools-error-lnk2019.md) ошибку, так как компилятор не создает неподставляемый код для `Example::inline_call` в файле example.obj. Из-за этого неподставляемый вызов в `main` ссылается на неопределенный внешний символ.  
  
 Чтобы устранить эту ошибку, можно удалить ключевое слово `inline` из объявления `Example::inline_call`, перенести определение `Example::inline_call` в файл заголовка или перенести реализацию `Example` в файл main.cpp. В следующем примере определение переносится в файл заголовка, где оно доступно любому вызывающему объекту, включающему заголовок.  
  
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
  
 Дополнительные сведения о вопросах соответствия в Visual C++ см. в статье [Nonstandard Behavior](../../cpp/nonstandard-behavior.md).  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Установка данного параметра компилятора в среде разработки Visual Studio  
  
1.  Откройте диалоговое окно **Страницы свойств** проекта. Дополнительные сведения см. в разделе [работа со свойствами проекта](../../ide/working-with-project-properties.md).  
  
2.  Выберите **C/C++** папки.  
  
3.  Выберите **командной строки** страницу свойств.  
  
4.  Изменить **Дополнительные параметры** включив `/Zc:inline` и выберите **ОК**.  
  
## <a name="see-also"></a>См. также  
 [/Zc (соответствие)](../../build/reference/zc-conformance.md)