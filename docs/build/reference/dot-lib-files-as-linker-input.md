---
title: ". LIB-файл в качестве входных данных компоновщика | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: VC.Project.VCLinkerTool.AdditionalDependencies
dev_langs: C++
helpviewer_keywords:
- OMF libraries
- linking [C++], OMF libraries
- import libraries, linker files
- libraries [C++], .lib files as linker input
- COFF files, import libraries
- default libraries [C++], linker output
- default libraries [C++]
- defaults [C++], libraries
- .lib files
ms.assetid: dc5d2b1c-2487-41fa-aa71-ad1e0647958b
caps.latest.revision: "15"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 181c8c3e5e762f2f20d99ca2acadaf285e717b6c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="lib-files-as-linker-input"></a>LIB-файлы в качестве входных файлов компоновщика
LINK принимает стандартные библиотеки COFF и библиотеки импорта COFF, которые обычно имеют расширение. lib. Стандартные библиотеки содержат объекты и создаются с помощью инструмента LIB. Библиотеки импорта содержат сведения об экспорте в другие программы и создаются либо самим LINK при построении программы, содержащую экспорты, или с помощью инструмента LIB. Сведения о применении LIB для создания стандартных библиотек или библиотек импорта см. в разделе [Справочник по LIB](../../build/reference/lib-reference.md). Дополнительные сведения по созданию библиотеки импорта с помощью ссылки в разделе [/DLL](../../build/reference/dll-build-a-dll.md) параметр.  
  
Библиотека задается для СВЯЗИ как аргумент имени файла или библиотеки по умолчанию. LINK разрешает внешние ссылки, выполняя поиск вначале в библиотеках, указанных в командной строке, то по умолчанию библиотеки задано с помощью [/DEFAULTLIB](../../build/reference/defaultlib-specify-default-library.md) параметр, а затем по умолчанию библиотеках, указанных в OBJ-файлы. Если путь указан с именем библиотеки, LINK ищет библиотеки в этом каталоге. Если путь не указан, LINK ищет сначала в каталоге, из которой запущен LINK, а затем во всех каталогах, указанных в переменной среды LIB.  
  
## <a name="to-add-lib-files-as-linker-input-in-the-development-environment"></a>Для добавления LIB-файлы в качестве входных данных компоновщика в среде разработки  
  
1.  Откройте диалоговое окно **Страницы свойств** проекта. Дополнительные сведения см. в разделе [работа со свойствами проекта](../../ide/working-with-project-properties.md).  
  
2.  Выберите **ввода** на странице свойств в **компоновщика** папки.  
  
3.  Изменить **Дополнительные зависимости** свойство для добавления LIB-файлы.  
  
## <a name="to-programmatically-add-lib-files-as-linker-input"></a>Для программного добавления LIB-файлы, компоновщик-ввод  
  
-   В разделе [AdditionalDependencies](https://msdn.microsoft.com/library/microsoft.visualstudio.vcprojectengine.vclinkertool.additionaldependencies.aspx).  
  
## <a name="example"></a>Пример  
Следующий пример показано, как создать и использовать LIB-файл. Сначала нужно создайте LIB-файл:  
  
```cpp  
// lib_link_input_1.cpp  
// compile by using: cl /LD lib_link_input_1.cpp  
__declspec(dllexport) int Test() {  
   return 213;  
}  
```  
  
И после этого следует скомпилировать в этом примере с помощью LIB-файл, который вы только что создали.  
  
```cpp  
// lib_link_input_2.cpp  
// compile by using: cl /EHsc lib_link_input_1.lib lib_link_input_2.cpp   
__declspec(dllimport) int Test();  
#include <iostream>  
int main() {  
   std::cout << Test() << std::endl;  
}  
```  
  
```Output  
213  
```  
  
## <a name="see-also"></a>См. также  
 [Входные LINK-файлы](../../build/reference/link-input-files.md)   
 [Параметры компоновщика](../../build/reference/linker-options.md)