---
title: "LIB-файлы в качестве входных файлов компоновщика | Microsoft Docs"
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
  - "VC.Project.VCLinkerTool.AdditionalDependencies"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LIB-файлы"
  - "COFF-файлы, библиотеки - импорт"
  - "библиотеки по умолчанию [C++]"
  - "библиотеки по умолчанию [C++], компоновщик - выходные данные"
  - "по умолчанию [C++], библиотеки"
  - "библиотеки - импорт, компоновочные файлы"
  - "библиотеки [C++], .LIB-файлы в качестве вводных файлов компоновщика"
  - "связывание [C++], OMF - библиотеки"
  - "OMF - библиотеки"
ms.assetid: dc5d2b1c-2487-41fa-aa71-ad1e0647958b
caps.latest.revision: 15
caps.handback.revision: 13
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# LIB-файлы в качестве входных файлов компоновщика
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

LINK принимает стандартные библиотеки COFF и библиотеки импорта COFF, которые обычно имеют расширение LIB.  Стандартные библиотеки содержат объекты и создаются с помощью инструмента LIB.  Библиотеки импорта содержат сведения об экспорте в другие программы и создаются либо самим LINK при построении программы, содержащей экспорт, либо инструментом LIB.  Подробнее о применении LIB для создания стандартных библиотек или библиотек импорта см. в [Справочнике LIB](../../build/reference/lib-reference.md).  Подробнее об использовании LINK для создания стандартных библиотек или библиотек импорта см. в разделе о параметре [\/DLL](../../build/reference/dll-build-a-dll.md).  
  
 Библиотека задается для LINK либо как аргумент имени файла, либо как библиотека по умолчанию.  LINK разрешает внешние ссылки, выполняя поиск вначале в библиотеках, указанных в командной строке, затем в библиотеках по умолчанию, заданных параметром [\/DEFAULTLIB](../../build/reference/defaultlib-specify-default-library.md), а после этого уже в библиотеках по умолчанию, указанных в OBJ\-файле.  Если путь указан с именем библиотеки, LINK ищет библиотеку в этой директории.  Если путь не указан, LINK ищет сначала в директории, из которой запущен LINK, а затем во всех директориях, указанных в переменной окружения LIB.  
  
### Для добавления LIB\-файлов в качестве ввода компоновщика в среде разработки  
  
1.  Откройте диалоговое окно **Страницы свойств** проекта.  Дополнительные сведения см. в разделе [Задание свойств проекта C\+\+](../../ide/working-with-project-properties.md).  
  
2.  Выберите папку **Компоновщик**.  
  
3.  Выберите страницу свойств **Ввод**.  
  
4.  Измените параметр **Дополнительные зависимости**.  
  
### Для добавления LIB\-файлов программными средствами  
  
-   См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AdditionalDependencies%2A>.  
  
## Пример  
 В следующем примере показано, как построить и использовать LIB\-файл:  
  
```  
// lib_link_input_1.cpp  
// compile with: /LD  
__declspec(dllexport) int Test() {  
   return 213;  
}  
```  
  
## Пример  
 Затем:  
  
```  
// lib_link_input_2.cpp  
// compile with: /EHsc lib_link_input_1.lib  
__declspec(dllimport) int Test();  
#include <iostream>  
int main() {  
   std::cout << Test() << std::endl;  
}  
```  
  
  **213**   
## См. также  
 [Входные LINK\-файлы](../../build/reference/link-input-files.md)   
 [Параметры компоновщика](../../build/reference/linker-options.md)