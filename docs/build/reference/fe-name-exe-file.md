---
title: "-Fe (именование EXE-файла) | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: /fe
dev_langs: C++
helpviewer_keywords:
- -Fe compiler option [C++]
- executable files, renaming
- rename file compiler option [C++]
- /Fe compiler option [C++]
- Fe compiler option [C++]
ms.assetid: 49f594fd-5e94-45fe-a1bf-7c9f2abb6437
caps.latest.revision: "10"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: b66c473c49527dff395d206594a314b527c4f914
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="fe-name-exe-file"></a>/Fe (именование EXE-файла)
Указывает имя и каталог для файла .exe или библиотеку DLL, созданную компилятором.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
/Fepathname  
```  
  
## <a name="remarks"></a>Примечания  
 Без этого параметра компилятор присваивает файлу имя по умолчанию по базовому имени первого файла источника или объекта, указанного в командной строке и расширением .exe или .dll.  
  
 При указании[/c (компиляция без связывания)](../../build/reference/c-compile-without-linking.md), компиляцию без компоновки, **/Fe** не делает ничего.  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Установка данного параметра компилятора в среде разработки Visual Studio  
  
1.  Откройте диалоговое окно **Страницы свойств** проекта. Дополнительные сведения см. в разделе [работа со свойствами проекта](../../ide/working-with-project-properties.md).  
  
2.  Нажмите кнопку **компоновщика** папки.  
  
3.  Нажмите кнопку **Общие**страницу свойств.  
  
4.  Изменить **выходной файл** свойство.  
  
### <a name="to-set-this-compiler-option-programmatically"></a>Установка данного параметра компилятора программным способом  
  
-   См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.OutputFile%2A>.  
  
## <a name="example"></a>Пример  
 Следующая команда компилирует и связывает все исходные файлы C в текущем каталоге. Полученный исполняемый файл с именем PROCESS.exe и создается в каталоге C:\BIN.  
  
```  
CL /FeC:\BIN\PROCESS *.C  
```  
  
## <a name="example"></a>Пример  
 Следующая команда создает исполняемый файл в `C:\BIN` с такое же базовое имя первого исходного или объектного файла:  
  
```  
CL /FeC:\BIN\ *.C  
```  
  
## <a name="see-also"></a>См. также  
 [Выходного файла (/ F) параметры](../../build/reference/output-file-f-options.md)   
 [Параметры компилятора](../../build/reference/compiler-options.md)   
 [Настройка параметров компилятора](../../build/reference/setting-compiler-options.md)   
 [Указание пути](../../build/reference/specifying-the-pathname.md)