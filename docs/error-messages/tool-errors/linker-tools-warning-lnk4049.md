---
title: "Предупреждение средств компоновщика LNK4049 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: LNK4049
dev_langs: C++
helpviewer_keywords: LNK4049
ms.assetid: 5fd5fb24-c860-4149-a557-0ac26a65d97c
caps.latest.revision: "19"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: f44634bd99e485e444ffe9cee7747f31374becf4
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="linker-tools-warning-lnk4049"></a>Предупреждение средств компоновщика LNK4049
локально определенный символ «символ» импортируется  
  
 Символ был и экспортировать из импортирован в программу.  
  
 Это предупреждение создается компоновщиком при объявлении символа с помощью `__declspec(dllexport)` storage-class-атрибут в одном объектном файле и ссылки на него с помощью `__declspec(dllimport)` атрибут в другом.  
  
 Предупреждение LNK4049 является более общей версией [Предупреждение средств компоновщика LNK4217](../../error-messages/tool-errors/linker-tools-warning-lnk4217.md). Компоновщик создает предупреждение LNK4049, когда не удается определить, из которого функция была ссылка на импортированный символ.  
  
 Ниже перечислены случаи LNK4049 выводится вместо LNK4217  
  
-   Выполнение инкрементную компоновку с помощью [/INCREMENTAL](../../build/reference/incremental-link-incrementally.md) параметр.  
  
-   Выполнение оптимизации всей программы с использованием [/LTCG](../../build/reference/ltcg-link-time-code-generation.md) параметр.  
  
 Чтобы устранить LNK4049, попробуйте один из следующих:  
  
-   Удалить `__declspec(dllimport)` объявление из опережающего объявления символа активировавшего LNK4049 имени. Можно выполнить поиск символов в двоичном образе с помощью **DUMPBIN** программы. **DUMPBIN/СИМВОЛЫ** отображает таблицей символов COFF изображения. Дополнительные сведения о **DUMPBIN** программы, в разделе [Справочник DUMPBIN](../../build/reference/dumpbin-reference.md).  
  
-   Временно отключите последовательную компоновку и оптимизации всей программы. Повторной компиляции приложения будет создавать Предупреждение LNK4217, в том числе имя функции, из которой была ссылка на импортированный символ. Удалить `__declspec(dllimport)` объявление из импортированного символа и Включить инкрементную компоновку или оптимизации всей программы при необходимости.  
  
 Несмотря на то, что конечный созданный код будет функционировать правильно, код, созданный для вызова импортированной функции является менее эффективным, чем непосредственный вызов функции. Это предупреждение не будет выводиться при компиляции с помощью параметра [/CLR](../../build/reference/clr-common-language-runtime-compilation.md).  
  
 Дополнительные сведения о импорта и экспорта данных объявления, см. в разделе [dllexport, dllimport](../../cpp/dllexport-dllimport.md).  
  
## <a name="example"></a>Пример  
 Компоновка следующих двух модулей вызовет предупреждение LNK4049. Первый модуль создает объектный файл, содержащий одну экспортированную функцию.  
  
```  
// LNK4049a.cpp  
// compile with: /c  
  
__declspec(dllexport) int func()   
{  
   return 3;  
}  
```  
  
## <a name="example"></a>Пример  
 Второй модуль создает объектный файл, содержащий упреждающее объявление для функции, экспортированной в первый модуль, а также вызов данной функции в `main` функции. Компоновка этого модуля с первым модулем вызывает предупреждение LNK4049. Удаление `__declspec(dllimport)` объявление устранить предупреждение.  
  
```  
// LNK4049b.cpp  
// compile with: /link /WX /LTCG LNK4049a.obj  
// LNK4049 expected  
  
__declspec(dllimport) int func();  
// try the following line instead  
// int func();  
  
int main()  
{  
   return func();  
}  
```  
  
## <a name="see-also"></a>См. также  
 [Предупреждение средств компоновщика LNK4217](../../error-messages/tool-errors/linker-tools-warning-lnk4217.md)   
 [dllexport, dllimport](../../cpp/dllexport-dllimport.md)